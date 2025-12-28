# What is the difference between Internet and Intranet?

**Internet:**
- A global public network connecting millions of devices worldwide
- Accessible by anyone with an internet connection
- Uses public IP addresses
- No single owner
- Security is less controlled
- Examples: Google, YouTube, Email, Cloud services

**Intranet:**
- A private network within an organization
- Accessible only to authorized users
- Uses private IP addresses
- Owned and managed by an organization
- More secure and faster than the Internet
- Examples: Company HR portal, Internal websites, File servers



# What is Client–Server Model?

The Client–Server model is a network architecture where a client requests services or data and a server processes the request and sends back a response over a network.

- **Client:** Initiates requests (e.g., web browser, mobile app)
- **Server:** Listens, processes requests, serves multiple clients

**Communication Flow:**
- Client → Request (HTTP over TCP/IP) → Server → Response → Client



# What is a Packet?

**Definition:**
A packet is a small unit of data that is transmitted over a network. Networks do not send complete files or messages at once. Instead, data is divided into many small packets, sent separately, and reassembled at the destination.

**Why Packets Are Used:**
- Efficient data transmission
- Faster communication
- Only lost packets are retransmitted
- Multiple users can share the same network

**Packet Structure:**
A packet consists of three main parts:

1. **Header**
   - Source IP address
   - Destination IP address
   - Sequence number
   - Protocol information (TCP or UDP)

2. **Payload**
   - Actual data (part of a file, message, video, etc.)

3. **Trailer**
   - Error detection information (checksum)

**Packet Characteristics:**
- Packets may travel through different paths
- Packets may arrive out of order
- Packets can be lost
- TCP ensures retransmission and correct ordering

# What is a NODE?

**Definition:**
- A node is any device that can send, receive, or forward data in a network.
- If a device participates in communication, it is considered a node.

**Types of Nodes:**

1. **End Node**
   - Final sender or receiver of data
   - Example: laptop, mobile phone

2. **Intermediate Node**
   - Forwards packets between devices
   - Example: router, switch

# What is a LINK?

**Definition:**
A link is the communication medium that connects two nodes and allows packets to travel between them. Without links, nodes cannot communicate.

**Types of Links:**

1. **Wired Links:**
   - Ethernet cable
   - Fiber-optic cable

2. **Wireless Links:**
   - Wi-Fi
   - Bluetooth
   - Cellular networks (4G/5G)

**Signals Used in Links:**
- Electrical signals (copper cables)
- Light signals (fiber optics)
- Radio waves (wireless communication)

**Link Characteristics:**
- Bandwidth (data capacity)
- Latency (delay)
- Reliability (error rate)

# OSI Model - Layers and their Functions

**Layer 7 – Application**
- Provides network services to user applications like web browsing, email, and file transfer
- Protocols include HTTP, FTP, SMTP, and DNS

**Layer 6 – Presentation**
- Formats data so systems can understand it
- Handles encryption/decryption and compression

**Layer 5 – Session**
- Establishes, manages, and terminates communication sessions
- Keeps track of ongoing conversations between devices

**Layer 4 – Transport**
- Ensures end-to-end data delivery using ports
- Provides reliability (TCP) or fast, connectionless transfer (UDP)

**Layer 3 – Network**
- Handles logical addressing and routing using IP addresses
- Determines the best path for data packets

**Layer 2 – Data Link**
- Provides node-to-node delivery using MAC addresses
- Frames data and performs error detection

**Layer 1 – Physical**
- Transmits raw bits over physical media
IP ADDRESS HIERARCHY (TOP TO BOTTOM)


# IP Address Hierarchy
- **IANA** → Owns all global IP addresses
- **RIR (APNIC for India)** → Gets IP blocks from IANA
- **ISP (Jio, Airtel, etc.)** → Gets IPs from RIR
- **Router (Home/Office)** → Gets 1 public IP from ISP
- **Devices (Mobile, Laptop, TV)** → Get private IPs from router

**Flow:** IANA → RIR → ISP → Router → Devices

#### About 192.168.0.1

- 192.168.0.1 is a **PRIVATE IP**
- It is usually the **DEFAULT GATEWAY** (router IP)
- It does **NOT** decide how many devices can connect

