# Lab 04 – Enumeration with Nmap

## Objective

Learn how to perform active reconnaissance using Nmap to discover live hosts, identify open ports, detect running services, perform operating system fingerprinting, and execute NSE (Nmap Scripting Engine) scripts for basic enumeration. :contentReference[oaicite:0]{index=0}

---

## Environment

- Operating System: Kali Linux
- Platform: Cisco Ethical Hacker Virtual Lab
- Target Network: 10.6.6.0/24
- Target Host: 10.6.6.23
- Tool Used:
  - Nmap

---

## Activities Performed

- Verified that Nmap was installed and available on the Kali system.
- Conducted a host discovery scan to identify active devices within the target subnet.
- Performed a basic port scan against the target host.
- Attempted operating system detection using Nmap fingerprinting techniques.
- Executed service version detection to identify running network services.
- Used Nmap Scripting Engine (NSE) scripts to perform SMB enumeration.
- Analyzed scan results to determine exposed services and potential attack surface.

---

## Tools Overview

| Tool | Purpose |
|------|---------|
| Nmap | Network discovery, host identification, port scanning, service detection, operating system fingerprinting, and security enumeration |

---

## Key Observations

- Host discovery successfully identified active systems within the subnet.
- The target host responded to Nmap scans, confirming network reachability.
- Service version detection identified available network services running on the target.
- Operating system fingerprinting attempted to estimate the host operating system based on TCP/IP characteristics.
- SMB enumeration scripts were executed to inspect SMB-related services and determine whether additional information could be collected.
- Nmap combines multiple reconnaissance techniques into a single framework, making it one of the most versatile tools for network enumeration.

---

## Skills Practiced

- Active Reconnaissance
- Host Discovery
- Port Scanning
- Service Enumeration
- Operating System Fingerprinting
- SMB Enumeration
- Nmap Scripting Engine (NSE)

---

## Key Learnings

- Host discovery should be performed before targeting individual systems.
- Port scanning reveals the network services exposed by a target host.
- Service detection provides additional context beyond open ports by identifying application versions.
- Operating system fingerprinting assists in selecting appropriate security assessment techniques.
- NSE scripts significantly extend Nmap's functionality by automating common enumeration tasks.
- Enumeration provides valuable intelligence that can guide later stages of a penetration test.

---

## Personal Reflection

This lab provided practical experience with Nmap as an active reconnaissance tool. I learned how to identify live hosts, enumerate services, perform operating system detection, and leverage NSE scripts for targeted information gathering. The exercise demonstrated how systematic enumeration helps build a detailed understanding of a target system before attempting further security assessments.

---

## Disclaimer

This lab was completed in an authorized training environment for educational purposes only. All scanning and enumeration activities were performed against systems specifically provided for hands-on cybersecurity training.
