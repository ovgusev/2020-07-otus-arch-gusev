#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS MAVEN_BUILD
COPY src /home/app/src
COPY pom.xml /home/app
RUN  mvn -f /home/app/pom.xml clean package
#
# Package stage
#
FROM openjdk:11-jre-slim
COPY --from=MAVEN_BUILD /home/app/target/actuator-app-1.0.jar /home/app/actuator-app.jar
EXPOSE 8000
ENTRYPOINT ["java","-jar","/home/app/actuator-app.jar"]