# Module 03 – Information Gathering and Vulnerability Scanning

## Overview

Perform information gathering and vulnerability scanning activities

---

## Learning Objectives

- Perform passive reconnaissance
- Perform active reconnaissance
- Perform vulnerability scans
- Analyze the results of reconnaissance exercises
- 
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
- 
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
