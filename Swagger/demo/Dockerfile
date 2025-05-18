# Stage 1: Build the application using Maven and OpenJDK 21
FROM maven:3-openjdk-21 AS build

# Set working directory to /app
WORKDIR /app

# Copy all files from the current directory to the container
COPY . .

# Run Maven clean and package the application (skip tests for now)
RUN mvn clean package -DskipTests

# Stage 2: Run the application using OpenJDK 17
FROM openjdk:17-jdk-slim

# Set working directory to /app
WORKDIR /app

# Copy the built JAR file from the 'build' stage into this image
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.jar demo.jar

# Expose port 8080 to make the application accessible
EXPOSE 8080

# Set the default command to run the application with 'java -jar'
ENTRYPOINT ["java", "-jar", "demo.jar"]

