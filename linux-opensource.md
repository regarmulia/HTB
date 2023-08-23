```
nmap -sS -sC -sV -T5 -Pn 10.10.11.164
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bd23ea8e-8d62-47e6-b5dc-85b954b967a3)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.164/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5795739c-4a17-4504-8488-d1ace66b3196)
