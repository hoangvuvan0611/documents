###Api tra cứu thông tin các nhân
```
Url: https://daotao.vnua.edu.vn/api/dkmh/w-locsinhvieninfo
method: POST
```

###Api Lấy thông tin lịch học
```
Url: https://daotao.vnua.edu.vn/api/sch/w-locdstkbtuanusertheohocky
method: POST
Input: 
{
	"filter": {
          "hoc_ky": #mahocky,
          "ten_hoc_ky": ""
        },
        "additional": {
          "paging": {"limit": 100, "page": 1},
          "ordering": []
        }
}
```



###Api lấy thông tin lịch thi
```
Url: https://daotao.vnua.edu.vn/api/epm/w-locdslichthisvtheohocky
Method: POST
input: 
{
        "filter": {
          "hoc_ky": #Mahocky,
          "is_giua_ky": false
        },
        "additional": {
          "paging": {"limit": 100, "page": 1},
          "ordering": []
        }
}
```

#Api lấy thông tin điểm
```
Url: https://daotao.vnua.edu.vn/api/srm/w-locdsdiemsinhvien?hien_thi_mon_theo_hkdk=false
Method: POST
```

#APi lấy thông tin học phí
```
Url: https://daotao.vnua.edu.vn/api/rms/w-locdschitiethocphisvtheohocky
Method: POST
input: 
{
	  "filter": {"hoc_ky": #mahocky},
          "additional": {
            "paging": {"limit": 100, "page": 1},
            "ordering": []
          }
}
```

#Api láy thông tin thông báo
```
Url: https://daotao.vnua.edu.vn/api/web/w-locdsbaidang
Method: POST
input: 
{
{"filter":{"ky_hieu":"","is_hien_thi":true,"is_hinh_dai_dien":true,"is_quyen_xem":true},"additional":{"paging":{"limit":200,"page":1},"ordering":[{"name":"do_uu_tien","order_type":1},{"name":"ngay_dang_tin","order_type":1}]}}
}
```





