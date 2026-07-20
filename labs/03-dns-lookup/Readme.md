# Lab 03 – DNS Lookups

## Objective

Learn how to perform passive reconnaissance using DNS-related tools to gather publicly available information about a target domain. The lab focuses on resolving domain names, retrieving DNS records, performing WHOIS lookups, comparing DNS query tools, and conducting reverse DNS lookups. :contentReference[oaicite:0]{index=0}

---

## Environment

- Operating System: Kali Linux
- Platform: Cisco Ethical Hacker Virtual Lab
- Tools Used:
  - nslookup
  - whois
  - dig

---

## Activities Performed

- Used **nslookup** to resolve domain names into IPv4 and IPv6 addresses.
- Retrieved DNS resource records such as Name Servers (NS).
- Explored advanced query types supported by **nslookup**.
- Performed **WHOIS** lookups to obtain domain registration information.
- Compared the output of **nslookup** and **dig**.
- Executed reverse DNS lookups using the **dig -x** command.
- Analyzed DNS responses to understand how publicly available DNS information can assist reconnaissance.

---

## Tools Overview

| Tool | Purpose |
|------|---------|
| nslookup | Queries DNS servers for domain names, IP addresses, and DNS records |
| whois | Retrieves domain registration and ownership information |
| dig | Performs advanced DNS queries and provides detailed DNS response data |

---

## Key Observations

- DNS records reveal valuable infrastructure information without directly interacting with the target.
- WHOIS provides domain ownership, registrar, registration dates, and authoritative name server details.
- The **dig** command offers more structured and detailed DNS output compared to **nslookup**.
- Reverse DNS lookups help identify hostnames associated with IP addresses.
- Passive DNS reconnaissance is an essential first step before conducting active security assessments.

---

## Skills Practiced

- Passive Reconnaissance
- DNS Enumeration
- WHOIS Analysis
- Reverse DNS Lookup
- Information Gathering
- Network Footprinting

---

## Key Learnings

- DNS stores a significant amount of publicly accessible information useful during reconnaissance.
- Different DNS query tools provide different levels of detail depending on the investigation requirements.
- Reverse DNS lookups help correlate IP addresses with hostnames.
- Combining DNS queries with WHOIS information creates a more complete picture of a target's infrastructure.
- Passive reconnaissance allows security professionals to gather intelligence while minimizing detection.

---

## Personal Reflection

This lab strengthened my understanding of DNS-based reconnaissance techniques. I learned how to use multiple command-line tools to collect publicly available domain information, compare their outputs, and identify infrastructure details that can support future penetration testing activities. The exercise demonstrated how much intelligence can be gathered without sending intrusive traffic to the target environment.

---

## Disclaimer

This lab was completed in an authorized training environment for educational purposes only. All reconnaissance activities were limited to publicly available information and approved learning resources.
