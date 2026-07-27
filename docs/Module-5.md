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
---

## References

- https://svn.nmap.org/nmap/scripts/smtp-open-relay.nse
- https://github.com/gentilkiwi/mimikatz
- https://www.offensive-security.com/metasploit-unleashed/mimikatz/
- https://www.kerberos.org/
- https://github.com/BC-SECURITY/Empire
- https://github.com/moxie0/sslstrip
- https://www.cisa.gov/news-events/alerts/2014/10/17/ssl-30-protocol-vulnerability-and-poodle-attack
