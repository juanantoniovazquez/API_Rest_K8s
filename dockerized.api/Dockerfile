#FROM alpine:latest

#CMD ["/bin/sh"]
FROM maven:3.8.4-openjdk-17-slim AS build

WORKDIR /app

ADD pom.xml .
RUN mvn package -Dmaven.test.skip -Declipselink.weave.skip

ADD src src
RUN mvn package -DskipTests 

RUN echo "done!"

FROM openjdk:21-jdk
EXPOSE 8080
COPY target/dockerized.api-0.0.1-SNAPSHOT.jar helado-api.jar
ENTRYPOINT ["java", "-jar", "helado-api.jar"]