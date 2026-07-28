# Module 05 – Exploiting Wired and Wireless Networks

## Overview

Explain how to exploit wired and wireless network vulnerabilities

---

## Key Learnings:

### Windows Name Resolution and SMB Attacks
- NetBIOS and LLMNR are protocols that are used primarily by Microsoft Windows for host identification
- LLMNR, which is based on the DNS protocol format, allows hosts on the same local link to perform name resolution for other hosts
- NetBIOS provides three different services:

NetBIOS Name Service (NetBIOS-NS) for name registration and resolution
Datagram Service (NetBIOS-DGM) for connectionless communication
Session Service (NetBIOS-SSN) for connection-oriented communication

- NetBIOS-related operations use the following ports and protocols:

TCP port 135: Microsoft Remote Procedure Call (MS-RPC) endpoint mapper, used for client-to-client and server-to-client communication
UDP port 137: NetBIOS Name Service
UDP port 138: NetBIOS Datagram Service
TCP port 139: NetBIOS Session Service
TCP port 445: SMB protocol, used for sharing files between different operating systems, including Windows and Unix-based systems

- In Windows, a WORKGROUP is a local area network (LAN) peer-to-peer network that can support a maximum of 10 hosts in the same subnet. A workgroup has no centralized administration
- A domain-based implementation, on the other hand, is a client-to-server network that can support thousands of hosts that are geographically dispersed across many subnets
- A user with an account on the domain can log on to any computer system without having an account on that computer. It does this by authenticating to a domain controller
- One of the common mitigations for these types of attacks is to disable LLMNR and NetBIOS in local computer security settings or to configure a group policy
- Successful exploitation of EternalBlue allows an unauthenticated remote attacker to compromise an affected system and execute arbitrary code. This exploit has been used in ransomware such as WannaCry and Nyeta
- To determine the exact location of any exploit, you can use the search command in Metasploit
- You can use tools such as Nmap and Enum4linux to gather information about vulnerable SMB systems and then use tools such as Metasploit to exploit known vulnerabilities
- A Relative Identifier (RID) is a no. that Uniquely identifies a user, group, system, or domain.
- Security Identifier (SID) Uniquely identifies users and groups within the local domain. Globally unique so can also work between domains.
- Domain controller is a server that manages network and identity security requests. It authenticates users and determines whether the users are allowed to access IT resources in the domain
- Lightweight Directory Access Protocol (LDAP) is a a directory access protocol that enables services and clients that use LDAP naming services to communicate 
- Smbclient is a component of Samba that can store and retrieve files, similar to an FTP client

### DNS Cache Poisoning
- DNS cache poisoning involves the manipulation of the DNS resolver cache through the injection of corrupted DNS data

### SNMP Exploits
- Simple Network Management Protocol (SNMP) is a protocol that many individuals and organizations use to manage network devices. SNMP uses UDP port 161. In SNMP implementations, every network device contains an SNMP agent that connects with an independent SNMP server (also known as the SNMP manager)
- An administrator can use SNMP to obtain health information and the configuration of a networking device, to change the configuration and to perform other administrative tasks
- The managed device information is kept in a database called the Management Information Base (MIB)
- The two most popular versions today are SNMPv2c and SNMPv3. SNMPv2c uses community strings, which are passwords that are applied to a networking device to allow an administrator to restrict access to the device in two ways: by providing read-only or read/write access.
- SNMPv3 uses usernames and passwords and it is more secure than all previous SNMP versions
-  A more modern and security implementation involves using NETCONF with newer infrastructure devices

### SMTP Exploits
- Attackers may leverage insecure SMTP servers to send spam and conduct phishing and other email-based attacks. 
- SMTP is a server-to-server protocol, which is different from client/server protocols such as POP3 or IMAP
- SMTP open relay is the term used for an email server that accepts and relays (that is, sends) emails from any user. It is possible to abuse these configurations to send spoofed emails, spam, phishing, and other email-related scams

