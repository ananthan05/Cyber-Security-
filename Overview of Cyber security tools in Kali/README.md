# Types of tools in kali linux

## I.Information gathering tools in kali linux
### 1.NMAP
High-Level Summary
> With Nmap, security professionals can find live hosts on a network and perform port scanning. This app is helpful for many reasons such as identifying open ports which are vulnerable to attack by hackers, or finding the operating system in use so that vulnerabilities may be exploited.

Recommendations
> This Tool is majorly used in port scanning and security audititng

Methodologies
> Its free utility tool available in kali linux

`nmap -sn 10.0.2.0/24`

The nmap -sn 10.0.2.0/24 command is used to perform a ping scan (also known as a "ping sweep") on the specified IP address range(no port scan it helps as to speed up the scan against the network)

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/84e1541d-1712-4f9a-bf2a-d8965267bf9c)

we will be able to find out which all host are up.

`nmap 10.0.2.1`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/6afa0373-e974-4bcc-90ea-555cb8766836)

will be able to understand the port number and the state and service.

`nmap -sV  10.0.2.1`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/64a11ebb-e8da-4288-889d-ed33b711caeb)

will be able to identify the service which is provided to that port.

`sudo nmap -O 10.0.2.1`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/37f4d817-6004-4bc6-9e84-011a65ac10c4)

it used to perform OS fingerprinting on the specified IP address.

`sudo nmap amrita.edu.in -Pn -F -O --osscan-guess`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/3f3e47bf-43de-4f23-8ade-783e7bd119c8)

-Pn: This option skips the host discovery phase. By default, Nmap performs host discovery to determine which hosts are up before scanning. Using -Pn disables this and assumes the target is online.

-F: This option enables a fast scan mode, which scans a reduced number of ports compared to a full scan. It's a quick way to gather basic information about open ports.

-O: This option instructs Nmap to perform OS detection on the target host, attempting to identify the operating system running on the target machine.

--osscan-guess: This option tells Nmap to make an educated guess about the operating system if it cannot determine it with high confidence. It's an additional step to enhance OS detection.

Service Enumeration

> Possible

### 2.Netcat

High-Level Summary
> Netcat functions as a back-end tool that allows for port scanning and port listening. In addition, you can actually transfer files directly through Netcat or use it as a backdoor into other networked systems

Recommendations
> Get Permission:Always get permission before using Netcat on any system or network.

> Use Encryption:Prefer secure protocols like SSH to keep communications encrypted.

> Mind Firewalls:Respect firewall rules on both client and server sides to avoid security alerts.

> Document Activities:Document why and how you're using Netcat, and be aware that activities may be logged.

> Be Careful with Daemons:Avoid running Netcat as a daemon unless necessary, as it can pose security risks.

> Secure File Transfers:Verify sources and destinations when using Netcat for file transfers.

> Limit Listening:Limit Netcat listening to specific IPs or networks instead of all interfaces.

> Keep Software Updated:Keep Netcat updated to fix bugs and address security issues.

> Know Network Ownership:Understand who owns the network and ensure you have the right to test it.

> Educate Team:Educate your team about Netcat's proper usage and potential risks.

> Consider Alternatives:For specific tasks, consider using more secure alternatives like SSH.

Methodologies
> Netcat methodologies include port scanning, listening on ports, file transfer, chat, remote shell, banner grabbing, and custom scripting for targeted tests

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/57f7475a-a0a6-4e42-8851-e964d09079b2)

using netcat tool i was able to listen to the port in the same pc using loopback address.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/1c9dfd96-fcd7-4207-b658-2c7b0f7e6405)

Netcat command flags

Service Enumeration 
> Use Netcat to connect to specific ports on a target machine and gather information about the services running on those ports.

Example:` nc -v target_host target_port`

### 3.Dmitry

High-Level Summary
> Dmitry is a tool that quickly gathers basic information about a website or domain, like who owns it, what servers it uses, and related details, helping security professionals in early stages of investigation.