#### Why People Say "255 Devices"

Most home networks use:
- Network: 192.168.0.0/24
- Subnet Mask: 255.255.255.0

**IP Breakdown:**
- 192.168.0.0 → Network ID (not usable)
- 192.168.0.1 → Router (Gateway)
- 192.168.0.2 → Device
- ...
- 192.168.0.254 → Device
- 192.168.0.255 → Broadcast (not usable)

**Total IPs:** 256
**Usable IPs:** 254

#### Important Rule

**Gateway IP does NOT decide device count**

**Subnet mask (/24) decides device count**

#### More Than 254 Devices?

Yes, by using a bigger subnet:
- /23 → 510 devices
- /16 → 65,534 devices

Example: 10.0.0.0/16

#### One-Line Summary

192.168.0.1 is just the router address.
Subnet size decides how many devices can connect.
# TCP/IP Model - Layers and their Functions

**What is TCP/IP?**
TCP/IP is the core networking model used on the Internet. It defines how data is created, sent, routed, received, and understood between devices.

TCP/IP is practical and used in real networks.
OSI is mainly a learning/reference model.

#### TCP/IP Has 4 Layers

**Application Layer**
- Closest to the user
- Creates and receives application data
- Handles communication between applications
- **Common protocols:** HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, DHCP
- **Data unit:** Message

**Transport Layer**
- Provides end-to-end communication
- Uses port numbers
- Handles reliability and flow control

**Protocols:**
- **TCP (Transmission Control Protocol)**
  - Reliable
  - Connection-oriented
  - Uses 3-way handshake
  - Ensures ordered delivery

- **UDP (User Datagram Protocol)**
  - Fast
  - Connectionless
  - No guarantee of delivery

- **Data unit:** Segment

**Internet Layer**
- Handles logical addressing and routing
- Moves data between different networks
- **Protocols:**
  - **IP** → Logical addressing
  - **ICMP** → Error messages and ping
  - **ARP** → Maps IP address to MAC address
- **Data unit:** Packet

**Network Access Layer**
- Handles physical transmission
- Uses MAC addresses
- Sends data over Ethernet or Wi-Fi
- **Technologies:** Ethernet, Wi-Fi, Fiber
- **Data unit:** Frame

#### Data Encapsulation

- Application Data
- TCP Segment
- IP Packet
- Ethernet Frame



# DNS Hierarchy - Who knows what?

**NO SINGLE SERVER KNOWS EVERYTHING**

**Root DNS Servers**
- Top of DNS hierarchy
- Know ONLY where TLD servers are
- **They know:**
  - .com → list of .com TLD servers
  - .org → list of .org TLD servers
  - .in → list of .in TLD servers
- **They DO NOT know:**
  - Domain names (google.com)
  - IP addresses
- **Purpose:** Answer: "Who handles this TLD?"

**TLD Servers (.com, .org, .in)**
- Middle layer of DNS
- **They know:**
  - Which authoritative DNS servers manage a domain
  - Example: google.com → ns1.google.com, ns2.google.com
- **They DO NOT know:**
  - Website IP addresses
- **Purpose:** Answer: "Who is authoritative for this domain?"

**Authoritative DNS Servers (Source of Truth)**
- Owned/configured by domain owner
- **They know:**
  - Actual DNS records:
    - A / AAAA → IP address
    - CNAME → alias
    - MX → mail server
  - Example: google.com → 142.250.x.x
- **Purpose:** Answer: "Here is the final IP address"

**Recursive DNS Resolvers (Google, Cloudflare)**
- Examples: 8.8.8.8, 1.1.1.1
- Not authoritative
- **They know:**
  - Cached DNS answers (temporary)
- **They do:**
  - Query Root → TLD → Authoritative
  - Cache results using TTL
  - Serve users quickly
- **They do NOT own:**
  - Domain information
- **Purpose:** Answer: "I will find the answer and remember it"

**Who is Authoritative?**
- Root → authoritative for TLD locations
- TLD → authoritative for domain → nameserver mapping
- Authoritative DNS → authoritative for actual IPs
- Recursive Resolver → NOT authoritative


































