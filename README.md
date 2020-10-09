# Kali-tools
Notes about how to use kali tools. 


## NMAP
Basic scan to file
```
sudo nmap -vv -sV --script vuln <ip> -o nmap.txt
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
hashcat --username --show -a 0 -m 1000 <hash-file> <path-to-wordlist>
```  

Gobuster
--------
Basic directory scan
```
gobuster dir -o gobuster.txt -u <url> -w <path-to-wordlist>
```

Priviledge escalation
--------------------
Find suid programs
```
find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null
```
