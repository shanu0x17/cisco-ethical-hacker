# Lab – Analyze Automation Code

## Objective

In this lab, a Bash script was created to automate an Nmap scan and store the scan results. The lab also focuses on understanding how scripting can automate repetitive penetration-testing tasks.

## Environment

- Operating System: Kali Linux
- Target IP: 10.6.6.23
- Scripting Language: Bash
- Scanning Tool: Nmap
- Script Name: recon.sh

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

## Script Logic

The script first checks whether a target IP address has been supplied as a command-line argument.

If no IP address is provided, the script displays the correct usage syntax and exits.

If an IP address is provided, the script displays the target and performs an Nmap service/version scan.

The scan output is redirected to `scan_results.txt`.

The script then checks the scan results for an open SMB port (445). If SMB is detected, `enum4linux` is executed for additional enumeration.

## Commands Used

```bash
chmod +x recon.sh
```

```bash
./recon.sh 10.6.6.23
```

The Bash script internally performs:

```bash
nmap -sV $1 > scan_results.txt
```

and checks for SMB using:

```bash
grep 445 scan_results.txt | grep -iq open
```

If an open SMB port is found, it executes:

```bash
enum4linux -U -S $1 >> scan_results.txt
```

## Observed Output

The script was successfully executed against:

```text
Target IP 10.6.6.23
Running Nmap...
Scan complete - results written to scan_results.txt
Open SMB share ports not found.
```

This indicates that the script successfully accepted the target IP, executed the Nmap scan, saved the results, and checked for an open SMB service.

## Key Concepts

| Concept | Description |
|---|---|
| Bash Script | Automates a sequence of Linux commands |
| `$1` | Stores the first command-line argument |
| `-z` | Checks whether a variable is empty/null |
| `echo` | Displays text on the terminal |
| `exit 1` | Terminates the script with an error status |
| `chmod +x` | Gives executable permission to the script |
| Nmap | Performs network/service scanning |
| `grep` | Searches text for a specified pattern |
| `enum4linux` | Performs enumeration of SMB/Windows-related information |

## Key Observations

- Bash scripts can automate repetitive penetration-testing tasks.
- Command-line arguments allow the same script to be reused against different targets.
- Nmap results can be redirected to a file for later analysis.
- The script can use the output of one security tool to decide whether another tool should be executed.
- The provided script does not validate whether the supplied value is actually a legal IP address before running Nmap.

## Skills Practiced

- Bash scripting
- Linux command-line operations
- Nmap automation
- Service enumeration
- File output and redirection
- Conditional statements
- Command-line argument handling
- Basic penetration-testing automation

## Personal Reflection

This lab helped me understand how Bash scripting can be used to automate repetitive penetration-testing tasks. I learned how command-line arguments, conditional statements, file redirection, and external security tools can be combined into a single script. Automating reconnaissance tasks can make security assessments more efficient and consistent.

## Disclaimer

This lab was performed in an authorized cybersecurity training environment for educational purposes only. The scanning and enumeration activities were conducted against the designated lab target.
