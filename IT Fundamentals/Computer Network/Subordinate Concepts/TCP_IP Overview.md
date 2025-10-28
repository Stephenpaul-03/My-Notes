## **Definition**

- The **TCP/IP model** is the **de facto framework** for all modern network communication.
- It defines a **layered abstraction** that enables interoperability across heterogeneous systems over the internet.
- It consists of **four conceptual layers**—each providing specific services to the layers above it and consuming services from the layers below.

## **Link Layer**

### **# Definition**

The **Link Layer** governs **data transmission between nodes** on the same physical or logical network. It encompasses hardware addressing, frame encapsulation, and direct node-to-node delivery.

**a.k.a. Network Interface / Network Access Layer**

### # **Primary Responsibilities**

- **Frame construction** and transmission
- **Hardware addressing** (MAC)
- **Error detection and correction** at the frame level (CRC, checksums)
- **Access to physical medium** (cabling, wireless signals)

### # **Key Technologies & Protocols**

- **Ethernet (IEEE 802.3)** – wired LAN communication
- **Wi-Fi (IEEE 802.11)** – wireless LAN communication
- **ARP (Address Resolution Protocol)** – resolves IP to MAC
- **PPP (Point-to-Point Protocol)** – serial link communication
- **DSL, FDDI, ATM, Frame Relay** – legacy WAN protocols
- **Switches and Network Interface Cards (NICs)** – operate here

**Note**: ARP is often ambiguously placed between Link and Internet layers; functionally, it resolves Layer 3 (IP) to Layer 2 (MAC).
## **Internet Layer**

### **# Definition**

The **Internet Layer** ensures **inter-network delivery of packets**, regardless of the underlying network structure. It introduces logical addressing and facilitates packet routing.

### # **Primary Responsibilities**

- **IP addressing (logical identification)**
- **Packet routing and forwarding**
- **Fragmentation and reassembly**
- **Error and diagnostic messaging**
- **Stateless transmission**

### **# Key Protocols**

- **IPv4 / IPv6** – packet delivery, addressing
- **ICMP (Internet Control Message Protocol)** – diagnostics (e.g., ping, traceroute)
- **IGMP (Internet Group Management Protocol)** – multicast group membership
- **IPSec (optional)** – encryption and authentication at the network layer
- **Routers** – operate at this layer

## **Transport Layer**

### **# Definition**

The **Transport Layer** establishes, maintains, and terminates **logical communication between endpoints**, supporting both reliable and best-effort data transfer.

## **# Primary Responsibilities**

- **Segmentation and reassembly** of application data
- **Port addressing** for multiplexed connections
- **Connection setup/teardown**
- **Flow control** (windowing, buffering)
- **Error recovery** (retransmission, acknowledgment)

## **# Key Protocols**

- **TCP (Transmission Control Protocol)** – reliable, ordered, connection-oriented
    - Flow control (Sliding Window)
    - Congestion control (AIMD, Fast Retransmit)
    - Three-way handshake (SYN, SYN-ACK, ACK)
- **UDP (User Datagram Protocol)** – lightweight, connectionless
    - No error correction, no sequencing
    - Used in time-sensitive applications (VoIP, DNS)

**Ports**: Range from 0–65535; classified into well-known (0–1023), registered (1024–49151), and dynamic/private (49152–65535).
## **Application Layer**

### **# Definition**

The **Application Layer** encompasses **all protocols and services** that provide direct **user-level interfaces** for network communication.

## **# Primary Responsibilities**

- **Application-level communication protocols**
- **User authentication, session control**
- **Data translation and formatting**
- **Encryption at application level (e.g., HTTPS)**

## **# Key Protocols**

- **HTTP/HTTPS** – web communication
- **FTP, SFTP, SCP** – file transfers
- **SMTP, IMAP, POP3** – email services
- **DNS** – domain name resolution
- **SSH, Telnet** – remote terminal access
- **SNMP** – network management
- **NTP** – time synchronization
- **DHCP** – dynamic IP address assignment
- **TLS/SSL** – application-layer encryption

## **Three Way Handshake**

![ChatGPT Image Jun 3, 2025, 09_43_42 AM.png](image%2018.png)

### **# **Connection Initiation****

- **SYN (Synchronize)**
- **Client → Server**
- The client sends a TCP segment with the **SYN flag set** and an initial **sequence number `x`**.
- Purpose: To request a connection and synchronize sequence numbers.

**Packet Details:**

- `SYN = 1`
- `Seq = x`
### **# **Acknowledgment and Response****

- **SYN-ACK (Synchronize-Acknowledge)**
- **Server → Client**
- The server responds with a TCP segment that:
    - Acknowledges the client’s request (`Ack = x + 1`)
    - Initiates its own connection using its own **sequence number `y`**.
- Both **SYN** and **ACK** flags are set.

**Packet Details:**

- `SYN = 1`, `ACK = 1`
- `Seq = y`, `Ack = x + 1`
### **# Final Confirmation**

- **ACK (Acknowledgment)**
- **Client → Server**
- The client sends back an acknowledgment confirming the server’s sequence number.
- Connection is now established. Both sides can begin data transmission.

**Packet Details:**

- `ACK = 1`
- `Seq = x + 1`, `Ack = y + 1`

**Note** : The image has a minor error in the last ACK (says Ack = y - 1 instead of y + 1). Correct form is Ack = y + 1. 
## **# **Summary****

| Step | Direction | Flags | Seq/Ack Values | Purpose |
| --- | --- | --- | --- | --- |
| 1 | Client → Server | SYN | Seq = x | Initiate connection |
| 2 | Server → Client | SYN + ACK | Seq = y, Ack = x + 1 | Acknowledge + Sync |
| 3 | Client → Server | ACK | Seq = x + 1, Ack = y + 1 | Confirm connection established |
## **Comparison with OSI Model**

| **TCP/IP Model** | **OSI Model (7-Layer)** | **Function** |
| --- | --- | --- |
| Application | Application, Presentation, Session | High-level communication protocols, user interaction |
| Transport | Transport | End-to-end data delivery, reliability |
| Internet | Network | Routing, logical addressing |
| Link | Data Link + Physical | Physical transmission, frame handling, MAC |

**OSI is a theoretical model; TCP/IP is practical and implemented. TCP/IP merges OSI’s top three layers and bottom two layers.**
