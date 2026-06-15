# Task 2 – Firewall Configuration with UFW

**Intern:** Charita Grace Munnangi  
**Internship:** AICTE OIB-SIP Cybersecurity – May 2026

## Objective
Configure a firewall using UFW (Uncomplicated Firewall) on Linux to allow and deny specific network traffic.

## Tools Used
- UFW (Uncomplicated Firewall)
- Ubuntu (WSL on Windows 11)

## Process Followed

1. Installed UFW: `apt install ufw -y`
2. Enabled the firewall: `ufw enable`
3. Added firewall rules:
   - `ufw allow ssh` – Allow SSH connections (port 22)
   - `ufw allow 80/tcp` – Allow HTTP web traffic (port 80)
   - `ufw deny 23/tcp` – Block Telnet (insecure protocol)
4. Verified configuration: `ufw status verbose`

## Results
The firewall was successfully configured with the following rules:
- Port 22 (SSH) – ALLOWED: Needed for secure remote administration
- Port 80 (HTTP) – ALLOWED: Needed for web traffic
- Port 23 (Telnet) – DENIED: Telnet transmits data in plaintext and is a security risk

## Key Learnings
- UFW simplifies iptables firewall management on Linux
- Default deny policy on incoming traffic is a security best practice
- Telnet (port 23) should always be blocked in favor of SSH (port 22)
- Firewall rules are applied in order and persist across reboots
