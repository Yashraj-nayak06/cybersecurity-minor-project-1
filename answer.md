SECTION A: CYBERSECURITY FUNDAMENTALS 

Q1. Fundamentals 
- Cybersecurity Definition: Cybersecurity is the practice of protecting computers, servers, mobile devices, electronic systems, networks, and data from malicious attacks, unauthorized access, or damage.
- Importance: It is crucial in today's digital world to prevent data breaches, protect sensitive personal and financial privacy, and maintain uninterrupted system operations.
- CIA Triad: The three core pillars of information security are:
  1. Confidentiality: Ensuring sensitive data is accessible only to authorized individuals. Example: Encrypting online banking passwords and OTPs so unauthorized parties cannot intercept them.
  2. Integrity: Maintaining data accuracy and preventing unauthorized tampering or modification. Example: Using cryptographic hashing to ensure that money transfer amounts are not altered mid-transit by hackers.
  3. Availability: Ensuring systems and data are accessible to authorized users whenever needed. Example: Implementing DDoS protection on e-commerce websites like Amazon so servers stay online during heavy sales traffic.

Q2. Security Thinking 
- Vulnerability: A weakness or flaw in a system or software that an attacker can exploit. Example: Running an outdated, unpatched software version on a computer.
- Threat: Any potential danger that could exploit a vulnerability and cause harm. Example: The risk of a malware or ransomware infection.
- Risk: The likelihood that a threat will exploit a vulnerability and result in damage. Example: The probability of losing a database entirely if an unpatched system is targeted by malware.
- Attack: An actual malicious attempt to breach system security by exploiting a vulnerability. Example: A hacker executing an SQL injection to steal database records.

Q3. Types of Security 
1. Network Security: Protecting internal network infrastructure and traffic using firewalls, VPNs, and intrusion detection systems.
2. Application Security: Fixing bugs and security flaws during the software development lifecycle to prevent exploitation.
3. Cloud Security: Securing data, applications, and infrastructures hosted on cloud platforms (e.g., AWS, Azure) using encryption and access controls.
4. Endpoint Security: Securing individual end-user devices (laptops, desktops, mobile phones) using antivirus and security agents.
5. Physical Security: Restricting physical access to data centers and server rooms to prevent hardware theft or damage (e.g., biometric locks, security guards).


SECTION B: NETWORKING FUNDAMENTALS 

Q4. What is Networking? 
- Computer Network Definition: A collection of two or more computing devices connected via wired or wireless media to share data, hardware resources (such as printers), and communication channels.
- Why Organizations Use It: For resource sharing, centralized data management, cost reduction, and efficient internal/external communication.
- Network Types:
  1. PAN (Personal Area Network): Covers a very small personal range (approx. 10 meters). Example: Connecting a smartphone to wireless earphones or a smartwatch via Bluetooth.
  2. LAN (Local Area Network): Covers a small geographical area such as a room, office, or college lab. Example: Computers connected in a university computer lab.
  3. MAN (Metropolitan Area Network): Covers an entire city or large town. Example: A city-wide cable television network.
  4. WAN (Wide Area Network): Covers vast geographical areas spanning countries and continents. Example: The Internet.

Q5. Network Devices 
- Hub: A simple multiport device that broadcasts incoming data packets to all ports without filtering.
- Switch: An intelligent device that uses MAC addresses to forward data packets specifically to the intended target device.
- Router: Connects different networks (such as a LAN to the Internet/WAN) and routes data packets using IP addresses.
- Firewall: Monitors and filters incoming and outgoing network traffic based on established security rules.
- Access Point (AP): Creates wireless Wi-Fi signals to connect wireless devices to a wired network infrastructure.
- Switch vs. Router Difference: A switch connects devices within the same network segment (LAN), whereas a router connects distinct networks together and manages internet traffic.

Q6. How the Internet Works 
When a user enters example.com into a web browser, the following process occurs:
1. DNS (Domain Name System): The browser queries a DNS server to resolve the domain name example.com into its corresponding IP address.
2. IP Addressing & Gateway: The computer packages the request into data packets destined for that IP address and forwards them to the local gateway/router.
3. TCP/IP Protocol: TCP breaks the data into segments and ensures reliable delivery, while IP handles packet routing across networks.
4. Web Server: The request reaches the target web server, which processes it and sends the website data (HTML/CSS) back to the user's browser for rendering.

Flow Diagram:
[ Browser ] --(Enter URL)--> [ DNS Server ] --(Get IP)--> [ Local Router ]
                                                               |
                                                               v
                                                        [ Web Server ]


