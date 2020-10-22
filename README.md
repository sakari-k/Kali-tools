# Kali-tools
Notes about how to use kali tools. 


## NMAP
Basic scan to file
```
sudo nmap -sV --script vuln <ip> -o nmap.txt
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
Crack FTP login
``` 
hydra -l <username> -P /usr/share/wordlists/rockyou.txt <ip> <ftp/ssh>
``` 

## Gobuster
Basic directory scan
```
gobuster dir -o gobuster.txt -u <url> -w <path-to-wordlist>
```

## Priviledge escalation
Find suid programs
```
find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null
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
