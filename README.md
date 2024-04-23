# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

# PROGRAM

Find out the ip address of the attackers system

## EXECUTION STEPS AND ITS OUTPUT

## OUTPUT:

![Screenshot 2024-04-23 091355](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/9e572cb8-bc4c-4554-a995-def36fcdca3a)


### Invoke msfconsole:

## OUTPUT:

![image](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/3c40eb1a-5b52-4c74-9103-6643e603ee6d)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:

![Screenshot 2024-04-23 091605](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/20005e1a-8f28-491a-9ed0-5966f6c09470)


Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![Screenshot 2024-04-23 091701](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/6902de2c-0f65-4d37-a70a-5eee4db178de)


### Step 4: 

Use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

![Screenshot 2024-04-23 091746](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/462712d6-1bcb-408e-9f06-d7ca8dfa8e6d)


Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![Screenshot 2024-04-23 091957](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/8a873b63-9c4e-4996-9bc3-ac72bff5c99f)

![Screenshot 2024-04-23 092045](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/3e402263-e875-4c1d-bba3-e64866bb53ba)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![Screenshot 2024-04-23 092139](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/88920d92-c94f-427e-93d0-13b2718fd0dc)


The info command provides information regarding a module or platform

## OUTPUT:

![Screenshot 2024-04-23 092254](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/3c5f8ce7-1191-4189-bd59-7240b1d5f547)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![Screenshot 2024-04-23 092337](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/fcf0b734-8719-43ae-9721-d525439763ae)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![Screenshot 2024-04-23 092430](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/7620a58b-ee26-45fb-a126-024b2aea8063)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![Screenshot 2024-04-23 092535](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/855071d7-57b5-46fe-a15b-6e37cb33a915)

Use the set rhosts command to set the parameter and run the module, as follows:

![Screenshot 2024-04-23 092701](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/a864226b-4d4b-46f9-a190-ef21b66398d1)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![Screenshot 2024-04-23 092752](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/99ee7696-a5e7-404e-946b-eeecf4e4dbd1)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![Screenshot 2024-04-23 092900](https://github.com/sathyaa22/Metasploit-for-reconnaissance/assets/140483368/d47e8fb0-f77a-4dbb-b92a-c04b9a39a181)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
