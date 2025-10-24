#Các lệnh quản lý sau khi tạo mới user



##Đổi mật khẩu
*Đổi mật khẩu cho chính mình:
```
passwd 
```

*Đổi mật khẩu cho user khác (cần quyền sudo)
```
sudo passwd vuvanhoang
```


##Xem danh sách user
```
cat /etc/passwd
```


##Xoá user
*Xoá user giữ lại thư mục home
```
sudo userdel vuvanhoang
```
*Xoá user xoá luôn home
```
sudo userdel -r vuvanhoang
```


##Switch giữa các user
```
su - <another_user>
```


##Khoá user
*Khoá user không cho đăng nhập
```
sudo usermod -L vuvanhoang
``` 
*Mở khoá user
```
sudo usermod -U vuvanhoang
```