SECTION C: IP ADDRESSING

Q7. IPv4 & IPv6 
- Differentiate:
  - IPv4: Utilizes a 32-bit address scheme written in dotted-decimal notation, supporting roughly 4.3 billion addresses.
  - IPv6: Utilizes a 128-bit address scheme written in colon-separated hexadecimal notation, providing a virtually unlimited number of addresses.
- Why Introduced: IPv4 addresses faced exhaustion due to the exponential growth of internet-connected devices worldwide, necessitating IPv6 for expanded address space.
- Examples:
  - IPv4 Example: 192.168.1.1
  - IPv6 Example: 2001:db8:85a3::8a2e:370:7334

Q8. IP Classification 
- 10.10.10.5: Class A | Private IP
- 172.16.5.20: Class B | Private IP
- 192.168.1.50: Class C | Private IP
- 8.8.8.8: Class A | Public IP

Q9. IP Components
- Given IP: 192.168.20.45/24
- Subnet Mask: /24 corresponds to 255.255.255.0
- Network Address: 192.168.20.0
- Host Portion: Last octet .45
- Broadcast Address: 192.168.20.255
- Usable Host Range: 192.168.20.1 to 192.168.20.254


SECTION D: SUBNETTING & CALCULATIONS 

Q10. Basic Subnet Calculation 
- Given Network: 192.168.10.0/26
- Subnet Mask: /26 equates to 255.255.255.192
- Number of /26 subnets from /24: 2^(26-24) = 2^2 = 4 subnets.
- Usable hosts per subnet: 2^(32-26) - 2 = 64 - 2 = 62 hosts.
- First Subnet Details:
  - Network Address: 192.168.10.0
  - First Usable: 192.168.10.1
  - Last Usable: 192.168.10.62
  - Broadcast Address: 192.168.10.63

Q11. Subnetting Design 
- Given Base Network: 192.168.10.0/24. Host Requirements: IT (50), HR (30), Finance (20), Management (10).
  1. IT (50 hosts): Requires 64 IPs (2^6), CIDR = /26
     - Network: 192.168.10.0/26 | Mask: 255.255.255.192
     - Usable Range: 192.168.10.1 - 192.168.10.62 | Broadcast: 192.168.10.63 | Hosts: 62
  2. HR (30 hosts): Requires 32 IPs (2^5), CIDR = /27
     - Network: 192.168.10.64/27 | Mask: 255.255.255.224
     - Usable Range: 192.168.10.65 - 192.168.10.94 | Broadcast: 192.168.10.95 | Hosts: 30
  3. Finance (20 hosts): Requires 32 IPs (2^5), CIDR = /27
     - Network: 192.168.10.96/27 | Mask: 255.255.255.224
     - Usable Range: 192.168.10.97 - 192.168.10.126 | Broadcast: 192.168.10.127 | Hosts: 30
  4. Management (10 hosts): Requires 16 IPs (2^4), CIDR = /28
     - Network: 192.168.10.128/28 | Mask: 255.255.255.240
     - Usable Range: 192.168.10.129 - 192.168.10.142 | Broadcast: 192.168.10.143 | Hosts: 14


SECTION E: SCENARIO-BASED QUESTIONS 

Q12. Scenario Company Network 
- Network Type: LAN utilizing a Star Topology.
- Required Devices: 1 Router, Switches, 1 Firewall, 45 Employee Computers, 5 Servers, and Wi-Fi Access Points.
- Role of Devices:
  - Router: Connects the internal company network to the external WAN/Internet.
  - Switch: Connects internal systems together for high-speed local data transfer.
  - Firewall: Blocks unauthorized external access and cyber threats.
- Request Flow: An employee's request travels through the internal switch and firewall to the router, which forwards it across the internet to the target web server.

Q13. Scenario - IP Troubleshooting 
For a user configured with 192.168.1.25/24 who can reach local computers but cannot access external websites, follow these troubleshooting checks sequentially:
1. IP Configuration Check: Run ipconfig to verify that the IP address, subnet mask, and default gateway are configured correctly.
2. Gateway Ping Check: Ping the default gateway IP (ping <gateway_ip>) to confirm local router connectivity.
3. DNS Resolution Check: Run nslookup google.com to verify whether domain name resolution is functioning properly.
4. External Connectivity Test: Ping a public IP address (ping 8.8.8.8) to verify direct internet routing.
5. Firewall and Router Role Check: Ensure that NAT is configured correctly on the router and that no firewall policies are blocking outbound web traffic.