Recommendations

> Information Gathering Tool through which we can get all basic required information of it

Methodologies

> In Kali Linux only it is pre defined tool which can be used for Information Gathering Scope of this Tool is to scan possible subdomains, email addresses, tcp port scan of a host, lookup on the IP address of a host.

`dmitry -i google.com`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/fb9ea835-3141-4aa5-800e-1232f2608ce2)

When you run this command (dmitry -i google.com), Dmitry will perform various queries and lookups to collect information about the domain "google.com." The gathered information may include WHOIS data, DNS details, network-related information, and more.

`dmitry -w google.com`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/4d7448f4-52d5-4473-ac8e-6c838671de41)

When you run this command (dmitry -w google.com), Dmitry will query the WHOIS database to obtain information about the registration details, such as the domain's owner, registration date, expiration date, and related information for "google.com".

`dmitry -s google.com`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/55df997c-b254-4d79-9714-658221dfc7d4)

When you run this command (dmitry -s google.com), Dmitry will conduct a more extensive analysis, which may include additional domain-related details such as subdomains, network infrastructure, and other relevant information. This goes beyond the basic WHOIS lookup and provides a more in-depth view of the target domain

`dmitry -e amrita.edu`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/94724472-a09a-4473-8e00-75b08f9fdabd)

Perform a search for possible email addresses

Service Enumeration

> By this we can get to know which all are live application running on the system

## II. Vulnerability Analysis Tools in kali linux
 
### 1.Legion (Root)

High-Level Summary
> Legion tool is a super-extensible and semi-automated network penetration testing framework.GUI with panels and a long list of options that allow pentesters to quickly find and exploit attack vectors on hosts. It has the feature of real-time auto-saving of project results and tasks. Legion also provides services like Automatic recon and scanning with NMAP, whataweb, sslyzer, Vulners, webslayer, SMBenum, dirbuster, nikto, Hydra, and almost 100 auto-scheduled scripts are added to it. Modular functionality of Legion Tool allows users to easily customize Legion.

Recommendations
> Automatic detection of CVEs (Common Vulnerabilities and Exposures and CPEs (Common Platform Enumeration).

Methodologies
> Its free utility tool available in kali linux which is GUI Based and also we can customize it.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/22f8ff51-b517-465f-8685-b2dc6e90cd7c)

we can use the ip address or url check the Vulnerability Analysis

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/68705224-8291-4150-b695-0929ec113f8b)

Several tools will be used for information gathering and find out the cVe(Common Vulnerability and exposure of the url or ip address)

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/3404c686-3318-42a0-96d1-e5337a8b725d)
 
ports and protocal and services of the url.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/78046ed1-9be3-4895-a4c2-c2a7507b1d17)

the picture captured by screenshot tool

Service Enumeration
> N.A.

Penetration
> We can get the information of open ports of host and many more options like auto detecting CVE

### 2.Lynis 

High-Level Summary

> Lynis is a security auditing tool for Linux systems, including Kali Linux, that scans for vulnerabilities, provides compliance checks, and offers recommendations for system hardening through detailed reports.

Recommendations
> Regularly run Lynis, address identified vulnerabilities and implement recommended hardening measures to ensure ongoing security compliance on your Linux system.

Methodologies

> Lynis utilizes a combination of methodologies for security auditing, including vulnerability scanning, compliance checks based on industry standards, and the evaluation of system configurations to provide actionable recommendations for system hardening.

`lynis audit system -Q`

The lynis audit system -Q command is used to perform a quick system audit with Lynis, focusing on essential checks. The -Q option stands for "Quick Audit," and it is designed to provide a faster overview of the system's security status with less detailed output compared to a full audit.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ab2f25a9-6dce-4473-aaf8-6540ec8f95ef)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/349848c4-ddee-44ac-9676-9e19cb30ffe2)

