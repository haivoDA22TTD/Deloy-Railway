# Giai đoạn build với Maven + Java 21
FROM maven:3.9.6-eclipse-temurin-21 AS build

WORKDIR /app
COPY Swagger/demo/ /app
RUN mvn clean package -DskipTests

# Giai đoạn chạy với JDK 21
FROM eclipse-temurin:21.0.2_13-jdk AS run
WORKDIR /app
COPY --from=build /app/target/demo.jar /app/demo.jar
CMD ["java", "-jar", "demo.jar"]
