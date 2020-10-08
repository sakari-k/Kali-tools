# Kali-tools
How to use kali tools


NMAP
----
#Basic scan

sudo nmap -vv -sV --script vuln DEST_IP -o FILE_NAME


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
#Crack NTLM hash with username (username:hash)

hashcat --username -a 0 -m 1000 HASHES.TXT WORDLIST


#Show earlier cracked

hashcat --username --show -a 0 -m 1000 HASHES.TXT WORDLIST
  

Gobuster
--------
#Basic directory scan

gobuster dir -o gobuster.txt -u http://DEST_IP/ -w PATH-TO-WORDLIST
