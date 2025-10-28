## **Types of Architecture**

- Network architecture defines the **framework and design principles** governing how computing devices interact, communicate, and share resources within a network.
- It encompasses physical and logical layout, protocols, transmission technologies, and roles assigned to devices

## **# 1. Client-Server Architecture**

- **Definition:** A centralized model where multiple client devices (users) request services, and one or more dedicated server machines provide those services.
- **Characteristics:**
    - Centralized control over resources and data.
    - Servers host files, applications, databases, etc.
    - Clients initiate communication; servers respond.
- **Advantages:**
    - Centralized security, updates, and administration.
    - Scalable with dedicated infrastructure.
    - Data integrity and backup are easier to manage.
- **Disadvantages:**
    - Single point of failure—server downtime affects all clients.
    - Higher cost due to server infrastructure and maintenance.
    - Network congestion possible under high client load.
- **Use Cases:** Web services, enterprise applications, online banking, DNS, email servers.

## **# 2. Peer-to-Peer (P2P) Architecture**

- **Definition:** A decentralized model where each device (peer) acts both as a client and a server, sharing resources directly with other peers.
- **Characteristics:**
    - No central authority or dedicated server.
    - Devices connect and share files/services autonomously.
    - Often implemented using ad hoc connections.
- **Advantages:**
    - Cost-effective with no need for central servers.
    - Scalable in small to medium environments.
    - Resilient—failure of one node does not disrupt the whole network.
- **Disadvantages:**
    - Lack of centralized control and security.
    - Difficult to manage and maintain at scale.
    - Performance degradation with increased peers and resource requests.
- **Use Cases:** File sharing systems (e.g., BitTorrent), blockchain networks, LAN-based collaboration tools.

## **# 3. Hybrid Architecture**

- **Definition:** A flexible model that combines characteristics of both Client-Server and P2P architectures, typically used to optimize performance, scalability, and control.
- **Characteristics:**
    - Critical services run on centralized servers.
    - Less critical or user-based services shared peer-to-peer.
    - Often supports layered architectures with both types coexisting.
- **Advantages:**
    - Balanced control and resource distribution.
    - Enhanced scalability and fault tolerance.
    - Flexible deployment across varied network environments.
- **Disadvantages:**
    - Increased architectural complexity.
    - Requires sophisticated coordination mechanisms.
    - Can be harder to secure and maintain consistency.
- **Use Cases:** Modern cloud systems, collaborative enterprise tools, content distribution networks (CDNs).

## **# 4. Tiered Architecture (Multi-tier / N-tier)**

- **Definition:** An extension of Client-Server architecture where functionality is separated into layers (tiers), each responsible for a specific concern (e.g., presentation, business logic, data storage).
- **Typical Tiers:**
    - **Presentation Tier:** User interface (web/mobile clients)
    - **Logic Tier:** Application or business logic server
    - **Data Tier:** Database or file server
- **Advantages:**
    - Modularity and separation of concerns.
    - Easier scalability and maintenance.
    - Enhanced security—tiers can be independently secured.
- **Disadvantages:**
    - Increased latency due to inter-tier communication.
    - More complex deployment and monitoring.
    - Dependency on robust integration between layers.
- **Use Cases:** Web applications, enterprise-grade software, banking systems.

## **# 5. Service-Oriented Architecture (SOA)**

- **Definition:** A loosely coupled architecture where independent services communicate over a network to perform business functions, typically using standardized interfaces and protocols.
- **Characteristics:**
    - Services are platform-independent and reusable.
    - Communication is typically over HTTP, XML, or JSON.
    - Strong emphasis on interoperability and modularity.
- **Advantages:**
    - High reusability and maintainability.
    - Enables rapid integration of heterogeneous systems.
    - Scalability across distributed environments.
- **Disadvantages:**
    - Higher overhead due to protocol stack.
    - Latency and complexity in orchestrating multiple services.
    - Security management is more challenging across distributed services.
- **Use Cases:** Web services, enterprise service buses (ESBs), microservices-based applications.

## **# 6. Cloud-Based Architecture**

- **Definition:** A virtualized architecture where computing resources (compute, storage, applications) are delivered as services over the internet or private networks.
- **Models:**
    - **IaaS:** Infrastructure as a Service (e.g., AWS EC2)
    - **PaaS:** Platform as a Service (e.g., Google App Engine)
    - **SaaS:** Software as a Service (e.g., Salesforce, Gmail)
- **Advantages:**
    - On-demand resource availability.
    - Cost-efficient with pay-as-you-go models.
    - High scalability, reliability, and global accessibility.
- **Disadvantages:**
    - Vendor lock-in risks.
    - Security and compliance concerns.
    - Requires stable internet connectivity.
- **Use Cases:** Scalable web apps, backup and disaster recovery, enterprise digital transformation.

## **# Summary Table**

| **Architecture** | **Definition** | **Characteristics** | **Advantages** | **Disadvantages** | **Use Cases** |
| --- | --- | --- | --- | --- | --- |
| Client-Server | Centralized model where clients request services from servers. | Centralized control, scalability with dedicated infrastructure. | Scalable, easy data integrity and backup management. | Single point of failure, higher cost due to server maintenance. | Web services, enterprise applications, online banking. |
| Peer-to-Peer (P2P) | Decentralized model where each device acts as both client and server. | No central authority or dedicated server, devices connect autonomously. | Cost-effective, scalable in small environments, resilient. | Lack of centralized control and security, difficult to manage at scale. | File sharing systems, blockchain networks, LAN-based collaboration tools. |
| Hybrid | Combines characteristics of Client-Server and P2P architectures. | Critical services run on central servers, less critical or user-based services shared peer-to-peer. | Balanced control and resource distribution, enhanced scalability and fault tolerance. | Increased architectural complexity, requires sophisticated coordination mechanisms. | Modern cloud systems, collaborative enterprise tools, content distribution networks (CDNs). |
| Tiered Architecture (Multi-tier / N-tier) | Separates functionality into layers or tiers for specific concerns. | Modularity, separation of concerns, easier scalability and maintenance. | Easier to maintain and scale, enhanced security through tier isolation. | Increased latency due to inter-tier communication, more complex deployment and monitoring. | Web applications, enterprise-grade software, banking systems. |
| Service-Oriented Architecture (SOA) | Loosely coupled architecture where services communicate over a network. | Services are platform-independent and reusable, strong emphasis on interoperability and modularity. | High reusability and maintainability, enables rapid integration of heterogeneous systems. | Higher overhead due to protocol stack, latency and complexity in orchestrating multiple services. | Web services, enterprise service buses (ESBs), microservices-based applications. |
| Cloud-Based Architecture | Virtualized architecture where computing resources are delivered as services over the internet or private networks. | On-demand resource availability, cost-efficient with pay-as-you-go models, high scalability and reliability. | Scalable, reliable, and globally accessible, on-demand resource availability. | Vendor lock-in risks, security and compliance concerns, requires stable internet connectivity. | Scalable web apps, backup and disaster recovery, enterprise digital transformation. |