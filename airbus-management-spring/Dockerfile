FROM openjdk:latest
RUN mvn clean
COPY target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app.jar"]