we will get know about the program version and many other things.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/86d55d17-719e-473e-920b-1e0304270b88)

 lynis audit system -Q command swiftly assesses and reports on a Linux system's security status, covering aspects such as vulnerability scanning, file permissions, user authentication, malware and rootkits, software package vulnerabilities, logging configurations, network and firewall settings, kernel parameters, running processes and services, security frameworks, service banners, and file integrity, offering concise insights for rapid security checks.

Service Enumeration

> Lynis reveals running services, inspects service banners for version details, checks configurations, and offers recommendations for hardening, providing essential service enumeration insights for penetration testing reports.

### 3.Nikto
High-Level Summary

> Nikto is an open-source web server scanner which performs comprehensive tests against web servers for multiple items. You can use Nikto with any web servers like Apache, Nginx, IHS, OHS, Litespeed, and so on. Nikto can check for server configuration items such as the presence of multiple index files, HTTP server options, and will attempt to identify installed web servers and software. Items and plugins scanned by Nikto are frequently updated and can be automatically updated.

Recommendations
> This Tool is majorly used in port scanning and security audititng

Methodologies

> Nikto employs methodologies such as server identification, directory enumeration, SSL/TLS assessment, CGI vulnerability scanning, and authentication checks to comprehensively analyze web servers, detecting outdated software, known vulnerabilities, and potential security risks for effective security assessments.

`nikto -h amrita.edu`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/4e786393-5359-4040-bd0b-71962ec5dc18)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/e906cfdf-e328-47fa-9a1a-6d7f9967361e)

When you run the command nikto -h amrita.edu, Nikto performs a web server scan on the domain "amrita.edu," conducting various tests to identify potential vulnerabilities, outdated software, misconfigurations, and security risks associated with the web server hosted at that domain. The scan results provide valuable information to assess and improve the security posture of the web server.

`nikto -h goole.com -p 80`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/f06befeb-d640-40be-a138-c0291f60f3b8)

command nikto -h google.com -p 80 instructs Nikto to perform a web server scan on "google.com" specifically targeting port 80. Nikto will analyze the web server on port 80 for potential vulnerabilities, misconfigurations, and security risks, providing a detailed report of its findings.

Service Enumeration
> Nikto performs service enumeration by scanning web servers to identify open ports, extract banners for service identification, and assess configurations, aiding in the discovery of potential vulnerabilities and security risks.

## III. Web Application Analysis Tools in kali linux

### 1.Burp suite

High-Level Summary 
> Burp Suite is a web application security testing tool that acts as a proxy, offers automated scanning for vulnerabilities, and provides various tools for manual testing and analysis, making it a comprehensive solution for identifying and addressing security issues in web applications.

Recommendations
> Regularly update and master the basics of Burp Suite, use extensions wisely, understand your application, blend automation with manual testing, focus on critical areas, review results thoroughly, test ethically, stay informed, and engage with the community for effective web application security testing.

Methodologies
> Proxy: Burp Suite acts as a proxy server between the user's browser and the target web application. It allows the user to intercept and modify the communication between the two, enabling the analysis and manipulation of HTTP requests and responses.
Intruder: Burp Intruder is a powerful tool for performing automated attacks against web applications. It can be used to test the susceptibility of an application to different types of attacks, such as brute force and parameter tampering.
Using the proxy option with intercept turned on, we can intercept the http get request from the user and modify the request according to our need.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/f7fc0979-b83d-4c45-88dc-c607c9d460e1)

Service Enumeration
> 
N.A.

### 2. WPScan-(WordPress Scan)

High-Level Summary
> WordPress is known to have many flaws and vulnerabilities. WPScan will scan the WordPress website for its version, plugins, users and also has an in-built password cracker

Recommendations
> This is used specifically for Websites hosted on WordPress.

Methodologies
> Checking the version of WordPress used and associated vulnerabilities for that version.Checks for database dumps that may be openly accessible.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/c9d231f7-4091-4d61-8639-4326602a485a)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/2df53421-4fea-4dc9-8d7d-293ba0144a55)

