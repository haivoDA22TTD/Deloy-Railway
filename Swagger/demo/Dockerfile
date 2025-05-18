# Build image with Maven and JDK 21 for building the app
FROM maven:3-openjdk-21 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Final image with JDK 17 for running the app
FROM openjdk:17-jdk-slim
WORKDIR /app
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.jar demo.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "demo.jar"]
