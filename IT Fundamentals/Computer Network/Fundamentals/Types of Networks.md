## **1. Personal Area Network (PAN)**

- **Definition:** A small-scale network focused on an individual, typically connecting personal devices.
- **Working:** Devices communicate directly via Bluetooth, infrared, or USB interfaces for short-range, low-power data transfer.
- **Distance Covered:** ~1 to 10 meters.
- **Examples:** Smartwatch connected to a phone, Bluetooth headset, file transfer via IR or USB.
- **Advantages:**
    - Portable and easy to set up.
    - Minimal infrastructure required.
    - Energy-efficient communication.
- **Disadvantages:**
    - Very limited range and speed.
    - Prone to interference.
    - Weak security in public spaces.

## **2.Local Area Network (LAN)**

- **Definition:** A network confined to a building or small campus.
- **Working:** Connects multiple devices using switches and routers over Ethernet or Wi-Fi for high-speed internal communication.
- **Distance Covered:** Up to a few hundred meters (building scale).
- **Examples:** Office network, home Wi-Fi, school labs.
- **Advantages:**
    - High speed (100 Mbps to 10 Gbps).
    - Easy to deploy in contained spaces.
    - Cost-effective for small-scale use.
- **Disadvantages:**
    - Limited to a single site.
    - Can become complex with more users.
    - Susceptible to local failures or congestion.


## **3. Campus Area Network (CAN)**

- **Definition:** A network connecting multiple LANs within a limited geographical area such as a campus or military base.
- **Working:** Utilizes high-speed backbone (fiber/Ethernet) to interconnect LANs under unified control.
- **Distance Covered:** Up to several kilometers (organization-wide).
- **Examples:** University campuses, industrial parks.
- **Advantages:**
    - Centralized control of IT infrastructure.
    - High-speed intra-campus communication.
    - More economical than WAN for local clusters.
- **Disadvantages:**
    - Higher cost and complexity than LAN.
    - Needs experienced network administration.
    - Doesn’t scale well beyond the local region.

## **4. Metropolitan Area Network (MAN)**

- **Definition:** A high-speed network that spans a city or metro region.
- **Working:** Connects multiple LANs using fiber optics or wireless backhaul; often maintained by ISPs or consortiums.
- **Distance Covered:** 5–50 kilometers (city-level).
- **Examples:** City-wide public Wi-Fi, university inter-building networks.
- **Advantages:**
    - Enables shared access to city-wide services.
    - Economies of scale for institutions.
    - Supports centralized cloud/data services.
- **Disadvantages:**
    - Costlier than LAN/CAN.
    - Susceptible to metropolitan traffic congestion.
    - Requires complex routing and QoS policies.

## **5. Wide Area Network (WAN)**

- **Definition:** A network that spans across large geographic areas such as countries or continents.
- **Working:** Utilizes leased lines, satellite, fiber, or the Internet to connect remote LANs and MANs globally.
- **Distance Covered:** 100s to 1000s of kilometers (nationwide/global).
- **Examples:** The Internet, multinational enterprise networks.
- **Advantages:**
    - Global reach and remote access.
    - Facilitates distributed business operations.
    - Scalable for cloud and hybrid deployments.
- **Disadvantages:**
    - Expensive to build and maintain.
    - Latency and reliability issues due to distance.
    - High complexity in management and security.

## **6. Storage Area Network (SAN)**  

- **Definition:** A dedicated high-speed network for connecting servers to storage resources.
- **Working:** Bypasses regular network traffic by using protocols like Fibre Channel or iSCSI to deliver block-level storage access.
- **Distance Covered:** Typically within a data center or between two sites (up to 10 km in standard setups).
- **Examples:** Enterprise data centers, virtualization environments.
- **Advantages:**
    - Centralized, high-speed data access.
    - Improves server performance and scalability.
    - Supports backup and disaster recovery.
- **Disadvantages:**
    - Expensive hardware and licensing.
    - Requires expert configuration and redundancy planning.
    - Can be a single point of failure if poorly architected.


