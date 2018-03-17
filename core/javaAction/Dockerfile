FROM adoptopenjdk/openjdk8-openj9:jdk8u162-b12_openj9-0.8.0

ENV LANG=en_US.UTF-8 \
    LANGUAGE=en_US:en \
    LC_ALL=en_US.UTF-8 \
    VERSION=8 \
    UPDATE=152 \
    BUILD=16

ADD proxy /javaAction

RUN rm -rf /javaAction/.classpath /javaAction/.gitignore /javaAction/.gradle /javaAction/.project /javaAction/.settings /javaAction/Dockerfile /javaAction/build

RUN cd /javaAction && ./gradlew --console=plain oneJar

RUN rm -rf /javaAction/src

CMD ["java", "-jar", "/javaAction/build/libs/javaAction-all.jar"]