### FTP Exploits
- Recommended practice dictates that you implement a more secure alternative, such as File Transfer Protocol Secure (FTPS) or Secure File Transfer Protocol (SFTP)
- SFTP uses SSH, and FTPS uses FTP over TLS. Best practice calls for disabling weak hashing protocols such as MD5 or SHA-1 and using stronger algorithms in the SHA-2 family (such as SHA-2 or SHA-512)

### Pass The Hash Attacks
- All versions of Windows store passwords as hashes in a file called the Security Accounts Manager (SAM) file. The operating system does not know what the actual password is because it stores only a hash of the password
- Microsoft also has a suite of security protocols for authentication, called this New Technology LAN Manager (NTLM)
- Microsoft has used Kerberos in Windows domains. However, NTLM may still be used when the client is authenticating to a server via IP address or if a client is authenticating to a server in a different Active Directory (AD) forest configured for NTLM trust instead of a transitive inter-forest trust
- The Windows operating system and Windows applications ask users to enter their passwords when they log in. The system then converts the passwords into hashes (in most cases, using an API called LsaLogonUser). A pass-the-hash attack goes around this process and just sends the hash to the system to authenticate

### Kerberos and LDAP-Based Attacks
- Kerberos is an authentication protocol defined in RFC 4120 that has been used by Windows for a number of years. Kerberos is also used by numerous applications and other operating systems
- contains three basic elements:
Client
Server
Key distribution center (KDC), including the authentication server and the ticket-granting server
- The following steps are illustrated in Figure 5-4:

Step 1. The client sends a request to the authentication server within the KDC.

Step 2. The authentication server sends a session key and a ticket-granting ticket (TGT) that is used to verify the client’s identity.

Step 3. The client sends the TGT to the ticket-granting server.

Step 4. The ticket-granting server generates and sends a ticket to the client.

Step 5. The client presents the ticket to the server.

Step 6. The server grants access to the client.

- Active Directory uses Lightweight Directory Access Protocol (LDAP) as an access protocol. The Windows LDAP implementation supports Kerberos authentication
- LDAP uses an inverted-tree hierarchical structure called the Directory Information Tree (DIT). In LDAP, every entry has a defined position. The Distinguished Name (DN) represents the full path of the entry
- If the system is connected to a domain, the attacker can identify a Kerberos TGT (KRBTGT) password hash to get the golden ticket
- Silver tickets are forged service tickets for a given service on a particular server
- The Windows Common Internet File System (CIFS) allows you to access files on a particular server, and the HOST service allows you to execute schtasks.exe or Windows Management Instrumentation (WMI) on a given server
- In order to create a silver ticket, you need the system account (ending in $), the security identifier (SID) for the domain, the fully qualified domain name, and the given service
- Kerberos delegation is a feature that allows an application to reuse the end-user credentials to access resources hosted on a different server
- Kerberos delegation is therefore not enabled by default in Active Directory
- Kerberoasting is a post-exploitation activity that is used by an attacker to extract service account credential hashes from Active Directory for offline cracking
- It is a pervasive attack that exploits a combination of weak encryption implementations and improper password practices

### On-Path Attacks
- On-path attack (previously known as a man-in-the-middle [MITM] attack), an attacker places himself or herself in-line between two devices or individuals that are communicating in order to eavesdrop (that is, steal sensitive data) or manipulate the data being transferred (such as by performing data corruption or data modification)
- An ARP spoofing attack can target hosts, switches, and routers connected to a Layer 2 network by poisoning the ARP caches of systems connected to the subnet and intercepting traffic intended for other hosts on the subnet
- Media Access Control (MAC) spoofing is an attack in which a threat actor impersonates the MAC address of another device (typically an infrastructure device such as a router). The MAC address is typically a hard-coded address on a network interface controller
- A common mitigation for ARP cache poisoning attacks is to use Dynamic Address Resolution Protocol (ARP) Inspection (DAI) on switches to prevent spoofing of the Layer 2 addresses
- An attacker can carry out an on-path attack at Layer 3 by placing a rogue router on the network and then tricking the other routers into believing that this new router has a better path than other routers
- An attack tool called SSLStrip uses on-path functionality to transparently look at HTTPS traffic, hijack it, and return non-encrypted HTTP links to the user in response
- In a downgrade attack, an attacker forces a system to favor a weak encryption protocol or hashing algorithm that may be susceptible to other vulnerabilities