Service Enumeration
> N.A.

### 3. WhatWeb

High-Level Summary

> WhatWeb identifies websites. It recognises web technologies including content management systems (CMS), blogging platforms, statistic/analytics packages, JavaScript libraries, web servers, and embedded devices.

Recommendations

> It scans website with aggression level set to 1 -v is for more readablility

Methodologies

> This tool can identify and recognize all the web technologies available on the target website. This tool can identify technologies used by websites such as blogging, content management system, all JavaScript libraries.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/577dcfcc-9734-48fa-a799-bfc498482626)

Service Enumeration

> N.A.

Penetration

> WhatWeb is responsible for grabbing particular information from the target website. Whatweb works as an information-gathering tool and can identify all the email addresses, SQL errors, technology used in the website.

##  IV.Database assessment Tools in kali linux

### 1.Sql Map

High-Level Summary

> Sqlmap is a python based tool; therefore it should operate on any system that supports Python. The purpose of sqlmap is to find and take benefit of SQL injection vulnerabilities in web applications.

Recommendations

> It includes a robust detection engine, numerous specialist features for the ultimate penetration tester, and a wide range of switches that span database fingerprinting, data retrieval from databases, access to the underlying file system, and executing commands on the operating system via out-of-band connections.

Methodologies

> When it detects one or more SQL injections on the target host, the user can choose from a number of options, including performing an extensive back-end database management system fingerprint, retrieving DBMS session user and database, enumerating users, password hashes, privileges, databases, dumping entire or user-specific DBMS table/columns, running his own SQL statement, reading particular files on the file system and more.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/49350751-179d-4f7c-9527-d8d3af8a870c)

Service Enumeration

> N.A.

Penetration

> By giving DBMS credentials, IP address, port, and a database name, it is possible to connect to the database directly without using SQL injection.

##  V.Password Attack Tools in kali linux

### 1. Medussa

High-Level Summary
> Medusa is a modular, speedy, and parallel, login brute-forcer. It is a very powerful and lightweight tool. Medusa tool is used to brute-force credentials in as many protocols as possible which eventually lead to remote code execution. It currently has over 21 modules, some of which are: PcAnywhere, POP3, CVS, FTP etc.

Recommendations

> N.A.

Methodologies

> It works on bruteforce method

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/d8272961-4435-4ebc-b1b3-25df9daf849f)

Service Enumeration

> N.A.

Penetration

> It uses the wordlist which is available on kali linux and apply brute force method

### 2. Crunch
High-Level Summary

> In order to hack a password, we have to try a lot of passwords to get the right one. When an attacker uses thousands or millions of words or character combinations to crack a password there is no surety that any one of those millions of combinations will work or not

Recommendations

> This collection of a different combination of characters is called a wordlist. And in order to crack a password or a hash, we need to have a good wordlist which could break the password. So to do so we have a tool in Kali Linux called crunch.

Methodologies

> crunch is a wordlist generating tool that comes pre-installed with Kali Linux. It is used to generate custom keywords based on wordlists. It generates a wordlist with permutation and combination. We could use some specific patterns and symbols to generate a wordlist.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/46f0be6f-3edf-4b1c-8811-342f736ca3f7)

Service Enumeration

> N.A.

Penetration

> It uses the wordlist which is available on kali linux and apply brute force method

### 3. Hash Finder
High-Level Summary

> As the name is it used to identify the type of hashes that is given as input further based on the hash information we can crack hash using any other tools.

Recommendations

> This collection of a different combination of characters is called a wordlist. And in order to crack a password or a hash, we need to have a good wordlist which could break the password. So to do so we have a tool in Kali Linux called crunch.

Methodologies

> It simply suggests type of hash whether its of MD5 or hash
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/4f661992-b4c1-4e20-b770-7b103c505a90)

Service Enumeration

> N.A.

Penetration

> N.A

