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

# PROGRAM:
Find out the ip address of the attackers system
## OUTPUT:
# ![Screenshot 2024-04-20 174135](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/50a6f470-a980-4eea-b2a0-acd7de92854a)

# Invoke msfconsole:
## OUTPUT:
# ![Screenshot 2024-04-20 174251](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/d8d9987f-6cd5-43e1-acbb-9c47a4d34f8d)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

# OUTPUT:


Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

# OUTPUT:
# ![Screenshot 2024-04-20 174450](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/ed59618f-2963-44d6-a412-d9740c2ea31d)

## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.
scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

# OUTPUT:
# ![Screenshot 2024-04-20 174600](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/3c3c81e6-b183-49dc-88ca-550b57f3ddae)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

# OUTPUT:
# ![Screenshot 2024-04-20 174705](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/32b038b8-4532-4e90-9f93-ad51c8680029)
# ![Screenshot 2024-04-20 174747](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/0872b8e3-e644-4b4e-a8e1-a4f71981b7de)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

# ![Screenshot 2024-04-20 174919](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/08e163ff-2d7d-4264-9612-a25a9ff5c8da)

The info command provides information regarding a module or platform

# OUTPUT:
# ![Screenshot 2024-04-20 175040](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/b98ecd8a-90c5-42c9-afad-52907bbe0f53)


Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![Screenshot 2024-04-20 175130](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/918f8123-64df-4915-98da-3a6259a4e5d7)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

# ![Screenshot 2024-04-20 175228](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/dd23d910-b582-4f40-89c7-cdd62457f962)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

# ![Screenshot 2024-04-20 175320](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/20b32d82-6c8c-4018-8560-bf3ce3301824)

Use the set rhosts command to set the parameter and run the module, as follows:

# ![Screenshot 2024-04-20 175407](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/17b0a213-c55e-41bf-8a9c-ccfb9313c84e)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

# ![Screenshot 2024-04-20 175502](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/8c8efd7c-26b4-40a1-952b-f31ab9d30e5c)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
# ![image](https://github.com/DEEPAK22003907/Metasploit-for-reconnaissance/assets/119404520/fafbbdfc-9838-4c09-a55e-594b9de2f47e)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
