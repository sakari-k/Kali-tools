# Kali-tools
How to use kali tools


NMAP
----
#Basic scan

sudo nmap -vv -sV -O --script vuln <ip>

Metasploit
----------

#Intialize database 

msfdb init


#Check connection to db

db_status


#Start msf 

msfconsole


#Search module 

search <module name>
  

Hashcat
-------
#Crack NTLM hash with username (username:hash)

hashcat --username -a 0 -m 1000 <hashes.txt> <wordlist>


#Show earlier cracked

hashcat --username --show -a 0 -m 1000 <hashes.txt> <wordlist>
  

Gobuster
--------
#Basic directory scan

gobuster dir -o gobuster.txt http://<ip>/ -w <path-to-wordlist>
