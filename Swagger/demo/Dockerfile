# Giai đoạn build: sử dụng Maven để build ứng dụng
FROM maven:3.9.6-eclipse-temurin-21 AS build
WORKDIR /app
COPY . /app
RUN mvn clean package

# Giai đoạn chạy: Chạy ứng dụng với JDK 21
FROM eclipse-temurin:21.0.2_13-jdk AS run
WORKDIR /app

# Sao chép tệp demo-0.0.1-SNAPSHOT.jar.original vào thư mục /app trong container
COPY swagger/demo/target/demo-0.0.1-SNAPSHOT.jar.original /app/demo.jar

CMD ["java", "-jar", "demo.jar"]