### Route Manipulation Attacks
- Border Gateway Protocol (BGP) is a dynamic routing protocol used to route Internet traffic
- An attacker can launch a BGP hijacking attack by configuring or compromising an edge router to announce prefixes that have not been assigned to his or her organization
- If the malicious announcement contains a route that is more specific than the legitimate advertisement or that presents a shorter path, the victim’s traffic could be redirected to the attacker. In the past, threat actors have leveraged unused prefixes for BGP hijacking in order to avoid attention from the legitimate user or organization
### DoS and DDoS Attacks
- DoS attacks can generally be divided into three categories, described in the following sections:

Direct- A direct DoS attack occurs when the source of the attack generates the packets, regardless of protocol, application, and so on, that are sent directly to the victim of the attack
Botnet-  A _botnet _is a collection of compromised machines that the attacker can manipulate from a command and control (CnC, or C2) system to participate in a DDoS attack, send spam emails, and perform other illicit activities
Reflected- With reflected DoS and DDoS attacks, attackers send to sources spoofed packets that appear to be from the victim, and then the sources become unwitting participants in the reflected attack by sending the response traffic back to the intended victim
Amplification- An amplification attack is a form of reflected DoS attack in which the response traffic (sent by the unwitting participant) is made up of packets that are much larger than those that were initially sent by the attacker (spoofing the victim)

### Network Access Control (NAC) Bypass
- NAC is a technology that is designed to interrogate endpoints before joining a wired or wireless network. It is typically used in conjunction with 802.1X for identity management and enforcement
- NAC implementations can allow specific nodes such as printers, IP phones, and video conferencing equipment to join the network by using an allow list (or whitelist) of MAC addresses corresponding to such devices. This process is known as MAC authentication (auth) bypass
- The network administrator can preconfigure or manually change these access levels
- An attacker could easily spoof an authorized MAC address (in a process called MAC address spoofing ) and bypass a NAC configuration

### VLAN Hopping
- A virtual LAN (VLAN) is another name for a Layer 2 broadcast domain. A VLAN is controlled by a switch. The switch also controls which ports are associated with which VLANs
- Dynamic Host Configuration Protocol (DHCP) is used to assign IP addresses from a common subnet range to the devices in a given VLAN
- Virtual local area network (VLAN) hopping is a method of gaining access to traffic on other VLANs that would normally not be accessible. There are two primary methods of VLAN hopping: switch spoofing and double tagging
- When you perform a switch spoofing attack, you imitate a trunking switch by sending the respective VLAN tag and the specific trunking protocols
- Another 802.1Q VLAN hopping attack is a double-tagging VLAN hopping attack. Most switches configured for 802.1Q remove only one 802.1Q tag. An attacker could change the original 802.1Q frame to add two VLAN tags: an outer tag with his or her own VLAN and an inner hidden tag of the victim’s VLAN

### DHCP Starvation Attacks and Rogue DHCP Servers
- The two most popular attacks against DHCP servers and infrastructure are DHCP starvation and DHCP spoofing (which involves rogue DHCP servers)
-  In a DHCP starvation attack, an attacker broadcasts a large number of DHCP REQUEST messages with spoofed source MAC addresses
-  If the DHCP server responds to all these fake DHCP REQUEST messages, available IP addresses in the DHCP server scope are depleted within a few minutes or seconds. After the available number of IP addresses in the DHCP server is depleted, the attacker can then set up a rogue DHCP server and respond to new DHCP requests from network DHCP clients
-  The attacker can set the IP address of the default gateway and DNS server to itself so that it can intercept the traffic from the network hosts

