# Giai đoạn build: Maven + Java 21
FROM maven:3.9.6-eclipse-temurin-21 AS build

WORKDIR /app
COPY Swagger/demo/ /app
RUN mvn clean package -DskipTests

# Giai đoạn chạy: Java 21
FROM eclipse-temurin:21-jdk-slim AS run
WORKDIR /app
COPY --from=build /app/target/demo.jar /app/demo.jar
CMD ["java", "-jar", "demo.jar"]


