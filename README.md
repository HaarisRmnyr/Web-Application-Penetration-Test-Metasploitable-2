# Web-Application-Penetration-Test-Metasploitable-2
This project documents a simulated penetration test conducted against Metasploitable 2, a deliberately vulnerable Linux VM. The goal was to identify and exploit common web application and network vulnerabilities, demonstrating a full understanding of the penetration testing lifecycle from reconnaissance to reporting.

**Phase 1: Reconnaissance with Nmap**
The project began by using Nmap, a leading network scanner, to perform an in-depth scan of the target machine. The Nmap scan provides a detailed map of the services running on the host, which is essential for planning subsequent attack vectors.

**Command Executed:**
nmap -A -p- [Metasploitable IP]

-A: The "Aggressive" flag, which enables OS detection (-O), version detection (-sV), and script scanning (-sC) in a single command. This provides a comprehensive overview of the host's configuration.

-p-: This option scans all 65,535 TCP ports, ensuring that no potential entry points are missed.

[Metasploitable IP]: The target IP address of the vulnerable machine on the isolated network.

**Key Findings from the Scan**

The Nmap scan, which ran for over 164 seconds, revealed several open ports and services that represent the primary attack surface of the machine. The following is a summary of the most critical findings:

Port 21 - FTP (vsftpd 2.3.4): An FTP service is running and allows anonymous logins. The version identified is known to contain a backdoor.

Port 22 - SSH (OpenSSH 4.7p1): The SSH service is active, indicating a potential entry point if weak credentials or a version-specific exploit can be found.

Port 80 - HTTP (Apache httpd 2.2.8): A web server is running on this port. The server is hosting several applications, including the Damn Vulnerable Web Application (DVWA), which is the intended target for web-based attacks.

Other Open Ports: The scan also identified a range of other open services, including Telnet (23), SMB (139, 445), and a database service (3306).

These findings provide the necessary intelligence to proceed with a targeted attack plan.
