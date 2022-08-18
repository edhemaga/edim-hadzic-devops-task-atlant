FROM maven:3.8.6-jdk-8 AS build

COPY . .

RUN mvn -f pom.xml clean package

FROM openjdk:8-jdk-alpine AS jdk

ARG JAR_FILE=/target/*.jar

COPY --from=build ${JAR_FILE} app.jar

ARG CONFIG=src/main/resources/application.yml

COPY ${CONFIG} my-config.yml

EXPOSE 8080

ENTRYPOINT ["java","-jar","/app.jar", "--spring.config.location=my-config.yml"]
