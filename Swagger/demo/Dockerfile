# Bắt đầu từ image Java Temurin
FROM eclipse-temurin:21.0.2_13-jdk

# Thiết lập thư mục làm việc trong container
WORKDIR /app

# Sao chép mã nguồn vào container
COPY . .

# Chạy Maven để build và tạo tệp JAR
RUN mvn clean install

# Sao chép tệp JAR từ thư mục target vào container (đảm bảo tên đúng)
COPY swagger/demo/target/demo-0.0.1-SNAPSHOT.jar /app/demo.jar

# Lệnh chạy khi container được khởi động
CMD ["java", "-jar", "demo.jar"]
