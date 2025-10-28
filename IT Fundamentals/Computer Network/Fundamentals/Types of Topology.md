## **Types of Topology**

- Network topology refers to the arrangement or layout of different devices (nodes) in a network, defining how they are interconnected and how data flows between them.

## **# Point To Point Topology**

![image.png](image%209.png)

- **Definition:** Direct communication link between exactly two nodes, where one node acts as the sender and the other as the receiver.
- **Advantages:**
    - Provides dedicated bandwidth with minimal latency.
    - Simple and easy to implement for small-scale communication.
    - Secure due to the direct connection without intermediaries.
- **Disadvantages:**
    - Not scalable beyond two devices.
    - If the link fails, communication is entirely disrupted.
    - Inefficient for large networks due to lack of multi-node connectivity.

## **# Mesh Topology**

![image.png](image%2010.png)

- **Definition:** Every device is interconnected with every other device via dedicated communication links.
- **Advantages:**
    - High redundancy and fault tolerance; multiple alternate paths for data.
    - Superior reliability and resilience to node/link failures.
    - Enhanced security through direct device-to-device links.
    - Facilitates fast data transmission and effective fault diagnosis.
- **Disadvantages:**
    - Complex installation and configuration.
    - High initial cost due to cabling and ports.
    - Expensive to maintain and scale as the number of devices grows.
- Formulas
    - $The~total~number~of~ports~required = N * (N-1).$
    - $The~total~number~of~dedicated~links =~^NC_2~i.e.~ N(N-1)/2$
        - Where N is the Total Number of Devices Connected in the Mesh Topology

## **# Star Topology**

![image.png](image%2011.png)

- **Definition:** All devices are connected to a single central hub or switch. The hub acts as a repeater to facilitate communication.
- **Advantages:**
    - Easy to install and manage.
    - Centralized control improves fault detection and isolation.
    - Failure of one peripheral device does not affect the rest of the network.
    - Scalable by adding more devices to the hub.
- **Disadvantages:**
    - Central hub failure leads to complete network outage.
    - Requires more cabling than bus or ring topologies.
    - Performance depends on the capacity of the central hub.

## **# Bus Topology**

![image.png](image%2012.png)

- **Definition:** All nodes are connected to a single shared communication line (backbone).
- **Advantages:**
    - Simple and cost-effective for small networks.
    - Requires less cabling compared to star topology.
    - Easy to extend by adding devices along the bus.
- **Disadvantages:**
    - Single point of failure: backbone failure disrupts entire network.
    - Performance degrades as more devices are added.
    - Difficult to troubleshoot and isolate faults.
    - Data collisions are common, requiring robust collision management.

## **# Ring Topology**

![image.png](image%2013.png)

- **Definition:** Devices are connected in a circular fashion, with each node connected to exactly two neighbors. Data travels in one direction (unidirectional).
- **Advantages:**
    - Data packets travel at high speed with minimal collisions.
    - Simple fault isolation since data flows in a specific direction.
    - Predictable performance under consistent network load.
    - Can be enhanced to Dual Ring Topology (bidirectional) for redundancy.
- **Disadvantages:**
    - Failure of a single node or link can disrupt the entire network.
    - Troubleshooting and reconfiguring are complex.
    - Adding/removing devices requires temporary network downtime.

## **# Tree Topology**

![image.png](image%2014.png)

- **Definition:** A hierarchical topology combining characteristics of star and bus topologies. Multiple star-configured networks are connected to a linear bus backbone.
- **Advantages:**
    - Supports scalability and easy expansion.
    - Fault isolation is simpler compared to bus topology.
    - Supports centralized management while allowing segmented networks.
- **Disadvantages:**
    - Backbone failure affects the entire segment connected to it.
    - More cabling and complexity than simple star or bus topologies.
    - Maintenance cost increases with network size.

## **# Hybrid Topology**

![image.png](image%2015.png)

- **Disadvantages:**
    - Design and implementation complexity.
    - Potentially higher cost due to integration of multiple topology types.
    - Requires skilled network management.
- **Advantages:**
    - Highly flexible and scalable.
    - Leverages strengths of various topologies while mitigating individual weaknesses.
    - Facilitates optimized performance and fault tolerance.
- **Definition:** A combination of two or more different topologies (e.g., star-ring, star-bus) tailored to meet specific organizational needs.

## **# Summary Table**

| Topology | Definition | Advantages | Disadvantages |
| --- | --- | --- | --- |
| Bus | All nodes connected to a single shared communication line (backbone) | Simple and cost-effective, easy to extend by adding devices along the bus | Single point of failure, performance degrades as more devices are added, difficult to troubleshoot and isolate faults |
| Star | Central hub or switch connects all devices | Easy to install and manage, centralized control improves fault detection and isolation, scalable by adding more devices to the hub | Central hub failure leads to complete network outage, requires more cabling than bus topology, performance depends on central hub capacity |
| Ring | Devices connected in a circular fashion with each node connected to exactly two neighbors (unidirectional) | Data packets travel at high speed with minimal collisions, simple fault isolation since data flows in a specific direction, predictable performance under consistent network load | Failure of a single node or link can disrupt the entire network, troubleshooting and reconfiguring are complex |
| Mesh | Each device connected to every other device (directly or indirectly) | Facilitates fast data transmission and effective fault diagnosis, allows for multiple paths for data transmission | Complex installation and configuration, high initial cost due to cabling and ports, expensive to maintain and scale as the number of devices grows |
| Tree | Hierarchical topology combining characteristics of star and bus topologies (multiple star-configured networks connected to a linear bus backbone) | Supports scalability and easy expansion, fault isolation is simpler compared to bus topology, supports centralized management while allowing segmented networks | Backbone failure affects the entire segment connected to it, more cabling and complexity than simple star or bus topologies |
| Hybrid | Combination of two or more different topologies (e.g., star-ring, star-bus) tailored to meet specific organizational needs | Highly flexible and scalable, leverages strengths of various topologies while mitigating individual weaknesses, facilitates optimized performance and fault tolerance | Design and implementation complexity, potentially higher cost due to integration of multiple topology types |