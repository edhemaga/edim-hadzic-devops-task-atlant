FROM maven AS maven

RUN  mvn clean package 

COPY *.jar .

FROM openjdk:8-jdk-alpine AS jdk

ARG JAR_FILE=target/*.jar

COPY ${JAR_FILE} app.jar

ARG CONFIG=src/main/resources/application.yml

COPY ${CONFIG} my-config.yml

EXPOSE 8080

ENTRYPOINT ["java","-jar","/app.jar", "--spring.config.location=/my-config.yml"]