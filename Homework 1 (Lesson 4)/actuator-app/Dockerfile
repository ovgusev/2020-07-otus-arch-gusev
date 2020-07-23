FROM openjdk:11-jre-slim
COPY /target/actuator-app-1.0.jar /app/actuator-app.jar
EXPOSE 8000
ENTRYPOINT ["java","-jar","/app/actuator-app.jar"]