FROM maven:3.8.5-openjdk-17 AS build
RUN mvn clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --from-build /target/bookstoremanagementsystem-0.0.1-SNAPSHOT.jar bookstoremanagementsystem.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "bookstore.jar"]