## Wireless Vulnerabilities

### Rogue Access Points
- One of the most simplistic wireless attacks involves an attacker installing a rogue AP in a network to fool users to connect to that AP. Basically, the attacker can use that rogue AP to create a backdoor and obtain access to the network

### Evil Twin Attacks
- In an evil twin attack, the attacker creates a rogue access point and configures it exactly the same as the existing corporate network
- The attacker uses DNS spoofing to redirect the victim to a cloned captive portal or a website. When users are logged on to the evil twin, a hacker can easily inject a spoofed DNS record into the DNS cache, changing the DNS record for all users on the fake network
- Any user who logs in to the evil twin will be redirected by the spoofed DNS record injected into the cache

### Disassociation (or Deauthentication) Attacks
- An attacker can cause legitimate wireless clients to deauthenticate from legitimate wireless APs or wireless routers to either perform a DoS condition or to make those clients connect to an evil twin. This type of attack is also known as a disassociation attack
- The attacker disassociates (tries to disconnect) the user from the authenticating wireless AP and then carries out another attack to obtain the user’s valid credentials
- A service set identifier (SSID) is the name or identifier associated with an 802.11 wireless local area network (WLAN). SSID names are included in plaintext in many wireless packets and beacons
- You can use the Airodump-ng tool to sniff wireless networks and obtain their SSIDs, along with the channels they are operating

###  Preferred Network List Attacks
- Operating systems and wireless supplicants (clients), in many cases, maintain a list of trusted or preferred wireless networks. This is also referred to as the preferred network list (PNL)
-  PNL includes the wireless network SSID, plaintext passwords, or WEP or WPA passwords
- It is possible for attackers to listen to these client requests and impersonate the wireless networks in order to make the clients connect to the attackers’ wireless devices and eavesdrop on their conversation or
manipulate their communication.

### Wireless Signal Jamming and Interference
- The purpose of jamming wireless signals or causing wireless network interference is to create a full or partial DoS condition in the wireless network
- In order to jam a Wi-Fi signal or any other type of radio communication, an attacker basically generates random noise on the frequencies that wireless networks use
- With the appropriate tools and wireless adapters that support packet injection, an attacker can cause legitimate clients to disconnect from wireless infrastructure devices

### War Driving
- War driving is a method attackers use to find wireless access points wherever they might be. By just driving (or walking) around, an attacker can obtain a significant amount of information over a very short period of time
- war flying, which involves using a portable computer or other mobile device to search for wireless networks from an aircraft, such as a drone or another unmanned aerial vehicle (UAV)

