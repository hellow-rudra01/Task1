# Task1
Objective : Learn to discover open ports on devices in your local network to understand network exposure.
Tools : Nmap, Wireshark

Outcome : Basic network reconnaissance skill; understanding network service exposure.


Interview Questions:

1. What is an open port?
   An open port is a network port on a device or server that is actively listening for incoming connections or data. It allows communication between devices over a network using specific protocols.


2. How does Nmap perform a TCP SYN scan?
   Nmap’s TCP SYN scan (a.k.a. “half-open” scan) works as follows:

. Nmap sends a TCP packet with only the SYN flag set to the target port.
. If the target responds with SYN/ACK, Nmap marks the port open and immediately sends a RST to tear down the connection (avoids completing the three-way handshake).
. If the target responds with RST, Nmap marks the port closed.
. If there is no response or an ICMP unreachable is received, Nmap marks the port filtered (packets likely blocked by a firewall).
. Implementation details: Nmap crafts raw packets, runs many probes in parallel, and requires elevated privileges to send raw SYN packets. It’s considered stealthier than a full connect scan because it doesn’t complete connections.


3. What risks are associated with open ports?
   Open ports can expose systems to attacks like unauthorized access, data leaks, and exploits. They increase the risk of hacking, malware, and denial-of-service attacks.


4. Explain the difference between TCP and UDP scanning.
   TCP scanning establishes or partially establishes a connection to check port status, while UDP scanning sends datagrams without a handshake and relies on responses (or lack of them) to identify open or closed ports.


5. How can open ports be secured?
   Open ports can be secured by closing unused ports, using firewalls, applying patches, enabling access controls, and regularly scanning for vulnerabilities.


6. What is a firewall's role regarding ports?
   A firewall controls network traffic by allowing or blocking connections to specific ports, protecting systems from unauthorized access or attacks.


7. What is a port scan and why do attackers perform it?
   A port scan probes a host’s network ports to discover which services are listening.
Reasons attackers perform it:

. Reconnaissance — find reachable services to target.
. Vulnerability discovery — identify outdated or misconfigured services to exploit.
. Prioritization — choose high-value targets (e.g., SSH, RDP).
. Mapping — learn network structure and possible pivot points.
   

8. How does wireshark complement port scanning?
   Wireshark captures and analyzes network traffic, letting you see which ports are active, the type of traffic, and potential anomalies. It helps validate scan results, detect unauthorized services, and troubleshoot network issues.

   
   
