#Quyền của user trong linux

##Quyền user với file
- Trong linux, quyền của user liên quan trực tiếp đến việc đọc, ghi và thực thi file, thư mục và quyền sở hữu chúng
* User - group - Others (Mỗi file/thư mục thuộc về):
+ User: người sở hữu file
+ Group: Nhóm mà file thuộc về
+ Others: tất cả những người còn lại. 


##Xem quyền của file: 
```
ls -l 
```
hoặc:
```
ll
```
*Kết quả mẫu '-rw-r--r-- 1 hoang staff  1200 Jan 24 10:00 test.txt'
- Trong đó: 
```
Vị trí		Ký hiệu			Ý nghĩa

1		- 			File thường (nếu là thư mục thì d)

2-4		rw- 			Quyền của User (hoang) 

5-7		r--			Quyền của Group (staff)

8-10 		r--			Quyền của Others
``` 


## Ý nghĩa của các quyền
```
Ký hiệu 	Ý nghĩa trên file 		Ý nghĩa trên thư mục

r 		Đọc nội dung file		Xem danh sách file con 

w		Chỉnh sửa file			Tạo, xoá file trong thư mục

x		Thực thi file 			Truy cập vào thư mục
```


## Thay đổi quyền: Chmod
* Sử dụng số 
```
Số		Quyền 			Nghĩa

7		rwx			Đọc + ghi + thực thi

6 		rw-			Đọc + ghi

5		r-x			Đọc + Thực thi

4		r--			Đọc
```

###Cú pháp thay đổi quyền
```
chmod <Quyền> <file>
```
ex: (cấu hình cho tất cả các quyền)
```
chmod 777 test.sh
```

###Cấp quyền dạng chữ
```
chmod u+x file.txt	#Thêm quyền thực thi cho user

chmod g-w file.txr	#Bỏ quyền ghi của group

chmod o+r file.txt	#Thêm quyền đọc cho others
```


##Đổi chủ sở hữu
*Đổi cả user và group
```
sudo chown <user>:<group> <file>

```
vd: đổi file cho user hoang va group staff
```
sudo chown hoang:staff file.txt
```

*Đổi cả thư mục kèm file con
```
sudo chown -R hoang:staff folder
```

*Chỉ đổi user
```
sudo chown hoang file.txt
```

##Thêm user vào group để nâng quyền
vd: thêm user hoang vào group sudo
```
sudo usermod -aG sudo hoang
```








