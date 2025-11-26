# Chapter 12: Computer Networks and the Internet

## Why Networks Matter

Individual computers are powerful, but networked computers are transformative:
- **Communication**: Email, messaging, voice, video
- **Resource sharing**: Files, printers, storage
- **Distributed computing**: Multiple computers work on one problem
- **Knowledge distribution**: Websites, databases, wikis
- **Coordination**: Organize communities, economies, societies

The internet (pre-collapse) connected billions of devices and people. Post-collapse, rebuilding networks is essential for coordinating the rebuilding of civilization itself.

## Network Fundamentals

### Basic Concepts

**Node**: Any device on the network (computer, server, router, etc.)

**Link**: Physical or wireless connection between nodes
- Wire (copper, fiber optic)
- Radio (wireless)
- Other (infrared, laser,acoustic in water)

**Protocol**: Rules for how nodes communicate
- How to format messages
- How to address recipients
- How to detect and handle errors
- How to control flow (don't overwhelm receiver)

**Network Topologies**:

**Bus**: All nodes on shared medium
```
Node—Node—Node—Node (all on one wire)
```
- Simple
- Collision problem (two nodes transmit simultaneously)
- Example: Early Ethernet

**Star**: Central hub or switch
```
    Node
     |
Node—Hub—Node
     |
    Node
```
- Hub failure breaks network
- Easy to manage
- Example: Modern Ethernet with switch

**Ring**: Nodes in loop
```
Node—Node
|        |
Node—Node
```
- Data travels one direction
- Break anywhere breaks network (unless dual ring)
- Example: Token Ring, FDDI

**Mesh**: Multiple paths between nodes
```
Node—Node
|  X  |
Node—Node
```
- Redundant (failure-tolerant)
- Complex routing
- Example: Internet backbone, wireless mesh networks

**Tree/Hierarchical**: Branching structure
```
       Root
      /    \
  Node      Node
  /  \      /  \
Node Node Node Node
```
- Scalable
- Single root = single point of failure
- Example: Corporate networks

### OSI Model (Seven Layers)

**Conceptual Framework** for understanding networks:

**Layer 1 - Physical**: Bits on wire
- Voltage levels, timing, connectors
- Examples: Ethernet cable, RS-232, fiber optics, radio

**Layer 2 - Data Link**: Frames between adjacent nodes
- Addressing (MAC addresses)
- Error detection (CRC)
- Examples: Ethernet, WiFi, PPP

**Layer 3 - Network**: Routing between networks
- Logical addressing (IP addresses)
- Routing decisions
- Examples: IP (Internet Protocol), ICMP

**Layer 4 - Transport**: End-to-end communication
- Reliability (error recovery, ordering)
- Flow control
- Examples: TCP (reliable), UDP (unreliable but fast)

**Layer 5 - Session**: Managing connections
- Setup, maintenance, teardown
- Less commonly used as distinct layer

**Layer 6 - Presentation**: Data format translation
- Encryption, compression, encoding
- Examples: TLS/SSL, JPEG, MPEG

**Layer 7 - Application**: User-facing protocols
- Examples: HTTP (web), SMTP (email), FTP (file transfer), DNS

**Practical Use**: When designing networks, think in layers. Each layer uses services of layer below, provides services to layer above.

## Local Area Networks (LAN)

### Ethernet

**Most Common LAN Technology** (by 2025)

**Principle**: Shared or switched communication over copper or fiber

**Original Ethernet** (1970s-1980s):
- 10 Mbps (megabits per second)
- Coaxial cable (thick or thin)
- Bus topology
- CSMA/CD (Carrier Sense Multiple Access with Collision Detection):
  - Listen before transmitting
  - If collision detected, wait random time and retry

**Modern Ethernet** (1990s-2020s):
- Speeds: 100 Mbps, 1 Gbps, 10 Gbps, 100 Gbps
- Twisted pair cable (Cat5, Cat6) or fiber optic
- Star topology with switch (not hub)
- Full duplex (simultaneous send and receive, no collisions)

**Frame Format**:
```
Preamble (8 bytes): Synchronization
Destination MAC (6 bytes): Receiver address
Source MAC (6 bytes): Sender address
Type/Length (2 bytes): What's inside (IP, ARP, etc.)
Data (46-1500 bytes): Payload
CRC (4 bytes): Error detection
```

**MAC Address**: 48-bit hardware address
- Unique per network interface (assigned by manufacturer)
- Example: 00:1A:2B:3C:4D:5E (hex notation)
- First 24 bits: Manufacturer ID (OUI)
- Last 24 bits: Device ID

**Building Ethernet**:

**Twisted Pair Cable**:
- 4 pairs of wires, each pair twisted (reduces interference)
- Category 5/6: 100 MHz / 250 MHz bandwidth
- RJ-45 connector (8 pins)
- Pin assignment: T568A or T568B standard
- Can make your own cables:
  - Cut cable to length
  - Strip outer jacket
  - Untwist pairs, arrange by standard
  - Insert into RJ-45 connector
  - Crimp with tool

**Network Interface Card (NIC)**:
- Translates between computer bus and network
- Has MAC address
- Transmit and receive logic
- Early: Discrete components or LSI chip
- Modern: Single chip
- Salvage: NICs common in 2025 computers

**Ethernet Switch**:
- Learns MAC addresses on each port
- Forwards frames only to destination port (vs. hub which broadcasts)
- Store-and-forward or cut-through
- Simple switch: 4-8 ports
- Can build with microcontroller (once you have them) or FPGA
- Salvage: Switches very common

**Hub** (Simpler, Lower Performance):
- Broadcasts all traffic to all ports
- Half-duplex only
- Collisions
- Easier to build than switch

**Building a Simple Ethernet**:
1. **Transceivers**: Convert digital signals to electrical (or optical)
2. **Collision detection** (if bus or hub): Monitor for simultaneous transmissions
3. **Framing**: Build frames with addresses, data, CRC
4. **CRC calculation**: Polynomial division for error detection
5. **MAC logic**: Address filtering (accept frames for this address or broadcast)

**Post-Collapse Approach**:
- Salvage NICs and switches (abundant)
- Make cables (easy with tools)
- Once salvage depleted, build discrete Ethernet controllers
- 10 Mbps achievable with modest electronics
- 100+ Mbps requires faster logic (use salvaged ICs or custom ASICs when capable)

### WiFi (Wireless LAN)

**Principle**: Radio waves for local networking
- No wires needed
- Mobile devices
- Based on IEEE 802.11 standard

**Frequency Bands**:
- 2.4 GHz: Longer range, more interference
- 5 GHz: Shorter range, less interference, more bandwidth
- 6 GHz (WiFi 6E): Even more bandwidth

**Modulation**:
- Early: DSSS (Direct Sequence Spread Spectrum), FHSS (Frequency Hopping)
- Modern: OFDM (Orthogonal Frequency Division Multiplexing)

**Modes**:
- **Infrastructure**: Access point (AP) coordinates
- **Ad-hoc**: Peer-to-peer, no AP

**Security**:
- WEP: Broken (don't use)
- WPA: Better
- WPA2/WPA3: Current standard (strong encryption)

**Building WiFi**:
- Requires RF design expertise
- Complex modulation (OFDM needs DSP)
- Salvage priority: High (WiFi chips cheap and common)
- Manufacturing: Very difficult until advanced IC capability

### Other LAN Technologies

**Token Ring** (IBM, 1980s):
- Ring topology
- Token passing (avoids collisions)
- 4 or 16 Mbps
- Largely replaced by Ethernet

**FDDI** (Fiber Distributed Data Interface):
- 100 Mbps fiber ring
- Dual ring for redundancy
- Expensive, mostly in backbones
- Replaced by Fast/Gigabit Ethernet

**Serial Link (Point-to-Point)**:
- RS-232, RS-485: Simple serial
- Speeds: 300 bps to 115 kbps (RS-232)
- Short distances (15 meters typical for RS-232)
- Or use modems over longer copper lines

## Wide Area Networks (WAN)

### Telephone Network (Circuit-Switched)

**Historical Backbone**: Voice telephone system

**PSTN** (Public Switched Telephone Network):
- Circuit-switched: Dedicated path for duration of call
- Analog (originally) or digital (later)
- Hierarchical: Local exchanges, trunk exchanges, international exchanges

**Components**:
- **Local loop**: Customer to central office (copper pair)
- **Central office (CO)**: Switch connecting local customers
- **Trunk lines**: Between COs, carry many calls (multiplexed)
- **Long distance**: Higher-level switching

**Using for Data**:
- **Modem** (Modulator-Demodulator): Converts digital to audio tones
  - Early: 300 bps
  - Later: 1200, 2400, 9600, 14.4k, 28.8k, 33.6k, 56k bps
  - Modulation: FSK, PSK, QAM
- **Leased line**: Dedicated circuit (not switched)
  - T1 (US): 1.544 Mbps
  - E1 (Europe): 2.048 Mbps

**Digital Telephone**:
- **ISDN** (Integrated Services Digital Network): 64-128 kbps
- **DSL** (Digital Subscriber Line): 1-100 Mbps over existing phone lines

**Building Modems**:
- Generate audio tones (FSK: frequency shift keying)
  - Mark (1): One frequency (e.g., 1200 Hz)
  - Space (0): Another frequency (e.g., 2200 Hz)
- Detect tones: Bandpass filters and comparators
- Early: Simple, 300 bps achievable with basic electronics
- Later: Complex (QAM requires DSP), 9600+ bps difficult without ICs

**Post-Collapse**: Modems useful if telephone infrastructure intact or rebuilt

### Packet-Switched Networks

**Principle**: Data divided into packets, routed independently

**Advantages**:
- Efficient (shared bandwidth)
- Flexible (route around failures)
- Scalable

**X.25** (Early Packet Network, 1970s):
- Connection-oriented
- Error recovery at every hop
- Slow but reliable
- Used in early internet and banking

**Frame Relay** (1990s):
- Simpler than X.25
- Error detection only (not correction)
- Faster

**ATM** (Asynchronous Transfer Mode, 1990s):
- Fixed-size cells (53 bytes)
- Quality of Service (QoS) guarantees
- Complex, expensive
- Used in telecom backbones

**Post-Collapse**: Start simple. Build on concepts, but don't replicate complexity of pre-collapse networks initially.

### Fiber Optic Links

**Principle**: Light pulses through glass fiber

**Advantages**:
- Extremely high bandwidth (Gbps to Tbps)
- Long distance without repeaters (50-100 km+)
- Immune to electromagnetic interference
- Secure (hard to tap)

**Components**:
- **Fiber**: Glass core, cladding (different refractive index causes total internal reflection)
  - Single-mode: Small core (8-10 µm), laser source, long distance
  - Multi-mode: Larger core (50-62.5 µm), LED source, shorter distance
- **Transmitter**: LED or laser diode converts electrical to light
- **Receiver**: Photodiode converts light to electrical
- **Connectors**: SC, LC, ST (precision alignment needed)

**Making Fiber**:
- Draw glass to precise diameter (complex)
- Purity and refractive index control critical
- Difficult to manufacture, but can salvage extensively

**Post-Collapse**:
- Salvage fiber optic cables from 2025 (telecoms, data centers)
- Fiber lasts decades if not physically damaged
- Transceivers (lasers, photodiodes) may fail, but can be replaced
- Indigenous fiber manufacturing: Very difficult, late-stage

## Internet Protocol Suite (TCP/IP)

### Why TCP/IP Matters

**Universal Standard**: By 2025, virtually all networks used TCP/IP
- Simple and flexible
- Open standard (not proprietary)
- Well-documented
- Proven at global scale

**Post-Collapse**: Use TCP/IP. Don't invent new protocols. Extensive documentation exists.

### IP (Internet Protocol) - Layer 3

**Purpose**: Route packets between networks

**IPv4 Address**: 32 bits (4 bytes)
- Notation: 192.168.1.1 (dotted decimal)
- Each number: 0-255
- Total: 4.3 billion addresses

**IPv6 Address**: 128 bits (16 bytes)
- Notation: 2001:0db8:85a3:0000:0000:8a2e:0370:7334 (hexadecimal)
- Total: 340 undecillion addresses
- Developed because IPv4 addresses running out

**IP Packet Format** (IPv4, simplified):
```
Version (4 bits): IPv4 = 4
Header Length (4 bits)
Type of Service (8 bits)
Total Length (16 bits): Packet size
Identification (16 bits): For fragmentation
Flags + Fragment Offset (16 bits)
Time to Live (8 bits): Hop limit
Protocol (8 bits): TCP=6, UDP=17, ICMP=1
Header Checksum (16 bits)
Source IP Address (32 bits)
Destination IP Address (32 bits)
Options (variable)
Data (variable, up to 65,535 bytes total)
```

**Routing**:
- Each router examines destination IP
- Consults routing table
- Forwards to next hop toward destination

**Subnetting**: Dividing IP address space
- Network portion + Host portion
- Subnet mask: Indicates division
  - Example: 255.255.255.0 (/24) → First 24 bits network, last 8 bits host
  - Network: 192.168.1.0/24 → Addresses 192.168.1.0 to 192.168.1.255

**Private Address Ranges** (Not routed on public internet):
- 10.0.0.0/8 (10.x.x.x)
- 172.16.0.0/12 (172.16.x.x to 172.31.x.x)
- 192.168.0.0/16 (192.168.x.x)

**Use for Local Networks**: No coordination needed, unlimited private addresses

### ICMP (Internet Control Message Protocol)

**Purpose**: Error messages and diagnostics

**Ping**: Echo request/reply (test connectivity)

**Traceroute**: Discover path to destination

**Error messages**: Destination unreachable, time exceeded, etc.

### TCP (Transmission Control Protocol) - Layer 4

**Purpose**: Reliable, ordered delivery

**Features**:
- **Connection-oriented**: Three-way handshake to establish connection
- **Reliable**: Retransmits lost packets
- **Ordered**: Delivers data in order sent
- **Flow control**: Prevents overwhelming receiver
- **Congestion control**: Backs off when network congested

**TCP Segment Format** (simplified):
```
Source Port (16 bits)
Destination Port (16 bits)
Sequence Number (32 bits): Position of this data in stream
Acknowledgment Number (32 bits): Next expected byte
Flags (9 bits): SYN, ACK, FIN, RST, PSH, URG, etc.
Window Size (16 bits): Flow control
Checksum (16 bits)
Options (variable)
Data (variable)
```

**Three-Way Handshake** (Connection Establishment):
1. Client → Server: SYN (Synchronize)
2. Server → Client: SYN-ACK (Synchronize-Acknowledge)
3. Client → Server: ACK (Acknowledge)

**Connection Termination**:
1. Client → Server: FIN (Finish)
2. Server → Client: ACK
3. Server → Client: FIN
4. Client → Server: ACK

**Ports**: 16-bit numbers identify applications
- Well-known ports (0-1023): HTTP=80, HTTPS=443, SMTP=25, SSH=22, FTP=20/21
- Registered ports (1024-49151)
- Dynamic ports (49152-65535)

**Uses**: Web browsing, email, file transfer, SSH, most reliable communication needs

### UDP (User Datagram Protocol) - Layer 4

**Purpose**: Simple, unreliable, fast delivery

**Features**:
- **Connectionless**: No handshake
- **Unreliable**: No retransmission
- **Unordered**: Packets may arrive out of order
- **Fast**: Less overhead than TCP

**UDP Datagram Format**:
```
Source Port (16 bits)
Destination Port (16 bits)
Length (16 bits)
Checksum (16 bits)
Data (variable)
```

**Uses**:
- DNS (Domain Name System)
- Streaming media (video, voice) where speed > reliability
- Simple query-response (where app handles retries)
- Gaming (low latency critical)

### Application Layer Protocols

**HTTP** (Hypertext Transfer Protocol):
- Web pages
- Request-response model
- Methods: GET (retrieve), POST (submit data), PUT, DELETE, etc.

**HTTPS**: HTTP over TLS/SSL (encrypted)

**SMTP** (Simple Mail Transfer Protocol):
- Sending email
- Server-to-server transfer

**POP3** (Post Office Protocol):
- Receiving email
- Downloads from server to client

**IMAP** (Internet Message Access Protocol):
- Receiving email
- Leaves mail on server, manages remotely

**FTP** (File Transfer Protocol):
- Transfer files
- Separate control and data connections

**SSH** (Secure Shell):
- Encrypted remote login
- Replaces insecure Telnet

**DNS** (Domain Name System):
- Translates names (www.example.com) to IP addresses (93.184.216.34)
- Hierarchical, distributed database
- Critical for user-friendly internet

**DHCP** (Dynamic Host Configuration Protocol):
- Automatically assigns IP addresses to devices
- Simplifies network management

## Building an Internet

### Small-Scale Internet (Single Community)

**Components**:

**1. Computers** (Nodes):
- With network interfaces (Ethernet, WiFi)
- Running TCP/IP stack

**2. Switches/Hubs**:
- Connect computers in local network

**3. Router**:
- Connects multiple networks
- Routes packets between them
- Can be dedicated device or computer with multiple NICs

**4. Servers**:
- **Web server**: Hosts websites (Apache, Nginx, or custom)
- **Email server**: SMTP, POP3/IMAP
- **File server**: Stores shared files (FTP, SMB/CIFS, NFS)
- **DNS server**: Name resolution
- **DHCP server**: IP address assignment

**5. Cabling**:
- Ethernet cables
- Or wireless (WiFi access points)

**Example Setup**:
```
Users—[Switch]—[Router]—[Servers]
                  |
          [Internet/WAN connection]
```

**Configuration**:
- Assign IP address range (e.g., 192.168.1.0/24)
- Set up DHCP server to assign addresses automatically
- Configure DNS (or use external)
- Set up servers (web, email, etc.)
- Configure router (routing tables, NAT if needed)

### Medium-Scale (Multiple Communities, Regional)

**Interconnection Methods**:

**Point-to-Point Links**:
- Fiber optic (if available)
- Radio links (microwave, 2.4/5 GHz)
- Leased lines (if telephone network exists)

**Routing**:
- Static routes (manual configuration)
- Or dynamic routing protocols:
  - **RIP** (Routing Information Protocol): Simple, distance-vector
  - **OSPF** (Open Shortest Path First): Link-state, faster convergence
  - **BGP** (Border Gateway Protocol): Used between autonomous systems

**Example**:
```
Community A [Router A]—Radio Link—[Router B] Community B
                |                       |
         [Community A LAN]       [Community B LAN]
```

**Challenges**:
- Ensuring reliability (redundant paths)
- Managing addressing (coordinate IP ranges)
- Maintaining equipment (spare parts, power)

### Large-Scale (Inter-Regional, Continent-Wide)

**Backbone**:
- High-capacity links (fiber optic primarily)
- Redundant paths (mesh topology)
- Multiple ISPs or regional networks

**Peering**:
- Networks exchange traffic directly
- Peering points (Internet Exchange Points, IXPs)

**Hierarchy**:
- Tier 1: Global backbone (no transit fees, only peering)
- Tier 2: Regional networks (buy transit from Tier 1, peer with each other)
- Tier 3: Local ISPs (buy transit from Tier 2)

**BGP Routing**:
- Each autonomous system (AS) has unique number
- BGP exchanges routing information between ASes
- Policy-based routing (choose paths based on business relationships)

**Challenges**:
- Coordination across many organizations
- Security (DDoS attacks, BGP hijacking)
- Scalability (millions of routes)

**Post-Collapse Reality**:
- Start small (community-level)
- Expand gradually (regional)
- Large-scale internet may take 50-100 years
- Leverage salvaged fiber, radio equipment

## Implementing TCP/IP Stack

### Software Layers

**Options**:
1. **Use existing stack**: Linux, BSD, Windows have mature TCP/IP stacks
   - If you have computers running these OSes, you're done
2. **Port existing stack**: lwIP (lightweight IP) is open source, designed for embedded systems
3. **Write your own**: Educational, but enormous effort

**Writing Your Own** (If You Must):

**Layer 2 (Ethernet)**:
- Driver for NIC
- Frame assembly/disassembly
- CRC calculation and checking
- MAC address filtering

**Layer 3 (IP)**:
- Packet assembly/disassembly
- Header checksum
- TTL handling
- Fragmentation and reassembly (if needed)
- Routing table lookup
- Forwarding or local delivery decision

**Layer 4 (TCP)**:
- Segment assembly/disassembly
- Checksum calculation
- Sequence number management
- Acknowledgment tracking
- Retransmission timers
- Window management (flow control)
- Connection state machine

**Layer 4 (UDP)**:
- Simpler than TCP
- Datagram assembly/disassembly
- Checksum

**Application Layer**:
- Sockets API (for applications to use TCP/UDP)
- Protocol implementations (HTTP, SMTP, etc.)

**Effort**: Thousands of hours for basic stack. Years for full-featured, robust stack.

**Recommendation**: Use existing, well-tested software. If writing from scratch is required (for education or custom hardware), study existing implementations (lwIP source code, RFCs).

## Services and Applications

### Web Server

**Purpose**: Serve HTML pages and other content via HTTP

**Simple Web Server**:
1. Listen on port 80 (HTTP)
2. Accept TCP connection
3. Read HTTP request (e.g., GET /index.html)
4. Parse request
5. Find requested file
6. Send HTTP response:
   ```
   HTTP/1.1 200 OK
   Content-Type: text/html
   Content-Length: 1234

   <html>...</html>
   ```
7. Close connection (or keep-alive for multiple requests)

**Building Web Server**:
- Language: C, Python, or any language with socket support
- Minimal: <500 lines of code
- Full-featured (Apache, Nginx): hundreds of thousands of lines

**Static Content**: Serve files from disk
**Dynamic Content**: Run scripts (CGI, PHP, Python, etc.) to generate pages

### Email System

**Components**:
- **MUA** (Mail User Agent): User's email program (Thunderbird, Outlook, etc.)
- **MTA** (Mail Transfer Agent): Server that relays mail (Sendmail, Postfix, Exim)
- **MDA** (Mail Delivery Agent): Delivers to user's mailbox

**Protocols**:
- **SMTP** (port 25): Sending and server-to-server relay
- **POP3** (port 110): Retrieve email, download-and-delete model
- **IMAP** (port 143): Retrieve email, keeps mail on server

**Setting Up Email**:
1. Install MTA (Postfix recommended for simplicity and security)
2. Configure domains, users, authentication
3. Set up MUA on client machines
4. Test sending and receiving

**Challenges**:
- Spam filtering (post-collapse, less of an issue initially)
- Security (authentication, encryption)
- Reliability (queue management, retries)

### DNS (Domain Name System)

**Purpose**: Translate names to IP addresses

**Hierarchical**:
- Root servers (.)
- Top-level domains (TLD): .com, .org, .net, country codes (.uk, .us, etc.)
- Second-level domains: example.com
- Subdomains: www.example.com, mail.example.com

**Record Types**:
- **A**: Name → IPv4 address
- **AAAA**: Name → IPv6 address
- **MX**: Mail exchange (where to send email for domain)
- **CNAME**: Canonical name (alias)
- **NS**: Nameserver (authoritative server for zone)
- **PTR**: Reverse lookup (IP → name)

**Running DNS Server**:
- Software: BIND, dnsmasq, PowerDNS, etc.
- Configure zones (list of records)
- Recursive resolver (queries other servers on behalf of clients)
- Authoritative server (answers for domains you own)

**Post-Collapse**:
- May not have access to root DNS servers
- Set up local root and TLDs
- Coordinate domain allocation within network

### File Sharing

**FTP** (File Transfer Protocol):
- Simple, old, insecure (passwords in clear text)
- Use SFTP (SSH File Transfer Protocol) or FTPS (FTP over TLS) instead

**SMB/CIFS** (Windows File Sharing):
- Samba (Linux implementation)
- Easy for Windows users

**NFS** (Network File System, Unix/Linux):
- Simple, efficient
- Less common on Windows

**HTTP/HTTPS**:
- Can serve files via web server
- Ubiquitous (every device has web browser)

### Voice and Video

**VoIP** (Voice over IP):
- SIP (Session Initiation Protocol): Signaling (set up calls)
- RTP (Real-time Transport Protocol): Media transport
- Codecs: G.711, G.729, Opus

**Video Conferencing**:
- Similar to VoIP but video + audio
- More bandwidth
- H.264, VP8/VP9, AV1 codecs

**Challenges**:
- Real-time requirements (low latency)
- Bandwidth
- Quality of Service (QoS)

**Post-Collapse**: VoIP can replace telephone network (if IP network more reliable)

## Network Security

### Threats

**Eavesdropping**: Intercept communications
**Man-in-the-Middle**: Intercept and modify
**Denial of Service** (DoS): Overwhelm system with traffic
**Intrusion**: Unauthorized access to systems
**Malware**: Viruses, worms, trojans

### Defenses

**Encryption**:
- **Symmetric**: AES, ChaCha20 (fast, same key for encrypt/decrypt)
- **Asymmetric**: RSA, ECC (slow, different keys for encrypt/decrypt, used for key exchange)
- **TLS/SSL**: Encrypts connections (HTTPS, SMTPS, etc.)
- **VPN**: Encrypts all traffic between sites or users and network

**Authentication**:
- Passwords (weak, but simple)
- Public key (SSH keys)
- Certificates (PKI - Public Key Infrastructure)
- Multi-factor authentication (password + something else)

**Firewall**:
- Filter traffic by IP, port, protocol
- Block unwanted connections
- Allow only authorized traffic

**Intrusion Detection/Prevention** (IDS/IPS):
- Monitor for suspicious activity
- Alert or block

**Software Updates**:
- Patch vulnerabilities
- Post-collapse: May lack vendor updates, so must maintain and patch yourself

**Best Practices**:
- Principle of least privilege (minimal access needed)
- Defense in depth (multiple layers)
- Monitoring and logging
- Regular audits and testing

## Practical Steps to Rebuild Networking

### Phase 1: Local Networks (Year 1-5)

1. Salvage network equipment (NICs, switches, routers, cables)
2. Set up small LANs in key locations (power plant, workshop, hospital, etc.)
3. Connect computers, share files
4. Set up intranet (local websites, email, etc.)

### Phase 2: Inter-Community Links (Year 5-15)

1. Establish point-to-point links (radio, fiber if available)
2. Connect communities
3. Set up routing (static or simple dynamic)
4. Expand services (shared databases, communications, etc.)

### Phase 3: Regional Network (Year 15-30)

1. Build out backbone (fiber preferred, radio backup)
2. Establish multiple paths (redundancy)
3. Set up formal routing (OSPF or BGP)
4. Coordinate IP addressing
5. Services: Regional web, email, VoIP, etc.

### Phase 4: Wide-Area Internet (Year 30+)

1. Interconnect regions
2. Establish governance (who manages root DNS, IP allocation, etc.)
3. Robust redundancy
4. Advanced services (cloud storage, distributed computing, etc.)

## Summary: Networking Development Stages

**Stage 1 (Year 0-10): Isolated Computers**
- Individual computers or small clusters
- Sneakernet (physical media transfer)
- Point-to-point serial links

**Stage 2 (Year 10-20): Local Networks**
- Ethernet LANs
- Simple routers
- Local servers (file, web, email)
- Community-scale

**Stage 3 (Year 20-40): Regional Networks**
- Inter-community links (radio, fiber)
- Routing protocols
- Coordinated addressing
- Regional services
- 10s to 100s of communities

**Stage 4 (Year 40-60): Wide-Area Networks**
- Long-distance fiber and microwave
- Hierarchical routing (BGP)
- Thousands of sites
- Continent-scale

**Stage 5 (Year 60-100+): Global Internet**
- Worldwide connectivity
- Robust, redundant
- Billions of devices
- Approaching pre-collapse capability

## Final Thoughts

Networks multiply the value of computers. One computer is useful. A hundred networked computers are transformative. A million are civilization-changing.

**Prioritize**:
1. Salvage existing equipment
2. Build local networks early
3. Expand methodically
4. Document protocols and standards
5. Train network engineers
6. Establish governance early (prevents conflicts over addressing, routing, policy)

The internet is humanity's most powerful tool for coordination and knowledge sharing. Rebuilding it should be a top priority. Every community that reconnects makes the entire network more valuable.

**Key Principle**: Networks are about cooperation. Technical standards (like TCP/IP) enable technical cooperation. Social structures (governance, coordination, trust) enable the human cooperation that makes networks useful. Build both.
