# Task 1 – Network Scanning with Nmap

**Intern:** Charita Grace Munnangi  
**Internship:** AICTE OIB-SIP Cybersecurity – May 2026

## Objective
Use Nmap to perform network scanning and identify open ports and running services on a target system.

## Tools Used
- Nmap 7.98
- Ubuntu (WSL on Windows 11)

## Process Followed

1. Installed WSL (Windows Subsystem for Linux) and set up Ubuntu on Windows 11
2. Installed Nmap using: `sudo apt update && sudo apt install nmap -y`
3. Ran a service version detection scan on localhost:
4. Saved scan output to `nmap_scan_results.txt`

## Results
The scan on localhost (127.0.0.1) showed all 1000 ports in closed/ignored states, which is expected for a fresh Ubuntu WSL environment with no services running. This confirms the system has a minimal attack surface with no unnecessary open ports.

## Key Learnings
- Nmap uses TCP connect scans to probe ports and identify their state (open/closed/filtered)
- The `-sV` flag detects service versions running on open ports
- The `-A` flag enables OS detection, version detection, and traceroute
- A clean scan result with no open ports indicates a well-secured minimal system
