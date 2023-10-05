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

## PROGRAM:
Find out the ip address of the attackers system


## OUTPUT:

![244913964-1f538f40-f876-4459-8677-8dfbac405ba8](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/8812a518-23f7-42dd-96e9-a273fa11b248)

## Invoke msfconsole:
## OUTPUT:
![244913998-953379bc-27c4-4e87-9702-3316dfb7c3ef](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/e545f5e3-9b74-41f7-92ea-5a777304d213)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![244914049-7f276d8f-8564-47aa-be92-6777dd9474db](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/0d0d00e0-b8de-4857-8028-5d70319df6a2)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![244914060-c0cf7ce9-74cc-4c75-8e07-dd3785c52086](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/3bc823e8-55e2-4a0b-a209-fe1b08a566a5)

 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![244914137-c3e81fb0-1f4d-4243-b8b0-8886a01ee24e](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/6bdec805-cca7-468f-985b-35dc78d2f04c)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![244914146-99aca0dd-3fd0-4380-904c-773475effa74](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/bb190fc2-074c-457e-b306-9fb1d2073017)

![244914149-0cb3f03c-c4c4-4b80-96b7-fdd4b3645f8b](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/cdad6652-196e-44d9-8a36-a721f9ea0950)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![244914160-616d4518-88b6-4b8f-80eb-c0c6e16df08a](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/4aa41d96-b79d-4b47-9908-2fedf278073c)

The info command provides information regarding a module or platform
## OUTPUT:

![244914190-09a5a034-e2b2-4100-a600-2994f2892c99](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/616e5eec-f850-4276-b73e-6a9fbdc2a661)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![244914204-4357ed6f-62a5-4adb-ad5c-fee8dffdfd7b](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/c9b14466-35bc-4881-980a-3f95362e5130)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![244914215-5dd2edca-fd00-45b3-956e-8dd5fe41465a](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/37478ecd-be0e-492b-aa49-33821f62b204)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![244914222-8f9525da-1a5b-4498-8f41-8ef701adb2d9](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/efe321cc-c1d1-4111-8188-89addb276bd0)

Use the set rhosts command to set the parameter and run the module, as follows:

![244914227-57882379-ea28-4349-a3dc-ecea7bb10dea](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/42bc034b-e464-4e11-8d3a-da5c2c5d4f83)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![244914264-7234a9cb-8baf-485c-b743-f6c6250dded8](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/db7a7f18-2620-4a7a-bc46-7d5782e54522)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![244914270-752e39b3-a594-4e46-b60e-1bb7a0ff9d5d](https://github.com/Yogeshvar005/Metasploit-for-reconnaissance/assets/113497367/f0dbd616-d1fc-4b0c-923b-bb112bdcf7b4)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
