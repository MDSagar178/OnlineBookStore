FROM maven:3.8.5-openjdk-17 AS build
COPY . /app
WORKDIR /app
RUN mvn clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --from=build /app/target/bookstoremanagementsystem-0.0.1-SNAPSHOT.jar bookstoremanagementsystem.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "bookstoremanagementsystem.jar"]
