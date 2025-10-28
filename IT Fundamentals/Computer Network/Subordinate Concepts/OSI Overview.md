## **Definition**

- The **OSI Model** is a **conceptual framework** that standardizes the functions of a telecommunication or computing system into **seven distinct layers**.
- It enables **interoperability** between different systems and guides the design of network protocols.

## **Overview**

| Layer | Name | Data Unit | Core Functions | Key Protocols  | Devices | Key Concepts | Limitations |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 7 | **Application** | Data | User interface, network services, API access, service delivery | HTTP, HTTPS, FTP, SMTP, DNS, SNMP, LDAP, Telnet, SSH | Browsers, Email clients, APIs, Apps | API, REST, SOA, content negotiation, session state | XSS, SQLi, CSRF, buffer overflow, auth flaws |
| 6 | **Presentation** | Data | Data translation, encryption, compression, formatting | SSL/TLS, MIME, JPEG, MPEG, ASCII, UTF-8, ASN.1 | TLS libraries, codecs, app logic | Serialization, encoding, encryption, interoperability | Insecure crypto, CRIME/BREACH, malformed inputs |
| 5 | **Session** | Data | Session control, dialog management, checkpoints | NetBIOS, RPC, SMB, PPTP, H.245 | OS session managers, app servers | Session tokens, stateful communication, rollback | Session hijacking/fixation, state exhaustion |
| 4 | **Transport** | Segments / Datagrams | Reliable or best-effort delivery, flow and error control | TCP, UDP, SCTP, DCCP | Firewalls, OS kernels, L4 load balancers | Ports, windowing, ACKs, congestion control, handshake | SYN flood, UDP flood, port scanning |
| 3 | **Network** | Packets | Routing, logical addressing, packet forwarding | IP (v4/v6), ICMP, IGMP, ARP, BGP, OSPF, RIP | Routers, L3 switches, gateways | IP addressing, subnetting, TTL, NAT, routing tables | IP spoofing, black holes, routing loops |
| 2 | **Data Link** | Frames | Framing, MAC addressing, error detection (CRC), media access | Ethernet, Wi-Fi, PPP, HDLC, VLANs | Switches, NICs, bridges, APs | MAC address, FCS, collision domains, VLAN tagging | MAC spoofing, Layer 2 loops, limited scalability |
| 1 | **Physical** | Bits | Transmission of raw bits over medium, signaling, voltage levels | IEEE 802.3, RS-232, DSL, USB, Bluetooth, Fiber | Cables, hubs, transceivers, repeaters | Bit rate, modulation, encoding, media types, signal strength | Physical tampering, EMI, attenuation |

# **Layer-by-Layer Breakdown**

## **Physical Layer**

### **Definition**

- The **Physical Layer** is the first layer of the OSI model. It deals with the **transmission and reception of raw binary data over a physical medium**. 
- This layer is **hardware-centric**, focused solely on electrical, mechanical, procedural, and functional means to activate and maintain physical links.

### **Functions**

- **Bit transmission**: Converts digital bits into electrical, light, or radio signals.
- **Physical topology**: Defines how devices are physically connected (bus, star, ring, etc.).
- **Line encoding and signaling**: Establishes methods like NRZ, Manchester encoding, etc.
- **Data rate control**: Sets transmission speed (bit rate).
- **Synchronization**: Ensures sender and receiver clocks are in sync.
- **Interface definitions**: Electrical/optical specifications (voltage, current, timing).
- **Medium specification**: Type of transmission medium (copper, fiber, wireless).

### **Devices**

- **Cables** (coaxial, twisted pair, fiber optic)
- **Hubs**
- **Repeaters**
- **Network Interface Cards (NICs)** – hardware portion
- **Modems** – partly

### **Protocols**

While the Physical Layer doesn’t have traditional protocols like higher layers, it uses **standards** from:

- **IEEE** (e.g., IEEE 802.3 for Ethernet)
- **ITU-T**
- **ANSI**
- **EIA/TIA** (e.g., RS-232 for serial communication)
- **SONET/SDH**

### **Data Unit**

- **Bits** (0s and 1s)

### **Key Concepts**

- **Bandwidth** – maximum rate of data transfer
- **Latency** – delay in data transmission
- **Throughput** – actual transmission rate
- **Noise & Attenuation** – signal degradation over distance
- **Modulation** – converting digital to analog (e.g., ASK, FSK, PSK)

