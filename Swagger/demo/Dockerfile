# Sử dụng image Java temurin
FROM eclipse-temurin:21.0.2_13-jdk

# Thiết lập thư mục làm việc trong container
WORKDIR /app

# Sao chép tệp JAR từ thư mục target vào container
COPY swagger/demo/target/demo-0.0.1-SNAPSHOT.jar /app/demo.jar

# Lệnh chạy khi container được start
CMD ["java", "-jar", "demo.jar"]
