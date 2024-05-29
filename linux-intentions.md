```
nmap -sS -sC -sV -T5 -Pn 10.10.11.220
```
![image](https://github.com/regarmulia/HTB/assets/33616880/528dff0c-5310-4215-a2d5-7be40b47e7bd)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://intentions.htb/FUZZ -fs 162 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7e5bb805-89c5-4842-a466-280fab8a28f3)

