FROM adoptopenjdk/openjdk8-openj9:x86_64-ubuntu-jdk8u152-b16

ENV DEBIAN_FRONTEND noninteractive

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

ENV VERSION 8
ENV UPDATE 152
ENV BUILD 16

ADD proxy /javaAction

RUN rm -rf /javaAction/.classpath /javaAction/.gitignore /javaAction/.gradle /javaAction/.project /javaAction/.settings /javaAction/Dockerfile /javaAction/build

RUN cd /javaAction; ./gradlew oneJar

RUN rm -rf /javaAction/src

CMD ["java", "-jar", "/javaAction/build/libs/javaAction-all.jar"]
