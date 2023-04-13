nmap -sS -sC -sV -T5 -Pn 10.10.11.158
![image](https://user-images.githubusercontent.com/33616880/231678963-7c74a0a4-d0d6-4c7a-9dd6-15fa0a3a0f90.png)



https://watch.streamio.htb/
![image](https://user-images.githubusercontent.com/33616880/231679081-ce827ae4-c21b-4073-b1d1-8d9f7ef87bb8.png)



ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://watch.streamio.htb/FUZZ -fc 403 -e .aspx,.php,.txt,.html![image](https://user-images.githubusercontent.com/33616880/231679110-329c5d3d-31d3-47c3-a82c-60f431c2b08a.png)



https://watch.streamio.htb/search.php
![image](https://user-images.githubusercontent.com/33616880/231679168-05ee4b46-32aa-44b9-9dc0-acdac11c53bb.png)
