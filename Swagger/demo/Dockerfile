# Bắt đầu với image của Eclipse Temurin JDK
FROM eclipse-temurin:21.0.2_13-jdk

# Thiết lập thư mục làm việc trong container
WORKDIR /app

# Sao chép toàn bộ mã nguồn vào thư mục làm việc trong container
COPY . .

# Chạy lệnh Maven để build dự án và tạo tệp JAR
RUN mvn clean install

# Sao chép tệp JAR đã biên dịch vào thư mục /app trong container
COPY swagger/demo/target/demo-0.0.1-SNAPSHOT.jar /app/demo.jar

# Lệnh chạy khi container được khởi động
CMD ["java", "-jar", "demo.jar"]
