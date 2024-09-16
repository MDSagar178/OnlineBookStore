FROM maven:3.8.5-openjdk-17 AS build
COPY ..
FROM openjdk:11
RUN mvn clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY -from-build/target/bookstoremanagementsystem-0.0.1-SNAPSHOT.jar bookstoremanagementsystem.jar
EXPOSE 8080
ADD target/bookstore.jar bookstore.jar
ENTRYPOINT ["java", "-jar", "/bookstore.jar"]


