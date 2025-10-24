#Thêm mới user và cấp quyền trên hệ điều hành linux 



##Thêm mới user 
```
sudo adduser <new_username>
```
ex: 
```
sudo adduser vuvanhoang
```
###Nếu hệ sử dụng useradd
```
sudo useradd -m -s /bin/bash <new_username>
sudo passwd <password>
```


##Thêm user vào nhóm (add user to group)
```
sudo usermod -aG sudo vuvanhoang
```
*Kiểm tra xem user đang ở group nào:
```
groups vuvanhoang
```















