  # Module 08 – Performing post-exploitation techniques

## Overview

- Creating a foothold and maintaing persistence after compromising a system
- Understanding how to perform lateral movement, detection, avoidance and enumeration
  
---

## Key Learnings:

- A shell is a utility (software) that acts as an interface between a user and the operating system (the kernel and its services)
- Windows PowerShell is a newer Microsoft shell that combines the old CMD functionality with a new scripting/cmdlet instruction set with built-in system administration functionality
- PowerShell cmdlets allow users and administrators to automate complicated tasks with reusable scripts
- With a bind shell, an attacker opens a port or a listener on the compromised system and waits for a connection. This is done in order to connect to the victim from any system and execute commands and further manipulate the victi
- A reverse shell is a vulnerability in which an attacking system has a listener (port open), and the victim initiates a connection back to the attacking system
- Netcat is one of the best and most versatile tools for pen testers because it is lightweight and very portable
- Attackers often use command and control (often referred to as C2 or CnC) systems to send commands and instructions to compromised systems
- A C2 creates a covert channel with the compromised system. A covert channel is an adversarial technique that allows the attacker to transfer information objects between processes or systems that, according to a security policy, are not supposed to be allowed to communicate
- Attackers often use virtual machines in a cloud service or even use other compromised systems as C2 servers. Even services such as Twitter, Dropbox, and Photobucket have been used for C2 tasks
- Many different techniques and utilities can be used to create a C2: Socat, wsc2, WMImplat, Dropbox c2, TrevoeC2, twittor, DNSCat2.
- Windows has a command that attackers can use to schedule automated execution of tasks on a local or remote computer
- You can take advantage of the Windows Task Scheduler to bypass User Account Control (UAC) if the user has access to its graphical interface. This is possible because the security option runs with the system’s highest privileges
- When a Windows user creates a new task, the system typically doesn’t require the user to authenticate with an administrator account
- Much as with scheduled tasks, you can create your own custom daemons (services) and processes on a victim system, as well as additional backdoors
- Whenever possible, a backdoor must survive reboots to maintain persistence on the victim’s system. You can ensure this by creating daemons that are automatically started at bootup
- After you compromise a system, if you obtain administrator (root) access to the system, you can create additional accounts
- Lateral movement (also referred to as pivoting) is a post-exploitation technique that can be performed using many different methods. The main goal of lateral movement is to move from one device to another to avoid detection, steal sensitive data, and maintain access to the devices to exfiltrate the sensitive data
- Data exfiltration is the act of deliberately moving sensitive data from inside an organization to outside an organization’s perimeter without permission
- Lateral movement is possible if an organization does not segment its network properly. Network segmentation is therefore very important
- Remote Desktop connections are fully encrypted, and monitoring systems cannot see what you are doing in the remote system. The main disadvantage of Remote Desktop is that a user working on the compromised remote system may be able to detect that you are logged on to the system
- Using legitimate tools to perform post-exploitation activities is often referred to as living-off-the-land and, in some cases, as fileless malware. The term fileless malware refers to the idea that there is no need to install any additional software or binaries to the compromised system
- Remote management in Windows via PowerShell (often called PowerShell [PS] remoting ) is a basic feature that a system administrator can use to access and manage a system remotely
- PowerSploit is a collection of PowerShell modules that can be used for post-exploitation and other phases of an assessment
- Another PowerShell-based post-exploitation framework is Empire, which is an open-source framework that includes a PowerShell Windows agent and a Python Linux agent
- You can use a single-page JavaScript web application called BloodHound that uses graph theory to reveal the hidden relationships in a Windows Active Directory environment
- An attacker can use BloodHound to identify numerous attack paths. Similarly, incident response teams can use BloodHound to detect and eliminate those same attack paths
- Windows Management Instrumentation (WMI) is used to manage data and operations on Windows operating systems. You can write WMI scripts or applications to automate administrative tasks on remote computers
- Sysinternals is a suite of tools that allows administrators to control Windows-based computers from a remote terminal. You can use Sysinternals to upload, execute, and interact with executables on compromised hosts
- PsExec is one of the most powerful Sysinternals tools. You can use it to remotely execute anything that can run on a Windows command prompt
- After compromising a system during a penetration testing engagement, you should always cover your tracks to avoid detection by suppressing logs (when possible), deleting user accounts that could have been created on the system, and deleting any files that were created
- Steganography involves hiding a message or any other content inside an image or a video file
- Attackers can use steganography for obfuscation, evasion, and to cover their tracks
---

## Tools Introduced

- netcat
- BloodHound
- PsExec
---

## References

- https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands
- https://www.offensive-security.com/metasploit-unleashed
- https://www.thec2matrix.com/
- https://github.com/PowerShellMafia/PowerSploit
- https://github.com/EmpireProject/Empire
- https://github.com/EmpireProject/Empire
- https://github.com/BloodHoundAD/Bloodhound
