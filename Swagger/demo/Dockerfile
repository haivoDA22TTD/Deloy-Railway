# Dùng image Eclipse Temurin làm base image
FROM eclipse-temurin:21.0.2_13-jdk

# Thiết lập thư mục làm việc trong container
WORKDIR /app

# Sao chép file .jar từ thư mục gốc của dự án vào thư mục /app trong container
COPY demo-0.0.1-SNAPSHOT.jar /app/demo.jar

# Lệnh để chạy ứng dụng trong container
CMD ["java", "-jar", "demo.jar"]
