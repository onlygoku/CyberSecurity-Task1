# CyberSecurity-Task1  
## Task 1: Local Network Security Scan

## Objective
The objective of this task was to perform a security assessment of a local network by identifying active hosts and enumerating open ports. The purpose of the scan was to understand the network exposure surface and identify potential security risks associated with accessible services.

## Tools Used
**Nmap (Network Mapper)**  
Used for host discovery, TCP port scanning, and service identification.

## Methodology
1. Identified the local network IP address range using system network configuration.
2. Performed a TCP SYN scan using Nmap:

nmap -sS <network_range>


3. Enumerated live hosts and detected open ports on each discovered device.
4. Analyzed running services associated with open ports.
5. Evaluated possible security risks based on exposed services and common attack vectors.

## Scan Results Summary
The scan identified multiple active devices within the local network. For privacy and security reasons, internal IP addresses have been anonymized.

### Router ([ROUTER_IP])
**Open Ports Identified**
- 53 (DNS)
- 80 (HTTP Web Interface)
- 443 (HTTPS Web Interface)
- 8080 (Alternate Web Administration)

**Security Considerations**
- Web administration interfaces exposed on the network may be vulnerable if default or weak credentials are used.
- HTTP access (port 80) may allow unencrypted management sessions if HTTPS is not enforced.
- Router firmware should be regularly updated to mitigate known vulnerabilities.

### Windows PC ([WINDOWS_PC_IP])
**Open Ports Identified**
- 135 (RPC)
- 139 (NetBIOS Session Service)
- 445 (SMB)

**Security Considerations**
- SMB-related services are historically targeted by worms and ransomware attacks.
- Systems must be patched regularly to prevent exploitation of known vulnerabilities.
- File sharing should be restricted to trusted networks only.
- Firewall rules should limit unnecessary exposure.

## Repository Contents
- **nmap_scan_results.txt**  
Raw output generated from the Nmap scan.

- **screenshot.png**  
Terminal screenshot showing the executed Nmap command and scan results.

## Conclusion
The assessment demonstrated that even small local networks expose multiple services that may present security risks if improperly configured. Regular network scanning, system patching, and secure credential management are essential practices for maintaining a strong security posture.
