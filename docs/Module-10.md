# Module 10 - Tools and Code analysis

## Overview

- Basic concepts of scripting and software developement
- different use case of tools
---

## Key Learnings:

### Scripting and Code analysis

- Programming logic constructs are the building blocks that include the sequence or order in which instructions occur and are processed, the path a program takes when it is running, and the iteration (or repeated execution) of a section of code
#### The most commonly used data structures in programming languages:
- JSON is a lightweight format for storing and transporting data that is easy to understand. It is the most common data structure in RESTful APIs and many other implementations
- An array is a special variable that holds more than one value at a time
- A dictionary is a collection of data values that are ordered using a key/value pair
- A CSV file is a plaintext file that contains data delimited by commas (,) and sometimes tabs or other characters, like semicolons (;)
- A list is a data structure in programming languages that contains an ordered structure of elements
- A tree is a non-linear data structure represented using nodes in a hierarchical model

- A library is a collection of resources that can be reused by programs
- Libraries contain Prewritten code, Configuration information, Subroutines, Documentation and help information, Message templates, Classes.
- A procedure is a section of code that is created to perform a specific task. A procedure can be used several times throughout a program. Procedures can make code simpler and more concise
- Functions and procedures are very similar. In some programming languages, functions and procedures are practically the same thing
- A function is a block of code that is very useful when you need to execute similar tasks over and over. A function runs only when it is called
- A class is a code template that can be used to create different objects. It provides initial values for member variables and functions or methods
- Bash is a command shell and language interpreter that is available for operating systems such as Linux, macOS, and even Windows
- A shell is a command-line tool that allows for interactive or non-interactive command execution
- Ruby is another programming language that is used in many web and other types of applications
- The first line in the Bash script is a special kind of comment line that indicates the location of the interpreter to be used to run the code. This line is called a "shebang" and is common to most Linux scripts

### Tools

- ​​​​​​​Tools for Reconnaissance: nslookup, Host, Dig, whois, Exif, theHarvester, Shodan, Maltego, Recon-ng, censys, enum4linux
- Fingerprinting Organization with Collected Archives (FOCA) is a tool designed to find metadata and hidden information in documents. FOCA can analyze websites as well as Microsoft Office, Open Office, PDF, and other documents
- Tools for vulnerability scanning: OpenVAS, Nessus, Nexpose, Qualys, SQLmap, Nikto, OWASP ZedAttack Proxy (ZAP), w3af, DirBuster, Brakeman, Open Security Content Automation Protocol (SCAP) scanners, Wapiti, Scout Suite, WPScan (Wordpress scanner)
- Common tools for credential attacks: John the Ripper, Cain and Abel, Hashcat, Hydra, RainbowCrack, Medusa and Ncrack, CeWL, Mimikatz, Patator
- There is a GUI version of John the Ripper called Johnny
- Cain (or Cain and Abel) is a tool that can be used to “recover” passwords of Windows-based systems. Cain and Abel can be used to decipher and recover user credentials by performing packet captures (sniffing); cracking encrypted passwords by using dictionary, brute-force, and cryptanalysis attacks; and using many other techniques
- Attackers can use rainbow tables – precomputed tables for reversing cryptographic hash functions – to accelerate password cracking. It is possible to use a rainbow table to derive a password by looking at the hashed value
- Medusa a tool used to perform brute-force credential attacks against various
- Mimikatz is a post exploittation tool that can retrive passwords from the memory of a compromised host
- Patator has several stratrgies for enumerating SMTP usernames and can then be used to brute force the passwords that are associated with those users
- Common protocols for Persistence: Microsoft’s Remote Desktop Protocol (RDP), Apple Remote Desktop, VNC, X server forwarding 
- PowerSploit is a collection of PowerShell modules that can be used for post- exploitation and other phases of an assessment
- Empire is a PowerShell-based post-exploitation framework that is very popular among pen testers
- Evasion techniques are methods used by attackers to bypass security defenses like firewalls, intrusion detection systems (IDS), and antivirus software to deliver malware or maintain access without detection
- Several tools and techniques can be used for evasion, including the following: Veil, Tor, Proxychains, Encryption, Encapsulation and tunneling using DNS and protocols such as NTP
- Veil is a framework that can be used with Metasploit to evade antivirus checks and other security controls
- Tor is a free tool that enables its users to surf the Web anonymously. Tor works by “routing” IP traffic through a free worldwide network consisting of thousands of Tor relays
- Proxychains can be used for evasion, as it is a tool that forces any TCP connection made by a specified application to use Tor or any other SOCKS4, SOCKS5, HTTP, or HTTPS proxy
- Tools for DNS tunneling; DeNise, dns2tcp, DNScapy, DNScat, DNScat2, Heyoka, iodine, sods, psudp, Feederbot 
- Exploitation frameworsks: Metasploit, BeEF
- 
---

## References

- https://www.w3schools.com/whatis/whatis_json.asp
- https://www.educative.io/edpresso/binary-trees-in-python
- https://www.advanced-ict.info/programming/functions.html
- https://www.advanced-ict.info/programming/functions.html
- https://linuxize.com/post/bash-functions/
- https://devhints.io/bash
- https://www.perltutorial.org/
- https://www.ruby-lang.org/en/documentation/quickstart/
- https://github.com/ElevenPaths/FOCA
- https://www.owasp.org/index.php/Category:Vulnerability_Scanning_Tools
- https://www.openwall.com/wordlists
- https://github.com/berzerk0/Probable-Wordlists
- https://sectools.org/tool/cain/
- https://github.com/haad/proxychains
- https://github.com/rapid7/metasploit-framework/tree/master/scripts/meterpreter
