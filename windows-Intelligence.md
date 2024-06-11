```
nmap -sS -sC -sV -T5 -Pn 10.10.10.248
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6413486e-f42a-43a5-b969-237d18b6e161)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.248/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/96991ceb-dfba-48ae-a7ad-6399ba07a2ed)

```
wget http://10.10.10.248/documents/2020-01-01-upload.pdf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bdc6e7f4-18d2-448d-95b8-1531c66d373e)
