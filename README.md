# Kali-tools
How to use kali tools


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
# Crack NTLM hash with username (username:hash)
hashcat --username -a 0 -m 1000 <hashes.txt> <wordlist>

# Show earlier cracked
hashcat --username --show -a 0 -m 1000 <hashes.txt> <wordlist>
