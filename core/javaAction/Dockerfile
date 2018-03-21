FROM adoptopenjdk/openjdk8-openj9:jdk8u162-b12_openj9-0.8.0

LABEL name=java8action,version=0.1

RUN mkdir -p /javaAction

ADD compileClassCache.sh /javaAction
ADD build/libs/javaAction-all.jar /javaAction

RUN cd /javaAction && ./compileClassCache.sh

EXPOSE 8080
CMD ["java", "-Dfile.encoding=UTF-8", "-Xshareclasses:cacheDir=/javaSharedCache,readonly", "-Xquickstart", "-jar", "/javaAction/javaAction-all.jar"]
