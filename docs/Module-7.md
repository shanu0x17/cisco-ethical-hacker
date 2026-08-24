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
---

## Tools Introduced

- nimbostratus
- 
---

## References

- https://github.com/andresriancho/nimbostratus
- https://www.owasp.org/index.php/Fuzzing
- https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html
- https://www.zaproxy.org/
- https://github.com/zaproxy/zaproxy
- https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet
