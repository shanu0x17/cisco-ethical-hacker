# Module 01 – Introduction to Ethical Hacking and Penetration Testing

## Overview

Explain the importance of methodological ethical hacking and penetration testing.

---

## Learning Objectives

- Explain the importance of ethical hacking and penteration testing
- Explain different types of penetration testing methodologies and framework
- Configure a VM for pentesting
  
---

## Key Learnings

- Ethical hacker describes a person who acts as an attacker and evaluates the security posture of a computer network for the purpose of minimizing risk
- Penetration Tester, who is responsible for securing and defending a network/system, you want to find any possible paths of compromise before the bad guys do

### Threat Actors(malicious attacker)

- Organized Crime: Organized crime consists of very well-funded and motivated groups that will typically use any and all of the latest attack techniques
- Hacktivists: Hacktivists are looking to make a point or to further their beliefs, using cybercrime as their method of attack, stealing sensitive data and then revealing it to the public for the purpose of embarrassing or financially affecting a target
- State-Sponsored Attackers: Cyber war and cyber espionage are two terms that fit into this category. Many governments around the world today use cyber attacks to steal information from their opponents and cause disruption
- Insider Threats: An insider threat is a threat that comes from inside an organization

### Environmental Considerations of penetration tests

- Network Infrastructure Test, it is focused on evaluating the security posture of the actual network infrastructure and how it is able to help defend against attacks
- Application-Based Tests, focuses on testing for security weaknesses in enterprise applications
- Penetration Testing in the Cloud, the responsibility for cloud security depends on the type of cloud model (software as a service [SaaS], platform as a service [PaaS], or infrastructure as a service [IaaS])

- Unknown-Environment Test(black box): The tester is typically provided only a very limited amount of information
- Known-Environment Test(white box): The tester starts out with a significant amount of information about the organization and its infrastructure
- Partially Known Environment Test(gray box): Somewhat of a hybrid approach between unknown- and known-environment tests. With partially known environment testing, the testers may be provided credentials but not full documentation of the network infrastructure

### Different Standards and Methodologies

 - The MITRE ATT&CK framework is an amazing resource for learning about an adversary’s tactics, techniques, and procedures (TTPs)
 - The OWASP Web Security Testing Guide (WSTG) is a comprehensive guide focused on web application testing
 - NIST SP 800-115 provides organizations with guidelines on planning and conducting information security testing
 - The OSSTMM is a document that lays out repeatable and consistent security testing.The OSSTMM has the following key sections:

Operational Security Metrics
Trust Analysis
Work Flow
Human Security Testing
Physical Security Testing
Wireless Security Testing
Telecommunications Security Testing
Data Networks Security Testing
Compliance Regulations
Reporting with the Security Test Audit Report (STAR)

- The Penetration Testing Execution Standard (PTES) provides information about types of attacks and methods, and it provides information on the latest tools available to accomplish the testing methods outlined. PTES involves seven distinct phases:

Pre-engagement interactions
Intelligence gathering
Threat modeling
Vulnerability analysis
Exploitation
Post-exploitation
Reporting

- The Information Systems Security Assessment Framework (ISSAF) is another penetration testing methodology similar to the others on this list. SSAF covers the following phases:

Information gathering
Network mapping
Vulnerability identification
Penetration
Gaining access and privilege escalation
Enumerating further
Compromising remote users/sites
Maintaining access
Covering the tracks
 
---

## Tools Introduced

- VM
- Kali linux
  
---

## References

- https://www.hackingisnotacrime.org/
- https://aws.amazon.com/compliance/shared-responsibility-model
- https://attack.mitre.org
- https://owasp.org/www-project-web-security-testing-guide/
- https://csrc.nist.gov/publications/detail/sp/800-115/final
- https://www.isecom.org
- http://www.pentest-standard.org
- https://github.com/The-Art-of-Hacking/h4cker/tree/master/build_your_own_lab
