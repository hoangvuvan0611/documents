# Thiết lập chạy project springboot trên server

### Chạy với lệnh build
``` 
./mvnw clean package -DskipTests
```
hoặc nếu máy cài maven
``` 
mvn clean package -DskipTests
```

## Thực hiện chạy lệnh với java'

### Lệnh chạy với PM2:
- Không cấu hình profile
``` 
pm2 start "java -jar target/<app.jar> --server.port=8080" --name springboot
```