## **7. Enterprise Private Network (EPN)**

- **Definition:** A company-owned network used to securely interconnect branches and data centers.
- **Working:** Uses private infrastructure or dedicated leased circuits with custom routing, firewalls, and encryption.
- **Distance Covered:** Varies—can be national or global.
- **Examples:** Corporate backbone, inter-site MPLS networks.
- **Advantages:**
    - Full control over network security and policies.
    - Optimized for enterprise applications.
    - Lower long-term cost than public cloud.
- **Disadvantages:**
    - High upfront cost and maintenance overhead.
    - Requires in-house network engineering.
    - Slower to scale or adapt compared to cloud-native alternatives.


## **8. Virtual Private Network (VPN)**

- **Definition:** A secure overlay network built on top of a public network (like the internet).
- **Working:** Uses encrypted tunnels (IPSec, SSL) to securely route data from a remote user to a private network.
- **Distance Covered:** Effectively global (via the Internet).
- **Examples:** Remote employee access, secure site-to-site links.
- **Advantages:**
    - Extends internal networks to remote users.
    - High level of encryption and security.
    - Cost-effective compared to leased lines.
- **Disadvantages:**
    - Performance depends on ISP and internet quality.
    - Latency due to encryption/decryption.
    - Vulnerable to endpoint compromise or misconfiguration.


## **9. Software-Defined Wide Area Network (SD-WAN**

- **Definition:** A virtualized WAN architecture that dynamically routes traffic across multiple transport networks (MPLS, LTE, broadband) using centralized control and software-based policies.
- **Working:** Decouples the control plane from the data plane. Traffic is intelligently routed based on application, performance SLAs, and real-time link metrics, managed through a central orchestrator.
- **Distance Covered:** Regional to global—depends on underlying WAN transport.
- **Examples:** Cloud-first enterprises with multiple remote branches connected via broadband + LTE + MPLS, optimized via Cisco SD-WAN (Viptela).
- **Advantages:**
    - Intelligent, application-aware routing.
    - Cost reduction by offloading MPLS to broadband.
    - Centralized, policy-driven management.
    - Supports ZTP, security integration (e.g., SASE, IPSec).
- **Disadvantages:**
    - Initial integration complexity.
    - Requires investment in SD-WAN-capable hardware/software.
    - Dependency on underlying internet links for QoS-sensitive applications.

---

## **Consolidated Comparison Table**

| Network Type | Distance Covered | Ownership | Typical Use Case | Key Tech | Advantages | Disadvantages |
| --- | --- | --- | --- | --- | --- | --- |
| **PAN** | 1–10 meters | Individual | Wearables, phones | Bluetooth, USB | Easy setup, portable | Limited range and speed |
| **LAN** | Up to 500 meters | Organization | Offices, homes | Ethernet, Wi-Fi | High speed, low cost | Local scope only |
| **CAN** | Up to 5 km | Organization | Campus or business parks | Ethernet, fiber | Centralized resources | Requires planning, costly infra |
| **MAN** | 5–50 km | Multiple or ISP | City-wide networks | Fiber, WiMAX | Broader coverage | Costly setup |
| **WAN** | 100s–1000s km | Shared/Leased | Global business connectivity | MPLS, satellite | Global reach | High cost, latency |
| **SAN** | Up to 10 km | Enterprise | Data center storage | Fibre Channel, iSCSI | High throughput | High cost, complexity |
| **EPN** | Variable | Enterprise | Secure internal comms | MPLS, VPN | Custom security | Requires IT ops team |
| **VPN** | Global via Internet | Shared (logical) | Remote work, site-to-site | IPSec, SSL VPN | Secure, low cost | Performance varies |
| **SD-WAN** | Regional/Global | Enterprise | Cloud, hybrid WANs | vEdge, vSmart, ZTP | Dynamic routing, cost-efficient | Integration effort, link dependency |