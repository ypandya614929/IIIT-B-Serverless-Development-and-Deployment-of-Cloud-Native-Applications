# 1
FROM maven:3.8.2-jdk-11 as build
MAINTAINER ypandya614929
WORKDIR /opt/app

COPY src /opt/app/src
COPY pom.xml /opt/app
RUN mvn clean install dependency:resolve

# 2
FROM openjdk:14-jdk-alpine
MAINTAINER ypandya614929
WORKDIR /opt/app

COPY --from=build /opt/app/target/notificationService-jar-with-dependencies.jar /opt/app/notificationService-jar-with-dependencies.jar

CMD [ "java", "-jar", "/opt/app/notificationService-jar-with-dependencies.jar"]