# Task1
Objective : Learn to discover open ports on devices in your local network to understand network exposure.<br>
Tools : Nmap, Wireshark<br><br>

Outcome : Basic network reconnaissance skill; understanding network service exposure.<br><br><br>


Interview Questions:<br><br>

1. What is an open port? <br>
   An open port is a network port on a device or server that is actively listening for incoming connections or data. It allows communication between devices over a network using specific protocols.<br><br><br>


2. How does Nmap perform a TCP SYN scan?<br>
   Nmap’s TCP SYN scan (a.k.a. “half-open” scan) works as follows:<br><br>

. Nmap sends a TCP packet with only the SYN flag set to the target port.<br>
. If the target responds with SYN/ACK, Nmap marks the port open and immediately sends a RST to tear down the connection (avoids completing the three-way handshake).<br>
. If the target responds with RST, Nmap marks the port closed.<br>
. If there is no response or an ICMP unreachable is received, Nmap marks the port filtered (packets likely blocked by a firewall).<br>
. Implementation details: Nmap crafts raw packets, runs many probes in parallel, and requires elevated privileges to send raw SYN packets. It’s considered stealthier than a full connect scan because it doesn’t complete connections.<br><br><br><br>


3. What risks are associated with open ports?<br>
   Open ports can expose systems to attacks like unauthorized access, data leaks, and exploits. They increase the risk of hacking, malware, and denial-of-service attacks.<br><br><br>


4. Explain the difference between TCP and UDP scanning.<br>
   TCP scanning establishes or partially establishes a connection to check port status, while UDP scanning sends datagrams without a handshake and relies on responses (or lack of them) to identify open or closed ports.<br><br><br>


5. How can open ports be secured?<br>
   Open ports can be secured by closing unused ports, using firewalls, applying patches, enabling access controls, and regularly scanning for vulnerabilities.<br><br><br>


6. What is a firewall's role regarding ports?<br>
   A firewall controls network traffic by allowing or blocking connections to specific ports, protecting systems from unauthorized access or attacks.<br><br><br>


7. What is a port scan and why do attackers perform it?<br>
   A port scan probes a host’s network ports to discover which services are listening.
Reasons attackers perform it:<br><br>

. Reconnaissance — find reachable services to target.<br>
. Vulnerability discovery — identify outdated or misconfigured services to exploit.<br>
. Prioritization — choose high-value targets (e.g., SSH, RDP).<br>
. Mapping — learn network structure and possible pivot points.<br><br><br>
   

8. How does wireshark complement port scanning?<br>
   Wireshark captures and analyzes network traffic, letting you see which ports are active, the type of traffic, and potential anomalies. It helps validate scan results, detect unauthorized services, and troubleshoot network issues.<br>

   
   
