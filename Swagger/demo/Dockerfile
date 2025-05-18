# Build image with Maven and JDK 21 for building the app
FROM maven:3-openjdk-21 AS build
WORKDIR /app
COPY . .  # Sao chép tất cả mã nguồn vào container
RUN mvn clean package -DskipTests  # Build ứng dụng với Maven, bỏ qua kiểm thử

# Final image with JDK 17 for running the app
FROM openjdk:17-jdk-slim
WORKDIR /app
COPY --from=build /app/target/demo-0.0.1-SNAPSHOT.jar demo.jar  # Sao chép tệp JAR từ bước build
EXPOSE 8080  # Mở cổng 8080 cho ứng dụng
ENTRYPOINT ["java", "-jar", "demo.jar"]  # Khởi động ứng dụng Spring Boot với `java -jar`
