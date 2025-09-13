# Thực hiện cài java trên máy macos

### Lệnh kiểm tra java
``` 
java --version
```
hoặc
``` 
which java
```

### Xem các phiên bản java hiện có
``` 
brew search openjdk
```

### Lệnh cài java version 21
``` 
brew install openjdk@21
```

### Thiết lập path cho java (JAVA_HOME)
``` 
echo 'export PATH="/opt/homebrew/opt/openjdk@21/bin:$PATH"' >> ~/.zshrc
echo 'export JAVA_HOME="/opt/homebrew/opt/openjdk@21"' >> ~/.zshrc
source ~/.zshrc
```

### Cấu hình maven sử dụng java 21
- Kiểm tra phiên bản mvn đang sử dụng
``` 
mvn -version
```
- Nếu chưa có maven, thực hiện cài maven
``` 
brew install maven
```
- Thiết lập java home
``` 
echo 'export PATH="/opt/homebrew/opt/openjdk@21/bin:$PATH"' >> ~/.zshrc
echo 'export JAVA_HOME="/opt/homebrew/opt/openjdk@21"' >> ~/.zshrc
source ~/.zshrc
```

### Kiểm tra các phiên bản java có trên máy
``` 
/usr/libexec/java_home -V
```
