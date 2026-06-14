# Research Report: Common Network Security Threats

**Intern:** Charita Grace Munnangi  
**Internship:** AICTE OIB-SIP Cybersecurity – May 2026  
**Task:** Task 4 – Research Report on Common Network Security Threats

---

## 1. Introduction

Network security threats are malicious activities that target computer networks with the intent to disrupt, steal, or damage data and systems. As organizations increasingly rely on digital infrastructure, understanding these threats is critical to building effective defenses. This report covers three major categories: Denial of Service (DoS) attacks, Man-in-the-Middle (MITM) attacks, and Spoofing attacks.

---

## 2. Denial of Service (DoS) and Distributed Denial of Service (DDoS) Attacks

### How It Works
A DoS attack overwhelms a target system — such as a web server — with a flood of illegitimate traffic, exhausting its resources (CPU, memory, bandwidth) until it can no longer serve legitimate users. A DDoS attack scales this up by using a botnet (a network of compromised machines) to generate traffic from thousands of sources simultaneously, making it far harder to block.

### Impact
- Service outages and downtime for businesses and users
- Financial losses (e-commerce sites can lose thousands per minute of downtime)
- Reputational damage and erosion of customer trust
- Can be used as a smokescreen for other simultaneous attacks

### Real-World Example
In 2016, the Mirai botnet launched a massive DDoS attack against Dyn, a major DNS provider, taking down major websites including Twitter, Netflix, Reddit, and GitHub for hours. The botnet was made up of compromised IoT devices like cameras and routers.

### Mitigation Strategies
- Use rate limiting and traffic filtering at the network edge
- Deploy DDoS protection services (e.g., Cloudflare, AWS Shield)
- Configure firewalls and intrusion prevention systems (IPS)
- Implement anycast network diffusion to distribute attack traffic
- Maintain an incident response plan specific to DDoS scenarios

---

## 3. Man-in-the-Middle (MITM) Attacks

### How It Works
In a MITM attack, an attacker secretly intercepts and potentially alters communication between two parties who believe they are communicating directly with each other. Common techniques include ARP spoofing (to redirect local network traffic), SSL stripping (to downgrade HTTPS to HTTP), and rogue Wi-Fi hotspots (to lure victims into connecting through the attacker's network).

### Impact
- Theft of sensitive data including login credentials, financial information, and personal data
- Session hijacking, allowing attackers to impersonate legitimate users
- Data manipulation — altering messages or transactions in transit
- Bypassing authentication mechanisms

### Real-World Example
In 2015, Lenovo was found shipping laptops with pre-installed adware called "Superfish" that performed MITM attacks on users' HTTPS connections by injecting a rogue root certificate, allowing it to intercept encrypted traffic and inject ads — and inadvertently exposing users to real attackers exploiting the same vulnerability.

### Mitigation Strategies
- Always use HTTPS (TLS/SSL) for web communications
- Implement certificate pinning in applications
- Use VPNs especially on public Wi-Fi networks
- Enable HSTS (HTTP Strict Transport Security) on web servers
- Use mutual authentication protocols to verify both parties in a communication

---

## 4. Spoofing Attacks

### How It Works
Spoofing refers to an attacker disguising their identity by falsifying data to impersonate a trusted entity. There are several types:
- **IP Spoofing:** Forging the source IP address in packets to impersonate another host
- **Email Spoofing:** Faking the sender address in emails to appear as a trusted source (common in phishing)
- **DNS Spoofing (Cache Poisoning):** Injecting false DNS records to redirect users to malicious websites
- **ARP Spoofing:** Sending fake ARP messages to link the attacker's MAC address with a legitimate IP address

### Impact
- Enables phishing and social engineering attacks
- Facilitates DDoS amplification attacks using forged source IPs
- Redirects users to fraudulent websites for credential theft
- Undermines trust in network communications

### Real-World Example
In 2010, the Kaminsky Attack (discovered by Dan Kaminsky in 2008) demonstrated a severe DNS cache poisoning vulnerability that could allow attackers to redirect internet traffic on a massive scale. This led to emergency patches being issued across the internet's DNS infrastructure.

### Mitigation Strategies
- Implement SPF, DKIM, and DMARC records to protect against email spoofing
- Use DNSSEC (DNS Security Extensions) to authenticate DNS responses
- Deploy ingress and egress filtering on routers to block spoofed IP packets
- Use dynamic ARP inspection (DAI) on network switches
- Regularly audit DNS records and monitor for anomalies

---

## 5. Comparative Summary

| Threat | Primary Target | Key Technique | Main Impact |
|---|---|---|---|
| DoS/DDoS | Availability | Traffic flooding | Service disruption |
| MITM | Confidentiality/Integrity | Traffic interception | Data theft/manipulation |
| Spoofing | Trust/Identity | Identity falsification | Fraud, redirection |

---

## 6. Conclusion

Network security threats such as DoS/DDoS attacks, MITM attacks, and spoofing represent some of the most persistent and damaging risks to modern digital infrastructure. Each exploits a different aspect of network communication — availability, confidentiality, and identity respectively. A robust security posture requires a layered defense strategy combining technical controls, network monitoring, and regular security audits. Understanding how these attacks work is the first step toward building systems resilient enough to withstand them.

---

## 7. References

- NIST Special Publication 800-61: Computer Security Incident Handling Guide
- OWASP: Man-in-the-Middle Attack – https://owasp.org/www-community/attacks/Manipulator-in-the-middle_attack
- Cloudflare Learning Center: What is a DDoS Attack – https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/
- US-CERT: Understanding Denial-of-Service Attacks
- Kaminsky, D. (2008). Black Ops 2008: It's the End of the Cache As We Know It.
