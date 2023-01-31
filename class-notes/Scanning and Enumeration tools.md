## Scanning Methodology Review

Check for live systems (no port scan)
- `nmap -sn`

Check for open ports (SYN scan)
- `nmap -sS`

Discover Services (service Version scan)
- `nmap -sV`

DIscover Operating Systems
- `nmap -A -sC -o`
    - `-A`: Stands for "all" scans
    - `-sC`: Scan with default NSE scripts
    - `-o` is included in the `-A` so its kinda repeative

Indentify Vulnerabillities
- `msf > search`

Map the network
- Use tools like sloarwinds, NTM, Zenmap, etc.

Create proxies
- Use tools like proxyswitcher, Proxy Workbench, CyberGhost, ProxyChains, Tor, etc.

## Define Scanning

When an attacker or penetration tester actively attempts to connect to a system and uses the response to gain information about a network.

## TCP/IP Networking

Why it matters in scanning?
- Layer 3 (network layer)
    - Where routing happens. Data is moved between systems.
    - The physical address is verified in the packet header and the segment is passed to layer 4 (transportation layer)
- Once at layer 4, the things an ethical hacker is most interested in occur... TCP flags and port numbering.

### What are PORTs for?
Ports are used to identify specific applications or services on a computer or device for incoming or outgoing data transmission. They allow communication between devices over a network.

## TCP Flags
- **SYN** - Establishes communication; first step in the 3-way handshake
- **Ack** - Achknowledgement flag, assures the inital packet was received
- **Fin** - Finished flag; the sender has axhausted its data and the connection is closed
- **URG** - Urgent flag; set when there is an urgent packet.
    - This packet will be processed before all other packets and the receiver will be notified. Cancelling a message in transit is an example.
- **PSH** - Push flag; these packets are processed first without buffering

## TCP Flags and Hackers

Hackers with tools like Nmap and others can manipulate the flags to obtain important data about systems.

## The three-way Handshake

Client sends a syn; Hello I would like to communicate

▼ Syn seq=x (client -> server)

Server sends back a syn ack; I ackknowledge that you want to communicate

▼ syn ack

## Port Numbering

Port numbers provide a way for layer 7 (the application layer) to process the datagram. This way, datagrams meant to send an email (SMTP), do not get sent to SSH or DNS.

## Port Scan Types

- **Full Connect** - Polite scan, TCP connect, or full open scan. Completes a 3-way handshake.
- **Stealth** - SYN scan, half open scan. Only SYN packets are sent to ports. The three-way handshake is not completed. Can bypass firewalls and monitoring systems because it hides as normal traffic

## ICMP Message Types
when you ping an address, its using one of the ICMP Message types

## Scanning and Enumeration tools

Ping tools:
- ping
- nmap
- Colasoft ping
- SolarWinds
- Angry IP scanner

Scanning tools:
- Hping
- Netcat
- Nmap
- SuperScan
- MegaPing

Banner Grabbing tools
- **Netcat**
- **Nmap**
- Netcat
- **curl**
- **wget**
- Xprobe
- Telnet
- Netcraft

Vulnerabillity Scanning tools
- Nessus
- Nikto
- OpenVas
- SAINT

## Banner Grabbing

Determine the OS on a remote target.

Knowing the OS will allow an attacker to search vulnerabilities that may exploit a target system. Banner grabbing looks at errors and responses, the compares them to a database of responses to determine the OS.

### Types of Banner Grabbing

- Active Banner Grabbing
    - Crafting packets to send to the target system and observing the responses
- Passive Banner Grabbing
    - Examine error messages, analyzing packet captures and examining extensions, can lead to OS detection.

## Banner Grabbing Countermeasures
- Disable or modify welcome messages
- Display false Banners
- Use producs like ServerMask to show the attacker different false information while showing administrators the correct information
- Turn off ServerSignature in the `httpd.conf` file.
- Hide file extensions because files like .asp will clearly define the OS.

## Scanning IPv6

Scanning an entire subnet is a difficult task as the search space is extremely large. It is not computionally feasible.

**Attackers will harvest IPv6 adresses by sniffing traffic**, checking logs, checking email headers, etc.

Nmap does support ipv6 scanning, but many scanning tools do not.
    - You would add the -6 after nmap.

- **Firewall rules are usually setup for IPv4. As a result, scanning the IPv6 could bypass the firewall** as the rules are not setup for IPv6.