### **Limitations**

- **Signal degradation** (attenuation)
- **Noise interference**
- **No error detection or correction**
- **Distance limitations**
- **No data structure awareness** – it’s unaware of frames, packets, or sessions

## **Data Link Layer**

### **Definition**

The **Data Link Layer** is responsible for **node-to-node communication** and ensures reliable data transfer across the **physical link**. It **frames data**, detects/corrects errors from the physical layer, and controls access to the shared medium.

### **Functions**

- **Framing**: Encapsulates raw bits from the Physical Layer into **frames**.
- **MAC (Media Access Control)**: Manages how devices access the medium (CSMA/CD in Ethernet).
- **LLC (Logical Link Control)**: Handles error checking, frame synchronization, and flow control.
- **Error Detection and Correction**: CRC, parity checks, and in some cases retransmission.
- **Flow Control**: Prevents a fast sender from overwhelming a slow receiver.
- **Addressing**: Uses **MAC addresses** for device identification.

### **Devices**

- **Switches**
- **Bridges**
- **Network Interface Cards (NICs)** – software/firmware portion
- **Access Points** (wireless MAC layer)

### **Protocols**

- **Ethernet (IEEE 802.3)**
- **Wi-Fi / WLAN (IEEE 802.11 MAC layer)**
- **PPP (Point-to-Point Protocol)**
- **HDLC (High-Level Data Link Control)**
- **Frame Relay**
- **ATM (partially Layer 2)**

### **Data Unit**

- **Frames**

### **Key Concepts**

- **MAC Addressing** – 48-bit globally unique identifiers for NICs
- **Collision Domains** – areas in which collisions can occur
- **Full-duplex vs. Half-duplex** – simultaneous send/receive vs. alternating
- **Frame Check Sequence (FCS)** – part of frame trailer for error checking
- **VLAN tagging** – Logical segmentation of Layer 2 networks (802.1Q)

### Limitations

- **No routing capabilities** – can’t move data across multiple networks
- **MAC spoofing** – security flaw where MAC addresses can be faked
- **Limited scalability** – broadcast domains can become congested
- **Layer 2 loops** – solved by STP (Spanning Tree Protocol), but dangerous without it


## **Network Layer**

### **Definition**

- The **Network Layer** is responsible for **end-to-end delivery across multiple networks**. 
- It handles **logical addressing**, **routing**, and **packet forwarding** between devices not directly connected.

This is the first layer with true **inter-networking capabilities**.

### **Functions**

- **Logical addressing**: Assigns and uses **IP addresses** (IPv4, IPv6).
- **Routing**: Determines optimal paths for data between source and destination.
- **Packet forwarding**: Moves packets from input to output across routers.
- **Fragmentation and reassembly**: Breaks large packets into smaller units to fit MTU.
- **Path selection**: Uses metrics like hop count, delay, bandwidth, or cost.
- **Traffic control and congestion avoidance**: Manages packet queueing and delivery quality.

### **Devices**

- **Routers**
- **Layer 3 switches**
- **Multilayer firewalls**
- **Gateways (partial operation)**

### **Protocols**

- **IP (Internet Protocol – IPv4, IPv6)**
- **ICMP (Internet Control Message Protocol)**
- **IGMP (Internet Group Management Protocol)**
- **ARP** (used in conjunction, though technically Layer 2/3 hybrid)
- **Routing protocols**:
    - **RIP (Routing Information Protocol)**
    - **OSPF (Open Shortest Path First)**
    - **EIGRP**
    - **BGP (Border Gateway Protocol)**

### **Data Unit**

- **Packets**

### **Key Concepts**

- **IP addressing and subnetting**
- **CIDR (Classless Inter-Domain Routing)**
- **Default gateway**
- **TTL (Time To Live)** – prevents infinite loops
- **NAT (Network Address Translation)**
- **Public vs. private IPs**
- **Route aggregation and summarization**

### **Limitations**

- **IP spoofing** – attacker fakes source IP
- **No guaranteed delivery** – IP is **connectionless and unreliable**
- **Routing loops and black holes**
- **Overhead from routing protocols**
- **Latency due to hop count**


## **Transport Layer**

### **Definition**