## VI.Wireless attacks Tools in kali linux
### 1. Wifite
High-Level Summary

> Wifite is a tool to audit WEP or WPA encrypted wireless networks. It uses aircrack-ng, pyrit, reaver, tshark tools to perform the audit.

Recommendations

> This collection of a different combination of characters is called a wordlist. And in order to crack a password or a hash, we need to have a good wordlist which could break the password. So to do so we have a tool in Kali Linux called crunch.

Methodologies

> When cracking the passwords for multiple networks it sorts them based on their signal strength. Packed with a lot of customizing options to improve the effectiveness of the attack. Changes mac address while attacking to make the

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/0bddbe1e-83c3-4a88-b1b0-cf93fb192f56)

Service Enumeration

> N.A.

Penetration

> N.A

### 2. Revear
High-Level Summary

> Reaver is a package that is a handy and effective tool to implement a brute force attack against Wifi Protected Setup (WPS) registrar PINs to recover WPA/WPA2 passphrases. It is depicted to be a robust and practical attack against WPS, and it has been tested against a wide variety of access points and WPS implementations. In today’s time hacking WPA/WPA2 is exceptionally a tedious job.

Recommendations

> Normal Dictionary attack could take days, and still will not succeed. On average Reaver will take 4-10 hours to recover the target AP’s plain text WPA/WPA2 passphrase, depending on the AP. Generally, it takes around half of this time to guess the correct WPS pin and recover the passphrase.

Methodologies

> First we can scan the available networks with airodump-ng and selected one network and we will take the bssid of that network and we will give the input to the reaver and try to brutteforce the password.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/7a30a7b8-4060-44c4-99af-3b01d3ce46bf)

Service Enumeration

> N.A.

Penetration

> N.A

### 3. Bully
High-Level Summary

> Bully is a new implementation of the WPS brute force attack, written in C. It is conceptually identical to other programs, in that it exploits the (now well known) design flaw in the WPS specification. It has several advantages over the original reaver code. These include fewer dependencies, improved memory and cpu performance, correct handling of endianness, and a more robust set of options.

Reccomendations

> nil

Methodologies

> Bully can be used by security professionals and network administrators to assess the security of wireless networks. Specifically, Bully is designed to exploit vulnerabilities in the WPS (Wi-Fi Protected Setup) feature commonly found in routers. WPS is intended to simplify the process of connecting devices to a Wi-Fi network, but some implementations have been found to have security flaws that can be exploited.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/0908c4f1-d2b3-4de5-8064-ae21626d17ef)

Service Enumeration

> N.A.

Penetration

> N.A

## VII.Reverse Engineering Tools in kali linux
### 1. Nasm
High-Level Summary

> NASM stands for Netwide Assembler. It's a popular assembler for the x86 architecture used in many Unix-like operating systems, including Linux.

Recommendations

> This tool Nasm very useful when we have understand the machine level language and what it does.

Methodologies

> NASM take assembly language code, which is a low-level programming language that closely maps to machine code, and convert it into machine code or object code that a computer's processor can understand and execute.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/5fe52b6b-78fd-4af9-baa9-463b2d5a02a1)

Service Enumeration

> N.A.

Penetration

> N.A

### 2. Radare2
High-Level Summary

> Radare2 is an open-source framework for reverse engineering and binary analysis. It provides a comprehensive set of tools for examining, analyzing, and understanding binary files.

Recommendations

> Radare2 is used by a diverse group of individuals, including security professionals, researchers, and hobbyists. It is particularly useful for reverse engineers, who rely on tools like r2 to understand and analyze code at a low level. This article will introduce you to radare2 and explore its key features and benefits.

Methodologies

> Disassembling and analyzing code, Debugging with Radare2 is also possible
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/1fce5c84-af17-428f-b0e5-2a3d1032ff15)

Service Enumeration

> N.A.

Penetration

> N.A

## VIII.Exploitation tools in kali linux

### 1. Metasploit
High-Level Summary

