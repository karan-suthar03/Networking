# TCP/IP Model - Layers and their Functions

**What is TCP/IP?**
TCP/IP is the core networking model used on the Internet. It defines how data is created, sent, routed, received, and understood between devices.

TCP/IP is practical and used in real networks.
OSI is mainly a learning/reference model.

## TCP/IP Has 4 Layers

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

## Data Encapsulation

- Application Data
- TCP Segment
- IP Packet
- Ethernet Frame
