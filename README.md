# Scanresults
Task 1 : 
scan  your local network for open ports

##Tools used
Nmap

##Command used 
nmap -sS 192.168.1.8/24

Devices found : 2

ip address 92.168.1.1
  
## Findings
- Devices found: 2
- ip address 92.168.1.1
- Common open ports:
  21/tcp – FTP 
  53/tcp – DNS 
  80/tcp – HTTP 
  443/tcp – HTTPS
  
- ip address 92.168.1.12
  135/tcp – MSRPC
  139/tcp – NetBIOS-SSN
  445/tcp – Microsoft-DS (SMB)

## Risk Analysis
- ip address 92.168.1.1
21	FTP	- File Transfer Protocol - Can expose usernames/passwords. Vulnerable to brute-force 
53	DNS	- Domain Name System	- Can be used for DDoS attacks or data exfiltration (DNS tunneling).
80	HTTP - Web Server	- If outdated, could be vulnerable to XSS, directory traversal, or RCE. Sends data in plaintext.
443	HTTPS	- Secure Web Server	-Generally secure if SSL/TLS is updated. Misconfigurations or weak ciphers can still be exploited.
  
 - ip address 92.168.1.12
 135 - MSRPC - Targeted by malware (e.g., Conficker, WannaCry). Used in lateral movement in Windows networks.
 139 - NetBIOS	-	Can leak sensitive info. Susceptible to SMB relay and sniffing attacks.
 445 - SMB	-	Highly exploited (EternalBlue, WannaCry). Should not be exposed to untrusted networks.


## Conclusion
This task gave me hands-on experience with Nmap and helped me understand how to scan a local network, detect open ports, and assess basic security risks. It was a great introduction to real-world network reconnaissance.