> Metasploit is an open-source platform that supports vulnerability research, exploit development, and the creation of custom security tools.It contains many exploits and we can get exploit to many well known vulnerabilities. And it also supports some scanners to.

Recommendations

> None

Methodologies

> Metasploit is a powerful and widely used penetration testing framework that assists security professionals in identifying and exploiting vulnerabilities in computer systems. It provides a set of tools, resources, and exploits to test the security of a network or system

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/298fd5eb-7eb1-4b26-8dda-8b19022dfffa)

Service Enumeration

> N.A.

Penetration

> The penetration testing use of Metasploit revolves around simulating real-world cyber attacks in a controlled environment to identify and address vulnerabilities in computer systems, networks, and applications.

### 2. Searchsploit
High-Level Summary

> SearchSploit is a command-line search tool for Exploit-DB that allows you to take a copy of the Exploit Database with you.

Recommendations

> SearchSploit is very useful for security assessments when you don’t have Internet access because it gives you the power to perform detailed offline searches for exploits in the saved Exploit-DB.

Methodologies

> suppose we are taking the vulnerable machine here i.e 192.168.219.129 we get some info about the services that are running on the port here take port 21 so the service running on the port 21 is vsftpd 2.3.4 if try check for the possible exploit in searchsploit we can get the result.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/c80582bb-241e-467c-98f3-676bc8d07bb0)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ab7dc7dd-68b5-45dc-8888-9ffddaa7b895)

Service Enumeration

> N.A.

Penetration

> N.A

## IX.Sniffing and Spoofing Tools in kali linux

### 1. Wireshark
High-Level Summary

> Wireshark is a free and open-source packet analyzer tool used for network troubleshooting, analysis, and communication protocol development and education.

Recommendations

> It captures network traffic from ethernet, Bluetooth, wireless (IEEE.802.11), and frame relay connections, among others, and stores that data for offline analysis.

Methodologies

> This image shows the main page of the wireshark it contains many options for capturing the traffic the we select interface eg eth0 for etherenet we can see that some traffic going through eth0 we can select the interface and start the capture

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/9a8f8465-3db1-4f35-87bb-33b0452b92e0)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/927364bd-49f5-47b1-85ba-4c50c5334318)

Service Enumeration

> N.A.

Penetration

> We can filter as per our requirement which we need.

### 2. TcpDump
High-Level Summary

> This program allows you to dump the traffic on a network. tcpdump is able to examine IPv4, ICMPv4, IPv6, ICMPv6, UDP, TCP, SNMP, AFS BGP, RIP, PIM, DVMRP, IGMP, SMB, OSPF, NFS and many other packet types.

Recommendations

> It can be used to print out the headers of packets on a network interface, filter packets that match a certain expression. You can use this tool to track down network problems, to detect attacks or to monitor network activities.

Methodologies

> we use tcpdump command to run tcpdump -i to specify interface here we are using eth0 interface that is ethernet -v increase the verbosity are make the output more readable.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/3c8df997-97d1-4694-89d2-cb6d2b142125)

Service Enumeration

N.A.

Penetration

N.A.

### 3. Macchanger

High-Level Summary

> GNU MAC Changer is an utility that makes the maniputation of MAC addresses of network interfaces easier. MAC addresses are unique identifiers on networks, they only need to be unique, they can be changed on most network hardware.

Recommendations

> Kali linux comes pre installed with a tool called macchanger which allows us to change mac address on a temporary basis.

Methodologies

> If you have prior experience with Kali Linux then you would understand that eth0 is the name of the system’s networking interface card or NIC.Always remember to specify the name of the interface whenever working with macchanger. Let us now change into a particular mac address,If you observe the help option then you can see that in order to that we need to use the -m argument.Use the help option well if you want to get proficient in using professional tools.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/e4fa672b-3aad-455d-b4ee-a5493b4ff0cb)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/74984b75-a631-4db6-afa4-7fc52702cc94)

Service Enumeration

