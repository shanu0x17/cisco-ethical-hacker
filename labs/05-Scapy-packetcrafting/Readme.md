# Lab 05 – Packet Crafting with Scapy

## Objective

Gain hands-on experience with Scapy, a Python-based packet manipulation framework, to inspect packet structures, capture live network traffic, and craft custom ICMP and TCP packets for reconnaissance activities.

---

## Environment

- Operating System: Kali Linux
- Platform: Cisco Ethical Hacker Virtual Lab
- Tool Used:
  - Scapy (Python Packet Manipulation Framework)

---

## Activities Performed

- Launched the Scapy interactive shell.
- Explored Scapy's available protocols, packet classes, and built-in functions.
- Inspected the structure of IP packets.
- Captured live network traffic using packet sniffing.
- Reviewed captured packets to understand network communication.
- Crafted and transmitted a custom ICMP Echo Request packet.
- Crafted and transmitted a custom TCP SYN packet to a target host.
- Observed packet transmission results within the Scapy console.

---

## Tools Overview

| Tool | Purpose |
|------|---------|
| Scapy | Python-based framework for packet crafting, packet analysis, traffic sniffing, protocol testing, and network security research |

---

## Key Observations

- Scapy provides complete control over individual packet fields, making it useful for security testing and protocol analysis.
- Live packet sniffing enables analysts to observe real-time network communication.
- Custom ICMP packets can be used to verify host reachability during reconnaissance.
- TCP SYN packets allow analysts to probe network services without establishing a full TCP connection.
- Packet crafting offers deeper visibility into networking concepts compared to traditional command-line tools.

---

## Skills Practiced

- Packet Crafting
- Packet Analysis
- Traffic Sniffing
- ICMP Packet Creation
- TCP SYN Packet Generation
- Python-based Security Tools
- Network Reconnaissance

---

## Key Learnings

- Scapy combines packet creation, manipulation, transmission, and analysis into a single framework.
- Understanding packet headers is essential for network troubleshooting and penetration testing.
- Custom-crafted packets provide greater flexibility than standard networking utilities.
- Traffic sniffing helps analysts understand how protocols communicate across a network.
- Packet crafting is widely used for reconnaissance, security testing, protocol analysis, and research.

---

## Personal Reflection

This lab introduced me to Scapy and demonstrated how Python can be used to interact directly with network packets. I learned how to inspect protocol fields, monitor live traffic, and create custom ICMP and TCP packets for reconnaissance. The exercise improved my understanding of low-level networking concepts and highlighted the importance of packet manipulation during offensive security assessments.

---

## Disclaimer

This lab was completed in an authorized training environment for educational purposes only. All packet crafting and traffic analysis activities were performed against approved lab systems within a controlled environment.