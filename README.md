# Kali-tools
How to use kali tools


## NMAP

### Basic scan
```
sudo nmap -vv -sV --script vuln DEST_IP -o nmap.txt
```

Metasploit
----------

#Intialize database 

msfdb init


#Check connection to db

db_status


#Start msf 

msfconsole


#Search module 

search MODULE NAME
  

Hashcat
-------
#Crack MD5 hash with username (username:hash)

hashcat --username -a 0 -m 0 HASHES.TXT WORDLIST


#Show earlier cracked

hashcat --username --show -a 0 -m 1000 HASHES.TXT WORDLIST
  

Gobuster
--------
#Basic directory scan

gobuster dir -o gobuster.txt -u http://DEST_IP/ -w PATH-TO-WORDLIST


Priviledge escalation
--------------------
#Find suid programs

find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null