- The **Transport Layer** ensures **reliable or best-effort delivery of data** between two endpoints. It provides **end-to-end communication**, handles **segmentation/reassembly**, and manages **error control, flow control, and connection control**.
- It creates a **logical communication channel** between applications on different hosts.

### **Functions**

- **Segmentation and reassembly**: Breaks down large messages from upper layers into smaller **segments** or **datagrams** and reassembles them at the destination.
- **End-to-end communication**: Establishes and maintains logical connections between hosts.
- **Error detection and correction**: Verifies integrity of transmitted data using checksums.
- **Flow control**: Prevents fast sender from overwhelming a slow receiver (e.g., sliding window).
- **Congestion control**: Reacts to network congestion (TCP congestion avoidance algorithms).
- **Multiplexing/demultiplexing**: Uses **ports** to allow multiple communication streams per host.

### **Devices**

- **Firewalls** (stateful, Layer 4 inspection)
- **Load balancers** (L4 type)
- **Proxies** (depending on configuration)
- **Host operating systems** (manage transport logic)

### **Protocols**

- **TCP (Transmission Control Protocol)** – reliable, connection-oriented
- **UDP (User Datagram Protocol)** – fast, connectionless, best-effort
- **SCTP (Stream Control Transmission Protocol)** – hybrid model
- **DCCP (Datagram Congestion Control Protocol)** – experimental, for streaming

### **Data Unit**

- **Segments** (TCP)
- **Datagrams** (UDP)

### **Key Concepts**

- **Three-way handshake** – used by TCP to establish a connection
- **Port numbers** – identifies services (e.g., HTTP = port 80, DNS = port 53)
- **Reliable vs. Unreliable Transport**:
    - TCP: ordered, reliable, with error correction
    - UDP: unordered, fast, minimal overhead
- **Timeouts and retransmissions**
- **Windowing and acknowledgments**
- **Connection establishment, maintenance, termination**

### **Limitations**

- **TCP SYN flood** – denial-of-service attack exploiting TCP handshake
- **Port scanning** – reconnaissance attack surface for open services
- **UDP flooding** – consumes bandwidth and resources
- **Overhead** – TCP adds significant overhead for reliability
- **No encryption or security** – requires upper-layer protocols

## **Session Layer**

### **Definition**

- The **Session Layer** is responsible for **establishing, managing, and terminating sessions** between applications. 
- A **session** is a sustained, structured dialog between two systems.
- This layer maintains state and controls the **dialog flow**, ensuring orderly communication and enabling **synchronization**, **checkpointing**, and **recovery** of sessions.

### **Functions**

- **Session establishment, maintenance, and termination**: Initiates and closes logical connections between applications.
- **Dialog control**: Manages who can transmit and when (half-duplex, full-duplex).
- **Synchronization**: Inserts checkpoints for long data transfers, allowing rollback in case of failure.
- **Session recovery**: Resumes interrupted sessions from the last known state.
- **Authentication** (in some implementations): Verifies identity before session start.
- **Session token management**: Tracks active sessions using identifiers.

### **Devices**

Session logic is typically implemented in **software applications** or **APIs**, not hardware. Infrastructure devices don't generally operate at this layer.

- **Application servers**
- **Middleware platforms**
- **Operating system session managers**
- **Web servers with session support**

### **Protocols / Standards**

The Session Layer doesn’t have as many widely recognized standalone protocols, but several protocols incorporate session-layer functionality:

- **NetBIOS (Network Basic Input/Output System)**
- **RPC (Remote Procedure Call)**
- **PPTP (Point-to-Point Tunneling Protocol)**
- **SMB (Server Message Block)**
- **SQL sessions**
- **H.245 (used in multimedia sessions)**
- **TLS/SSL** (Session aspects handled here and at Layers 6/7)

### **Data Unit**

- **Data** (transparent to lower layers, no special unit)

### **Key Concepts**

- **Session ID / tokens**
- **Half-duplex / full-duplex session types**
- **Checkpoints and rollback**
- **Stateful communication**
- **Timeout and inactivity handling**

### **Limitations**

- **Session hijacking** – attacker impersonates a user by stealing session token
- **Session fixation** – attacker sets session ID before authentication
- **Session timeout misconfigurations** – can lead to security or usability issues
- **State explosion** – poor session tracking can exhaust system resources
- **Dependency on Application Layer for actual enforcement**

## **Presentation Layer**

### **Definition**