### Initialization Vector (IV) Attacks and Unsecured Wireless Protocols
- An attacker can cause some modification on the initialization vector (IV) of a wireless packet that is encrypted during transmission
- The goal of the attacker is to obtain a lot of information about the plaintext of a single packet and generate another encryption key that can then be used to decrypt other packets using the same IV. WEP is susceptible to many different attacks, including IV attacks.
- WEP must be avoided, and many wireless network devices no longer support it. WEP keys exist in two sizes: 40-bit (5-byte) and 104-bit (13-byte) keys
- When WEP uses RC4 to encrypt a packet, it prepends the IV to the secret key before including the key in RC4. Subsequently, an attacker has the first 3 bytes of an allegedly “secret” key used on every packet
- An attacker can accelerate this type of attack by just injecting ARP packets (because the length is predictable), which allows the attacker to recover the PSK much faster
- WPA version 3 (WPA3) addresses all the vulnerabilities to which WPA and WPA2 are susceptible, and many wireless professionals recommend WPA3 to organizations and individuals
- WPA is not susceptible to the IV attacks that affect WEP; however, it is possible to capture the WPA four-way handshake between a client and a wireless infrastructure device and then brute-force the WPA PSK
- Mathy Vanhoef and Frank Piessens, from the University of Leuven, found and disclosed a series of vulnerabilities that affect WPA and WPA2. These vulnerabilities – also referred to as KRACK (which stands for key reinstallation attack
- Successful exploitation could allow unauthenticated attackers to reinstall a previously used encryption or integrity key
-  Several vulnerabilities in WPA3 have been discovered in recent years. The WPA3 protocol introduced a new handshake called the “dragonfly handshake” that uses Extensible Authentication Protocol (EAP) for authentication
-  Several vulnerabilities can allow an attacker to perform different side-channel attacks, downgrade attacks, and DoS conditions
-  FragAttacks (which stands for fragmentation and aggregation attacks) is another type of vulnerability that can allow an attacker to exploit WPA3
-  Wi-Fi Protected Setup (WPS) is a protocol that simplifies the deployment of wireless networks. It is implemented so that users can simply generate a WPA PSK with little interaction with a wireless device

### KARMA Attacks
- KARMA (which stands for karma attacks radio machines automatically) is an on-path attack that involves creating a rogue AP and allowing an attacker to intercept wireless traffic
- In a KARMA attack scenario, the attacker listens for the probe requests from wireless devices and intercepts them to generate the same SSID for which the device is sending probes

### Fragmentation Attacks
- Wireless fragmentation attacks can be used to acquire 1500 bytes of pseudo-random generation algorithm (PRGA) elements. Wireless fragmentation attacks can be launched against WEP-configured devices
- These attacks do not recover the WEP key itself but can use the PRGA to generate packets with tools such as Packetforge-ng (which is part of the Aircrack-ng suite of tools) to perform wireless injection attacks

### Credential Harvesting
- Credential harvesting attacks can be launched using common social engineering attacks such as phishing attacks, and they can be performed by impersonating a wireless AP or a captive portal to convince a user to enter his or her credentials

### Bluejacking and Bluesnarfing
- Bluejacking is an attack that can be performed using Bluetooth with vulnerable devices in range. An attacker sends unsolicited messages to a victim over Bluetooth, including a contact card (vCard) that typically contains a message in the name field.
- This is done using the Object Exchange (OBEX) protocol. A vCard can contain name, address, telephone numbers, email addresses, and related web URLs
- Bluesnarfing attacks are performed to obtain unauthorized access to information from a Bluetooth-enabled device. An attacker can launch Bluesnarfing attacks to access calendars, contact lists, emails and text messages, pictures, or videos from the victim
- Bluejacking attacks only transmit data to the victim device, Bluesnarfing attacks actually steal information from the victim device
- Bluesnarfing attacks can also be used to obtain the International Mobile Equipment Identity (IMEI) number for a device
- Password spraying is a type of credential attack in which an attacker brute-forces logins (that is, attempts to authenticate numerous times) based on a list of usernames with default passwords of common systems or application

---

## Tools Introduced

- Pupy
- searchspoilt
- enum4linux
- smbclient
- snmp-check
- smtp-user-enum tool
- Mimikatz
- Empire is a popular tool that can be used to perform golden ticket
- aircrack-ng
- bluesnarfer
  
---

## References

- https://svn.nmap.org/nmap/scripts/smtp-open-relay.nse
- https://github.com/gentilkiwi/mimikatz
- https://www.offensive-security.com/metasploit-unleashed/mimikatz/
- https://www.kerberos.org/
- https://github.com/BC-SECURITY/Empire
- https://www.aircrack-ng.org/
- https://github.com/moxie0/sslstrip
- https://www.cisa.gov/news-events/alerts/2014/10/17/ssl-30-protocol-vulnerability-and-poodle-attack
- https://wigle.net/
- https://www.krackattacks.com/
- https://wpa3.mathyvanhoef.com/
- https://www.fragattacks.com/
- https://github.com/t6x/reaver-wps-fork-t6x
- http://download.aircrack-ng.org/wiki-files/doc/Fragmentation-Attack-in-Practice.pdf
- http://acadpubl.eu/jsi/2017-116-8/articles/9/72.pdf