> N.A.

Penetration

> Sometimes to manipulate the mac address we have to change the device Mac Address

## X.Post Exploitation Tool in kali linux
### 1. Weevely
High-Level Summary

> Weevely is a stealth PHP web shell that simulate telnet-like connection. It is an essential tool for web application post exploitation, and can be used as stealth backdoor or as a web shell to manage legit web accounts, even free hosted ones.

Recommendations

> At the same time it is a feature-rich network debugging and exploration tool, since it can create almost any kind of connection you would need and has several interesting built-in capabilities.

Methodologies

> suppose when generated and ran the payload in the target machine we got the reverse shell using netcat
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/7e8fbf9a-c48e-4262-8167-3171d1836e1e)
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/c7a982f6-5107-4a7d-a520-590f18f331cb)

Service Enumeration

> N.A.

Penetration

> N.A

### 2. Mimikatz
High-Level Summary

> Mimikatz is also capable of assisting in lateral movements and privilege escalations. Attacks like Pass-the-Hash, Pass-the-Ticket, Over-Pass-the-Hash, Kerberoasting etc. can also be achieved with Mimikatz.

Recommendations

> Mimikatz abuses and exploits the Single Sign-On functionality of Windows Authentication that allows the user to authenticate himself only once in order to use various Windows services.

Methodologies

> After a user logs into Windows, a set of credentials is generated and stored in the Local Security Authority Subsystem Service (LSASS) in the memory. As the LSASS is loaded in memory, when invoked mimikatz loads its dynamic link library (dll) into the library from where it can extract the credential hashes and dumps them onto the attacking system, and might even give us cleartext passwords.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/8ab8adca-f036-4746-88d8-f683e6284478)

Service Enumeration

> N.A.

Penetration

> N.A

## XI.Social Engineering Tools in kali linux

### 1. SET(Social Engineering Tool kit)
High-Level Summary

> The Social-Engineer Toolkit (SET) is an open-source Python-driven tool aimed at penetration testing around Social-Engineering.It can be used to perform various social engineering attacks like email phisphing, site phisphing etc.

Recommendations

> The Spear-phishing module allows you to specially craft email messages and send them to your targeted victims with attached FileFormatmalicious payloads. For example, sending malicious PDF document which if the victim opens, it will compromise the system.

Methodologies

> The web attack module is a unique way of utilizing multiple web-based attacks in order to compromise the intended victim. This module is used by performing phishing attacks against the victim if they click the link. There is a wide variety of attacks that can occur once they click a link.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/db36273b-de58-4874-8086-b5ec9b1e248e)

Service Enumeration

> N.A.

Penetration

> N.A

## XII.Forensic Tools in kali linux

### 1. BinWalk
High-Level Summary

> Binwalk is a great tool when we have a binary image and have to extract embedded files and executable codes out of them.

Recommendations

> It is even used to identify the files and codes which are embedded inside the firmware images. Binwalk is compatible with magic signatures for UNIX file utility as it uses libmagic library.

Methodologies

> binwalk supports a variety of command-line options that allow you to customize the analysis and extraction process, such as the signature database to use, the output format, or the extraction options. You can use these options to fine-tune the analysis and extraction to suit your needs.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/31313b05-75a1-4751-8ca9-0dbe2b46438c)
Service Enumeration

N.A.

Penetration

N.A

### 2. Autopsy
High-Level Summary

> Autopsy is a digital forensics tool that is used to gather the information form forensics. Or in other words, this tool is used to investigate files or logs to learn about what exactly was done with the system.

Recommendations

> It could even be used as a recovery software to recover files from a memory card or a pen drive.

Methodologies

> Autopsy comes pre-installed in Kali Linux Just type “autopsy” in the terminal.
![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/f965ccc2-c7d8-4bb0-8fb8-5860ea024632)

Service Enumeration

> N.A.

Penetration

> N.A

## XIII.Reporting Tools in kali linux 

### 1.Cherry tree

