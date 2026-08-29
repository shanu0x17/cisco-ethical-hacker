  # Module 07 – Cloud, Mobile & IOT

## Overview

- How to attack cloud technologies
- Common attacks against specialized systems
---

## Key Learnings:

### Cloud
- Cloud deployment models include the following:

Public cloud: Open for public use
Private cloud: Used just by the client organization on premises or at a dedicated area in a cloud provider
Community cloud: Shared between several organizations
Hybrid cloud: Composed of two or more clouds (including on-prem services)

- IaaS is a cloud solution in which you rent infrastructure
- PaaS provides everything except applications. Services provided by this model include all phases of the systems development life cycle (SDLC) and can use application programming interfaces (APIs), website portals, or gateway software
- SaaS is designed to provide a complete packaged solution. The software is rented out to the user. The service is usually provided through some type of front end or web portal
- Some of the common attacks are credential harvesting, privilige escalation, account takeover
- When an application requires access to specific assets, it can query the metadata service to get a set of temporary access credentials. This temporary set of credentials can then be used to access services such as AWS Simple Cloud Storage (S3) buckets and other resources
- If an attacker is able to manipulate a cloud-based IAM solution in an IaaS or PaaS environment, it could be catastrophic for the cloud consumer
- Federated authentication (or federated identity) is a method of associating a user’s identity across different identity management systems
- Insecure permission configurations for cloud object storage services, such as Amazon’s AWS S3 buckets, are often the cause of data breaches
- Attacks against container-based deployments (such as Docker, Rocket, LXC, and containerd) have led to massive data breaches. For instance, you can passively obtain information from Shodan (shodan.io) or run active recon scans to find cloud deployments widely exposing the Docker daemon or Kubernetes elements to the Internet
- Typosquatting is a technique that leverages human error when typing URLs in a web browser or accessing other resources
- One of the benefits of leveraging cloud services is the distributed and resilient architecture that most leading cloud providers offer. This architecture helps minimize the impact of a DoS or distributed denial-of-service (DDoS) attack compared to what it would be if you were hosting your application on premises in your data center
- Another example of a DoS attack that can affect cloud environments is the direct-to-origin (D2O) attack. In a D2O attack, threat actors are able to reveal the origin network or IP address behind a content delivery network (CDN) or large proxy placed in front of web services in a cloud provider
- A CDN is a geographically distributed network of proxies in data centers around the world that offers high availability and performance benefits by distributing web services to end users around the world
- In a cloud malware injection attack, the attacker creates a malicious application and injects it into a SaaS, PaaS, or IaaS environment
- Side-channel attacks are often based on information gained from the implementation of the underlying computer system (or cloud environment) instead of a specific weakness in the implemented technology or algorithm
- Software development kits (SDKs) and cloud development kits (CDKs) can provide great insights about cloud-hosted applications, as well as the underlying infrastructure
- An SDK is a collection of tools and resources to help with the creation of applications. SDKs often include compilers, debuggers, and other software frameworks
- CDKs, on the other hand, help software developers and cloud consumers deploy applications in the cloud and use the resources that the cloud provider offers

### IOT, Mobile devices

- The process of analyzing the compiled mobile app to extract information about its source code could be used to understand the underlying architecture of a mobile application and potentially manipulate the mobile device is reverse engineering
- Attackers use reverse engineering techniques to compromise the mobile device operating system (for example, Android, Apple iOS) and root or jailbreak mobile devices
- iOS and Android apps are isolated from each other via sandbox environments. Sandboxes in mobile devices are a mandatory access control mechanism describing the resources that a mobile app can and can’t access
- An attacker could perform detailed analysis of the sandbox implementation in a mobile device to potentially bypass the access control mechanisms implemented by Google (Android) or Apple (iOS), as well as mobile app developers
- Most prevalent vulnerabilities: Insecure storage, Passcode vulnerabilities and biometric integrations, Certificate pinning, Execution of activities using root and over reach of permissions, Buisness logic flaws
- Tools used to perform security research and test the security posture of mobile devices: Burpsuite, Drozer, needle, postman, ettercap or bettercap, frida, APK Studio
- Managing and orchestrating IoT systems introduces additional complexity due to disparate hardware and software, the use of legacy technologies, and, often, multiple vendors and integrators
-  IoT platforms must integrate a wide range of IoT edge devices with varying device constraints and must be integrated to back-end business applications
- IoT environments span a range of components that include sensors, gateways, network connectivity, applications, and cloud infrastructure
- A secure IoT platform should provide the complete end-to-end infrastructure to build an IoT solution, including the software, management, and security to effectively collect, transform, transport, and deliver data to provide business value
- Few special considerations to keep in mind when trying to secure IoT implementations: Fragile Env, DoS attacks against IoT systems are a major concern, Data corruption, Data Exfiltration
- Common IOT Vulnerabilities: Insecure defaults, Plaintext communication and data leakage, hard coded configurations, Outdated firmware
- Data Storage System Vulnerabilities: Default credentials, Network exposure, lack of user input sanitization, error messages and debug handling
- The hypervisor is the entity that controls and manages the VMs. There are two types of hypervisors:

Type 1 hypervisors (also known as native or bare-metal hypervisors) run directly on the physical (bare-metal) system. Examples of Type 1 hypervisors include VMware ESXi, Proxmox Virtual Environment, Xen, and Microsoft Hyper-V.
Type 2, or hosted, hypervisors run on top of other operating systems. Examples of type 2 hypervisors include VirtualBox and VMware Player or Workstation.

- VM escape vulnerabilities: These vulnerabilities allow an attacker to “escape” the VM and obtain access to other virtual machines on the system or access to the hypervisor
- Hyperjacking is a vulnerability that could allow an attacker to control the hypervisor. Hyperjacking attacks often require the installation of a malicious (or “fake”) hypervisor that can manage the entire virtual environment

---

## Tools Introduced

- nimbostratus
- GATTacker
---

## References

- https://github.com/andresriancho/nimbostratus
- https://www.owasp.org/index.php/Fuzzing
- https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html
- https://www.zaproxy.org/
- https://github.com/zaproxy/zaproxy
- https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet
- https://spectreattack.com/
- https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html
- https://github.com/OWASP/owasp-mstg/tree/master/Crackmes
- https://greatscottgadgets.com/ubertoothone/
- https://github.com/securing/gattacker
- https://www.cisecurity.org/cis-benchmarks
