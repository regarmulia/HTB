```
SQL injection
```


nmap -sS -sC -sV -T5 -Pn 10.10.10.143

![image](https://user-images.githubusercontent.com/33616880/231966154-8ab1d289-572e-4097-8072-e2a664de70ca.png)



ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.143/FUZZ -fc 403 -e .aspx,.php,.txt,.html

![image](https://user-images.githubusercontent.com/33616880/231966267-6a6058e9-6223-44d8-acd9-72244a55407f.png)



http://10.10.10.143/room.php?cod=2

![image](https://user-images.githubusercontent.com/33616880/231967239-40ac1ae1-c35f-4c56-9740-62bd236b9436.png)



![image](https://user-images.githubusercontent.com/33616880/231967279-462d7629-3f4f-4f75-bff1-b82ba0cfeb7b.png)

![image](https://user-images.githubusercontent.com/33616880/231967320-8aa8e60a-e6b3-4552-882e-0ad264e09771.png)



![image](https://user-images.githubusercontent.com/33616880/231967801-2f5bd5b6-9767-41e1-89f4-82d8f5d4f615.png)
![image](https://user-images.githubusercontent.com/33616880/231967856-7435605f-89d9-4062-aa65-6075b6bfcd58.png)
![image](https://user-images.githubusercontent.com/33616880/231967993-6a81e947-d988-4e23-9042-a8ba3eb2bca0.png)