- The **Presentation Layer** is responsible for **data translation, transformation, and formatting** between the application and the transport layer. 
- It ensures that **data sent from one system can be read and understood by another**, regardless of differences in syntax, encoding, or data structure.
- This is the **“syntax layer”** of the OSI model.

### **Functions**

- **Data translation**: Converts data between application formats and the common formats used in transmission.
- **Data encoding/decoding**: Converts character sets (e.g., ASCII, EBCDIC, Unicode).
- **Data compression/decompression**: Optimizes bandwidth and performance.
- **Encryption/decryption**: Secures data in transit (confidentiality).
- **Serialization/deserialization**: Converts complex data structures to byte streams and vice versa.
- **Format negotiation**: Agrees on common data formats between communicating systems.

### **Devices**

Like Layer 5, this is mostly handled in **software applications** or **middleware**, not by dedicated hardware.

- **Application frameworks**
- **API libraries (e.g., TLS libraries)**
- **Cryptographic modules**
- **Codecs (e.g., audio/video encoding)**

### **Protocols**

While few protocols are strictly isolated to this layer, many incorporate or rely on Presentation Layer functionality:

- **TLS/SSL (Transport Layer Security / Secure Sockets Layer)** – encryption
- **MIME (Multipurpose Internet Mail Extensions)** – formatting email content
- **XDR (External Data Representation)**
- **ASN.1 (Abstract Syntax Notation One)** – used in SNMP, LDAP
- **JPEG, MP4, MPEG, GIF** – multimedia encoding
- **ASCII / Unicode / UTF-8** – character encoding standards

### **Data Unit**

- **Data** (still abstract; formatting applies to application-layer payloads)

### **Key Concepts**

- **Interoperability** – enables heterogeneous systems to communicate
- **Data abstraction** – separates data representation from application logic
- **Encoding schemas** – how data is structured and parsed
- **Security abstraction** – handles encryption before transmission

### **Limitations**

- **Insecure encoding** – leads to injection attacks (e.g., character set manipulation)
- **Weak or misconfigured encryption** – exploitable by attackers
- **Compression attacks** – e.g., CRIME/BREACH in TLS
- **Codecs can be exploited** – buffer overflows, malformed file parsing

## **Application Layer**

### **Definition**

- The **Application Layer** is the **topmost layer** of the OSI model. It provides **interfaces and services for user-facing applications to interact with the network**. 
- It enables software processes to communicate over a network, acting as the **entry and exit point for network data**.

This is where **end-user operations and network-aware applications** reside.

### **Functions**

- **User interface interaction**: Presents network services to applications and users.
- **Application-level protocols**: Executes protocols tailored to specific services (e.g., email, web browsing, file transfers).
- **Resource access**: Requests access to remote files, printers, systems.
- **Service advertisement and discovery**: Locates network resources and services.
- **Content delivery**: Serves data to the user (web, mail, media).
- **Authentication and authorization**: User identity verification and access control (can be implemented across Layers 5–7).

### **Devices**

Layer 7 is implemented entirely in **software**, specifically in applications that utilize the network:

- **Web browsers**
- **Email clients**
- **File transfer tools**
- **Database front-ends**
- **API clients**
- **Mobile apps with internet connectivity**

### **Protocols**

This layer hosts the most recognizable protocols:

- **HTTP / HTTPS** – web browsing
- **FTP / SFTP** – file transfers
- **SMTP / POP3 / IMAP** – email transmission and retrieval
- **DNS** – domain name resolution
- **SNMP** – network device monitoring
- **Telnet / SSH** – remote terminal access
- **REST / SOAP** – web services and APIs
- **LDAP** – directory access
- **NFS / SMB** – file sharing
- **RDP / VNC** – remote desktops

### **Data Unit**

- **Data** (pure application data)

### **Key Concepts**

- **Application interfaces (APIs)**
- **Content negotiation** (e.g., Accept headers in HTTP)
- **Application-aware firewalls and proxies**
- **User experience and session state**
- **Microservices and service-oriented architecture (SOA)**

### **Limitations**

- **Most exploited layer** – surface for application-level attacks
- **Common attacks**:
    - **SQL Injection**
    - **Cross-Site Scripting (XSS)**
    - **Cross-Site Request Forgery (CSRF)**
    - **Buffer overflows**
- **Data leakage** due to poor access control
- **Dependency on all lower layers** – any failure below can compromise functionality
