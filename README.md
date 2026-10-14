# Campus Hub — Dockerize Backend + MySQ

Bài kiểm tra: đóng gói backend Campus Hub thành Docker Image và chạy cùng MySQL bằng Docker Compose.

## Công nghệ
- Spring Boot 3.5.7, Java 21, Gradle
- MySQL 8.0
- Health check: Spring Boot Actuator

## Lệnh chạy hệ thống

```bash
# 1. Chạy test backend
cd backend
./gradlew test

# 2. Build JAR và Docker image cho backend
./gradlew clean bootJar -x test
docker build -t campus-hub-backend .

# 3. Chạy toàn bộ hệ thống (từ thư mục gốc repo)
cd ..
docker compose up -d --build

# 4. Kiểm tra trạng thái
docker compose ps
