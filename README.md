# Kali-tools
Notes about how to use kali tools. 


## NMAP
Basic scan to file
```
sudo nmap -sV --script vuln <ip> -o nmap.txt
```

Fast scan
```
nmap -F <ip>
```


## Nessus
Start
```
/bin/systemctl start nessusd.service
```

Web UI
```
https://localhost:8834/
```


## Metasploit
Intialize database 
```
msfdb init
```

Check connection to db
```
db_status
```

Start msf 
```
msfconsole
```

Set RHOSTS globally
```
setg RHOSTS <ip>
```

Search module 
```
search <module>
```  

## Hashcat
Crack MD5 hash with username (username: hash)
```
hashcat --username -a 0 -m 0 <hash-file> <path-to-wordlist>
```

Show earlier cracked
```
hashcat --username --show -a 0 -m 0 <hash-file> <path-to-wordlist>
```  

## John the ripper
Crack hash
```
sudo john <hash-file>
```  

Show earlier cracked
```
sudo john --show <hash-file>
```  

## Hydra
Crack FTP/SSH login
``` 
hydra -l <username> -P /usr/share/wordlists/rockyou.txt <ip> <ftp/ssh>
```
Crack Post Web Form
``` 
hydra -l <user> -P /usr/share/wordlists/rockyou.txt <ip> http-post-form "/<login url>:username=^USER^&password=^PASS^&Login=Login:<error message>" -V
``` 
HTTP basic auth (pop up)
``` 
hydra -l <user> -P /usr/share/wordlists/rockyou.txt -s <port> -f <ip> http-get /<page>
``` 

## Nikto
Scan server with credentials
```
nikto -h http://10.10.21.122:1234/manager/html -id bob:bubbles
```

## Gobuster
Basic directory scan
```
gobuster dir -o gobuster.txt -u <url> -w <path-to-wordlist> -x php,sh,txt,cgi,html,css,js,py
```

## Steghide
extract data from image
```
steghide --extract -sf <file>
```

## Priviledge escalation
Find suid programs
```
find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null
```
List programs that could be run as root for current user
```
sudo -l
```


## Tips and tricks
shell stabilization
```
python3 -c 'import pty;pty.spawn("/bin/bash")'
```
```
export TERM=xterm
```
```
Ctrl + Z
```
```
stty raw -echo; fg
```


## Ftp
Login
```
ftp <ip>
```

Get file
```
get <file>
```




## MYSQL
Login to local database
```
mysql -u<USERNAME> -p
```

Available databases
```
show databases;
```

Enter database
```
use DATABASE;
```

List tables
```
show tables;
```

Dump table content
```
SELECT * FROM <TABLE NAME>;
```
