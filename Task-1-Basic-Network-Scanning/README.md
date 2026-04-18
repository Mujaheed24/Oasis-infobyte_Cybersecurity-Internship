# Task 1: Basic Network Scanning with Nmap

## Objective
Perform a network scan to identify open ports and services, and explain their significance in a security context.

## Methodology
* **Target:** Metasploitable 2 Virtual Machine (IP: `192.168.56.101`)
* **Command Executed:** `nmap -sV -O 192.168.56.101`
* **Tools Used:** Nmap on Kali Linux

## Port Findings & Security Significance

| Port | State | Service | Version | Definition & Security Significance |
| :--- | :--- | :--- | :--- | :--- |
| **21/tcp** | open | ftp | vsftpd 2.3.4 | Unencrypted file transfer. Contains a known backdoor. |
| **22/tcp** | open | ssh | OpenSSH 4.7p1 | Encrypted remote login. Essential for secure management. |
| **23/tcp** | open | telnet | Linux telnetd | Clear-text remote login. Highly insecure (sniffable). |
| **25/tcp** | open | smtp | Postfix smtpd | Mail server. Vulnerable to spoofing/spam relay. |
| **53/tcp** | open | domain | ISC BIND 9.4.2 | DNS resolver. Risk of unauthorized zone transfers. |
| **80/tcp** | open | http | Apache 2.2.8 | Web server. Prime target for web application exploits. |
| **139/tcp**| open | netbios-ssn| Samba smbd 3.X | Shared folders. Vulnerable to remote code execution. |
| **1524/tcp**| open | bindshell | Metasploitable root shell | **CRITICAL.** Open backdoor providing instant root access. |
| **3306/tcp**| open | mysql | MySQL 5.0.51a | Database server. Prime target for SQL injection. |
| **5900/tcp**| open | vnc | VNC (protocol 3.3) | Remote graphical desktop. Insecure if publicly exposed. |
| **6667/tcp**| open | irc | UnrealIRCd | Chat service. This version has known malicious backdoors. |

## Conclusion
The target is critically vulnerable, exposing legacy protocols and intentional backdoors. Immediate firewall restriction is mandatory.
