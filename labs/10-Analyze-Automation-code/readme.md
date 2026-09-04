# Lab – Analyze Automation Code

## Objective

In this lab, a Bash script was created to automate an Nmap scan and store the scan results. The lab also focuses on understanding how scripting can automate repetitive penetration-testing tasks. :contentReference[oaicite:2]{index=2}

---

## Environment

- Operating System: Kali Linux
- Target IP: 10.6.6.23
- Scripting Language: Bash
- Scanning Tool: Nmap
- Script Name: recon.sh

---

## Activities Performed

- Created a Bash script named `recon.sh`.
- Added command-line argument handling to accept the target IP address.
- Implemented input checking to verify whether a target IP was supplied.
- Added Nmap service/version detection scanning.
- Stored the Nmap scan results in `scan_results.txt`.
- Added logic to check whether SMB port 445 was open.
- Attempted SMB enumeration using `enum4linux` when an open SMB port was detected.
- Made the Bash script executable using `chmod +x`.
- Executed the script against the target `10.6.6.23`.
- Verified the generated scan results.

---

## Script Logic

The script first checks whether a target IP address has been supplied as a command-line argument.

If no IP address is provided, the script displays the correct usage syntax and exits.

If an IP address is provided, the script displays the target and performs an Nmap service/version scan.

The scan output is redirected to:

`scan_results.txt`

The script then checks the scan results for an open SMB port (445). If SMB is detected, `enum4linux` is executed for additional enumeration.

---

## Commands Used

```bash
chmod +x recon.sh