High Level summary

> CherryTree is a versatile hierarchical note-taking application with advanced features, including a tree-like organizational structure, rich text editing for formatting, syntax highlighting for code analysis, image embedding for visual elements, hyperlinks for quick access, and robust import/export functionality supporting various formats. Its multilingual support makes it a comprehensive solution for efficient note-taking and report generation, particularly beneficial for developers, security professionals, and diverse users worldwide.


Recommendation

> CherryTree is highly recommended for effective note-taking and report generation, particularly in the context of cybersecurity and penetration testing activities. Its feature-rich environment empowers users to create detailed and well-organized documentation, essential for communicating findings and insights.

> Use Cases

> Penetration Testing Reports: CherryTree proves invaluable in crafting detailed reports for penetration testing, including vulnerability assessments, exploitation details, and remediation recommendations.

> Incident Response Documentation: Security professionals can utilize CherryTree to document incident response activities, keeping a comprehensive record of incidents, actions taken, and lessons learned.

> Knowledge Base Creation: The hierarchical structure and rich text capabilities make CherryTree an excellent tool for building a knowledge base, centralizing information for future reference.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/b7b05b03-a1fe-4a4e-a637-04dd73878690)

Service enumeration

> N/A

### 2.Pipal

High-Level Summary:
> Pipal serves as a password analysis and research tool specifically designed to scrutinize password lists and patterns. It aids in assessing password security, offering valuable insights into common or weak password occurrences.

> Key Features:

> Password Analysis: Pipal is adept at analyzing password lists, providing a comprehensive overview of patterns, trends, and vulnerabilities within the chosen dataset.

> Security Insights: The tool facilitates the identification of common or weak passwords, enabling users to enhance password policies and bolster overall security measures.

> Custom Wordlist Analysis: Pipal is particularly useful for manual creation and analysis of custom wordlists. Security professionals can assess the efficiency of a specific wordlist in uncovering potential vulnerabilities.

> Efficiency Testing: By evaluating the effectiveness of manually created wordlists, Pipal assists in gauging their efficiency in uncovering weak or easily guessable passwords.

Recommendation:
> Pipal is recommended for scenarios where a manual analysis of specific wordlists is required, especially for testing their effectiveness. Utilizing Pipal to analyze, for example, an "sqlmap.txt" file provides valuable insights into the password patterns and characteristics present within that dataset.

> Use Case:
> Analyzing the "sqlmap.txt" file with Pipal allows security professionals to understand the strengths and weaknesses of passwords within that particular context. This information is crucial for refining security strategies and implementing stronger authentication practices.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/6db8eeb8-cc94-43ae-a796-e48096b944d5)

Service enumeration

> N/A

### 3.Cutycapt

High-Level Summary:
> Cutycapt is a compact cross-platform command-line utility designed to capture the rendering of a web page by WebKit. It supports the conversion of web page views into various formats, including SVG, PDF, PS, PNG, JPEG, TIFF, GIF, and BMP.

> Key Features:

> Cross-Platform Utility: Cutycapt operates seamlessly across different platforms, providing a consistent command-line interface for capturing web page renderings.

> Format Compatibility: The utility offers a variety of output formats, including vector formats like SVG, PDF, and PS, as well as bitmap formats such as PNG, JPEG, TIFF, GIF, and BMP.

> Command-Line Operation: Cutycapt is specifically designed for command-line usage, allowing users to capture web page screenshots efficiently without the need for a graphical user interface.

Recommendation:
> Cutycapt is highly recommended for situations where there is a requirement to capture screenshots of web pages directly from the command line. Its versatile output format options make it a convenient tool for users needing flexibility in choosing the format that best suits their needs.

> Use Case:
> In scenarios where automated or scripted web page screenshot capture is necessary, Cutycapt proves invaluable. Its command-line nature allows for integration into scripts and workflows, streamlining the process of generating screenshots in various formats

Service enumeration

> N/A

***




