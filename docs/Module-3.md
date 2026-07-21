# Module 03 – Information Gathering and Vulnerability Scanning

## Overview

Perform information gathering and vulnerability scanning activities

---

## Learning Objectives

- Perform passive reconnaissance
- Perform active reconnaissance
- Perform vulnerability scans
- Analyze the results of reconnaissance exercises

---

## Key Learnings

- Reconnaissance in a penetration testing engagement typically consists of scanning and enumeration
- Active reconnaissance is a method of information gathering in which the tools used actually send out probes to the target network or systems in order to elicit responses that are then used to determine the posture of the network or system
- Passive reconnaissance is a method of information gathering in which the tools do not interact directly with the target device or network
- DNS lookups to determine the IP address or addresses used by target and any other subdomains that might be in use
- Dig queries only the A record type and Nslookup queries both the A and AAAA records
- The Host utility is a function in Linux that performs lookups to convert IP addresses to host names
- A company can own a domain and related subdomain, but its applications might be hosted in the cloud
- During the reconnaissance phase, attackers often can inspect Secure Sockets Layer (SSL) certificates to obtain information about the organization, potential cryptographic flaws, and weak implementations
- Certificate revocation is the act of invalidating a digital certificate
- Attackers can leverage password dumps from previous breaches. There are a number of ways that an attacker can get access to such password dumps, such as by using Pastebin, dark web websites, and even GitHub in some cases
- You can obtain a lot of information from metadata in files such as images, Microsoft Word documents, Excel files, PowerPoint files, and more
- What you might not know is that search engines, such as Google, can perform much more powerful searches than most people ever dream of. Google can translate documents, perform news searches, and do image searches
- By using basic search techniques combined with advanced operators, both you and attackers can use Google as a powerful vulnerability search tool
- The Wayback Machine allows you to go back in time on the Internet
- An attacker can obtain extremely valuable information from public source code repositories such as GitHub and GitLab
- Shodan is an organization that scans the Internet 24 hours a day, 365 days a year.
-  The process of gathering this information is called enumeration
-  A port scan is an active scan in which the scanning tool sends various types of probes to the target IP address and then examines the responses to determine whether the service is actually listening
-  A TCP connect scan actually makes use of the underlying operating system’s networking mechanism to establish a full TCP connection with the target device being scanned. This is default scan
-  UDP Scan ( -sU ), With the TCP FIN(-sF) scan, a FIN packet is sent to a target. Not for windows, as it send RST regardless of state of port
- A host discovery scan is one of the most common types of scans used to enumerate hosts on a network because it can use different types of ICMP messages to determine whether a host is online and responding on a network.
-  The default for the -sn scan option is to send an ICMP echo request packet to the target, a TCP SYN to port 443, a TCP ACK to port 80, and an ICMP timestamp request
###  Timing Options ( -T 0-5 )
The Nmap scanner provides six timing templates that can be specified with the -T option and the template number (0 through 5) or name. Nmap timing templates enable you to dictate how aggressive a scan will be, while leaving Nmap to pick the exact timing values. These are the timing options:

-T0 (Paranoid) : Very slow, used for IDS evasion
-T1 (Sneaky) : Quite slow, used for IDS evasion
-T2 (Polite) : Slows down to consume less bandwidth, runs about 10 times slower than the default
-T3 (Normal) : Default, a dynamic timing model based on target responsiveness(default)
-T4 (Aggressive) : Assumes a fast and reliable network and may overwhelm targets
-T5 (Insane) : Very aggressive; will likely overwhelm targets or miss open ports

### Types of Enumeration
-  Host enumeration is performed internally and externally. When performed externally, you typically want to limit the IP addresses you are scanning to just the ones that are part of the scope of the test
-  When you have the username, you can then begin brute-orce attempts to get the account password. You perform user enumeration when you have gained access to the internal network. On a Windows network, you can do this by manipulating the Server Message Block (SMB) protocol, which uses TCP port 445
- SMB_COM_NEGOTIATE: This message allows the client to tell the server what protocols, flags, and options it would like to use. The response from the server is also an SMB_COM_NEGOTIATE message
- Authentication is the primary function of the SMB_COM_SESSION_SETUP_ANDX message. The information sent in this message includes the client username, password, and domain. If this information is not encrypted, it is easy to sniff it right off the network.   nmap --script smb-enum-users.nse <host>
- The Nmap NSE script for enumerating SMB groups is smb-enum-groups. This script attempts to pull a list of groups from a remote Windows machine.
- he Nmap smb-enum-shares NSE script uses Microsoft Remote Procedure Call (MSRPC) for network share enumeration. The syntax of the Nmap smb-enum-shares.nse script is as follows:
nmap --script smb-enum-shares.nse -p 445 <host>
- An easy way to perform additional enumeration and fingerprinting of the applications and operating system running on a host is by using the nmap -sC command.
- You can also use tools such as enum4linux to enumerate Samba shares, including user accounts, shares, and other configurations
- smbclient to enumerate shares and other information from a system running SMB
- The handy Nmap tool actually has an NSE script available for brute forcing the directory and file paths of web applications. Armed with a list of known files and directories used by common web applications, it probes the server for each of the items on the list
- The syntax of the http-enum NSE script is as follows:
nmap -sV --script=http-enum <target>
- Nikto is an open-source web vulnerability scanner that has been around for many years. It’s not as robust as the commercial web vulnerability scanners; however, it is very handy for running a quick script to enumerate information about a web server and the applications it is hosting.
- Service enumeration is the process of identifying the services running on a remote system, and it is a primary focus of what Nmap does as a port scanner
- The Nmap smb-enum-processes NSE script enumerates services on a Windows system, and it does so by using credentials of a user who has access to read the status of services that are running
  nmap --script smb-enum-processes.nse --script-args smbusername=<username>, smbpass=<password> -p445 <host>
- Exploring Enumeration via Packet Crafting
  - Scapy is one of pentesters' favorite tools and frameworks. Scapy is a very comprehensive Python-based framework or ecosystem for packet generation

- As a penetration tester, you can use tools like Wireshark, tshark, and tcpdump to collect packet captures for packet inspection and eavesdropping
---


## Tools Introduced

- Recon-ng
- spiderfoot
- dig
- dnsrecon
- whois
- host
- crt.sh
- sslscan
- h8mail
- Exif
- Google Dorking
- emailharvester
- nmap
- enum4linux, smbclient
- nikto
- Scapy- packet crafter
---

## References

- https://www.kali.org/tools/recon-ng/
- https://github.com/The-Art-of-Hacking/h4cker/tree/master/osint
- https://certificate.transparency.dev/
- WhatBreach: https://github.com/Ekultek/WhatBreach
LeakLooker: https://github.com/woj-ciech/LeakLooker
Buster: https://github.com/sham00n/buster
Scavenger: https://github.com/rndinfosecguy/Scavenger
PwnDB: https://github.com/davidtavarez/pwndb
- "public $user =" | "public $password = " | "public $secret =" | "public $db =" ext:txt | ext:log -git
- intext:JSESSIONID OR intext:PHPSESSID inurl:access.log ext:log
- https://archive.org/web
- https://www.exploit-db.com/google-hacking-database/
- https://tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-20170214-smi
- https://nmap.org/book/man-port-specification.html
- https://nmap.org/book/man-nse.html
- https://github.com/cddmp/enum4linux-ng
