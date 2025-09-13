# Thiết lập Cloudflare tunnel trên macos
(sử dụng tunnel để public trực tiếp các service chạy trên máy macos)


### Cài cloudflare tunnel trên máy mac
```
brew install cloudflare/cloudflare/cloudflared
```

### Đăng nhập vào cloudflare
``` 
cloudflare tunnel loggin 
```
=> trang sẽ điều hướng tới cloudflare để login và chọn domain

### Thực hiện tạo mới tunnel
``` 
cloudflared tunnel create tunnel name
```

### Xóa tunnel
``` 
cloudflared tunnel delete <tunnel-id>
```

### Lấy thông tin danh sách tunnel đã tạo
``` 
cloudflared tunnel list
```

### Cấu hình dịch vụ cho tunnel chạy, trong ~/.cloudflared
- mặc định cloudflare sẽ lưu credential của tunnel ở ~/.cloudflared/[tunnel-id].json
- Thực hiện tạo mới file ~/.cloudflare/config.yml với nội dung:
``` 
tunnel: <TUNNEL-ID>
credentials-file: /Users/vuvanhoang/.cloudflared/<TUNNEL-ID>.json

ingress:
  - hostname: app.tenmien.com
    service: http://localhost:3000   # ví dụ Next.js chạy ở port 3000
  - hostname: api.tenmien.com
    service: http://localhost:8080   # ví dụ Spring Boot chạy ở port 8080
  - service: http_status:404
```

### Kết nối tunnel với domain trên cloudflare 
``` 
cloudflared tunnel route dns <tunnel-id> <domain.com>
```
- Nếu lỗi 1003:
``` 
Failed to add route: code: 1003, reason: Failed to create record afood.fun with err An A, AAAA, or CNAME record with that host already exists
```
=> Lỗi này có nghĩa là trong DNS hiện tại đã có 1 record cho domain.com trỏ vào server hoặc tunnel khác

- Cách xử lý: 
  - Thực hiện xóa record A hoặc AAA hoặc CNAME được cấu hình
  - Thực hiện chạy lại lệnh:
```
cloudflared tunnel route dns macmini-tunnel afood.fun
```
=> Cloudflare sẽ tự cấu hình record cho tunnel tương ứng

### Lệnh chạy thử tunnel 
```
cloudflared tunnel run <tunnel name>
```

### Lệnh cho tunnel chạy nền
``` 
cloudflared service install 
```

### Chạy tunnel bằng pm2
``` 
pm2 start "cloudflared tunnel run macmini-tunnel" --name cloudflare-tunnel
pm2 save
pm2 startup
```