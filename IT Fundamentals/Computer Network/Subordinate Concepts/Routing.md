## **Definition**

- Routing protocols are algorithms used by routers to determine the **optimal path** for forwarding packets through a network. 
- They are classified broadly into 
	- **Interior Gateway Protocols (IGPs)** 
	- **Exterior Gateway Protocols (EGPs)**.
## **Components**

1. **Router**    
    A device that connects multiple networks and determines the path for packet forwarding.
    
2. **Routing Table**
    A data structure stored in a router that lists routes to destination networks. Each entry typically contains:
	    - **Destination prefix**
	    - **Next-hop IP address**
	    - **Interface to forward out**
	    - **Administrative distance**
	    - **Metric**
    
    **Example**
    
| Destination  | Next Hop      | Interface | Metric | Admin Distance |
| ------------ | ------------- | --------- | ------ | -------------- |
| `10.0.0.0/8` | `10.1.1.1`    | `eth0`    | 1      | 110 (OSPF)     |
| `0.0.0.0/0`  | `192.168.1.1` | `eth1`    | 10     | 1 (static)     |

1. **Packet Forwarding**
    - Once the best route is selected, the router **forwards the packet** to the next hop toward its destination.
    
## **Key Concepts**

1. **Administrative Distance (AD)**
    - Trustworthiness of a route source.
    - Lower AD is preferred.
                
| Source             | AD  |
| ------------------ | --- |
| Directly Connected | 0   |
| Static             | 1   |
| EIGRP              | 90  |
| OSPF               | 110 |
| RIP                | 120 |

1. **Route Aggregation**    
    - Combining multiple prefixes into a single route (supernetting) to reduce routing table size.
    
2. **Route Redistribution**
    - Exchanging route information between different routing protocols (e.g., OSPF ↔ EIGRP)
    
3. **Convergence**
    - **Convergence** is the time it takes for all routers to agree on the network topology after a change (e.g., link failure).
    

## **Types**

### **# 1. Distance Vector**

- **Mechanism:** Routers exchange information with their **direct neighbors**, and each router updates its routing table based on the **distance (metric)** and direction (vector) to a destination.
- **Examples:** RIP, IGRP
- **Pros:** Simple to configure
- **Cons:** Slower convergence, prone to routing loops (needs loop-avoidance techniques like split horizon)

### **# 2. Link State**

- **Mechanism:** Routers build a **complete topology map** of the network and independently calculate the best path using **Dijkstra's Shortest Path First** algorithm.
- **Examples:** OSPF, IS-IS
- **Pros:** Fast convergence, highly scalable, accurate routing decisions
- **Cons:** More complex and resource-intensive

### **# 3. Path Vector**

- **Mechanism:** Used between **autonomous systems (ASes)**. Routes include **path information**, typically AS numbers, to avoid loops and enforce policies.
- **Examples:** BGP
- **Pros:** Allows flexible policy-based routing, essential for internet-scale routing
- **Cons:** Complex configuration and slow convergence

### **# 4. Hybrid**

- **Mechanism:** Combines characteristics of both Distance Vector and Link State. For example, EIGRP uses **distance vector behavior** but also maintains **topology tables** like link-state protocols.
- **Examples:** EIGRP
- **Pros:** Fast convergence, more efficient than pure DV protocols
- **Cons:** Proprietary (in Cisco’s case), limited multi-vendor support

## **Metrics**

### **# 1. Hop Count**

- **Used By:** RIP
- **Description:** Counts the number of routers a packet must pass through.
- **Goal:** Fewer hops = better path
- **Limitation:** Does not consider bandwidth, delay, or load.

### **# 2. Bandwidth**

- **Used By:** IGRP, EIGRP
- **Description:** Prefers paths with **higher bandwidth** (i.e., faster links).
- **Goal:** Use links with more capacity for better performance.

### **# 3. Delay**

- **Used By:** IGRP, EIGRP
- **Description:** Measures the **time it takes for packets to traverse** the link.
- **Goal:** Lower delay = better performance.

### **# 4. Load**

- **Used By:** IGRP, EIGRP
- **Description:** Represents the **current traffic load** on a link.
- **Goal:** Avoid over-utilized links.
- **Note:** Dynamic and fluctuates rapidly; often weighted less.

### **# 5. Reliability**

- **Used By:** IGRP, EIGRP
- **Description:** Based on the **error rate** or stability of the link.
- **Goal:** Prefer more stable and error-free links.

### **# 6. Cost**

- **Used By:** OSPF
- **Description:** Inversely proportional to bandwidth. Admins can **manually assign cost values**.
- **Goal:** Lower cost = better path.
- **Example:** A 100 Mbps link might have a cost of 1, while a 10 Mbps link might have a cost of 10.

## **# 7. Path Attributes**

- **Used By:** BGP
- **Description:** Not numerical metrics but **policy-based factors** such as:
    - **AS Path:** Shorter path = preferred
    - **Local Preference:** Higher value = preferred
    - **Multi-Exit Discriminator (MED):** Lower = preferred
    - **Next-Hop IP**
    - **Origin Type**

## **Protocols**

### **# 1.RIP (Routing Information Protocol)**

- **Type:** Distance Vector (IGP)
- **Metric:** Hop count (max 15 hops)
- **Algorithm:** Bellman-Ford
- **Version:** RIP v1 (classful), RIP v2 (classless, supports VLSM)
- **Updates:** Every 30 seconds (periodic)
- **Pros:**
    - Simple to configure
    - Works on small, flat networks
- **Cons:**
    - Converges slowly
    - Not scalable; limited by hop count
    - High bandwidth usage due to periodic updates

### **# 2. IGRP (Interior Gateway Routing Protocol)** – *Cisco proprietary (legacy)*

- **Type:** Distance Vector (IGP)
- **Metric:** Bandwidth, delay, load, reliability
- **Algorithm:** Composite metric formula
- **Pros:**
    - More robust than RIP
    - Supports unequal cost load balancing
- **Cons:**
    - Not suitable for modern, scalable networks
    - Classful, lacks VLSM support
    - Deprecated in favor of EIGRP

## **# 3. EIGRP (Enhanced IGRP)** – *Cisco proprietary*

- **Type:** Advanced Distance Vector / Hybrid (IGP)
- **Metric:** Bandwidth, delay, reliability, load, MTU
- **Algorithm:** DUAL (Diffusing Update Algorithm)
- **Pros:**
    - Fast convergence
    - Unequal-cost load balancing
    - Efficient bandwidth usage
    - Supports VLSM and CIDR
- **Cons:**
    - Vendor lock-in (Cisco-centric)
    - Less commonly used in multi-vendor environments

## **# 4. OSPF (Open Shortest Path First)**

- **Type:** Link State (IGP)
- **Metric:** Cost (based on bandwidth)
- **Algorithm:** Dijkstra (SPF)
- **Area-based Design:** Area 0 is backbone
- **Pros:**
    - Fast convergence
    - Scalable with area hierarchies
    - Open standard (multi-vendor support)
    - Supports VLSM, CIDR, route summarization
- **Cons:**
    - More complex to configure than RIP/EIGRP
    - Requires careful design and planning

## **# 5. IS-IS (Intermediate System to Intermediate System)**

- **Type:** Link State (IGP)
- **Metric:** Cost (can be configured)
- **Algorithm:** Dijkstra
- **Design:** IS-IS levels instead of areas (like OSPF)
- **Pros:**
    - Highly scalable (used by ISPs)
    - Vendor-neutral
    - More efficient in large networks than OSPF
- **Cons:**
    - Less intuitive than OSPF
    - Rare in enterprise networks

## **# 6. BGP (Border Gateway Protocol)**

- **Type:** Path Vector (EGP)
- **Metric:** Path attributes (AS-Path, Next-Hop, Local Pref, etc.)
- **Algorithm:** Policy-based routing
- **Versions:** BGP-4 supports IPv6 (MP-BGP)
- **Pros:**
    - Internet-scale routing (default for ISPs)
    - Policy control over route advertisement
    - Highly scalable and robust
- **Cons:**
    - Complex to configure
    - Slow convergence
    - Vulnerable to misconfigurations and route leaks

## **# **Comparison Table****

| Protocol | Type | Metric | Algorithm | Convergence | Scalability | Vendor Support |
| --- | --- | --- | --- | --- | --- | --- |
| **RIP** | DV | Hop Count | Bellman-Ford | Slow | Low | Multi-vendor |
| **IGRP** | DV | Bandwidth, Delay | Bellman-Ford (composite) | Moderate | Low | Cisco only |
| **EIGRP** | Hybrid | Bandwidth, Delay, Load, Reliability | DUAL | Fast | Medium | Cisco only |
| **OSPF** | LS | Cost (Bandwidth) | Dijkstra | Fast | High | Multi-vendor |
| **IS-IS** | LS | Configurable | Dijkstra | Fast | Very High | Multi-vendor |
| **BGP** | PV | Path Attributes | Policy-based | Slow | Extremely High | Multi-vendor |

## **Algorithms**

### **# 1. **Bellman-Ford Algorithm**

**Used in:** RIP, IGRP (with enhancements)

**Working**

- Each router maintains a routing table with the **best known distance** (metric) to each destination and the **next hop**.
- Routers periodically exchange **entire routing tables** with their immediate neighbors.
- Upon receiving a neighbor’s table, the router:
    - Adds **1 hop** to each of the neighbor's routes.
    - Updates its own routing table **if a better (shorter) path** is found.

**Advantages**

- Simple to implement.
- Low CPU/memory usage.
- Good for small, stable networks.

**Disadvantages**

- **Slow convergence.**
- Susceptible to **routing loops** (e.g., count-to-infinity problem).
- Limited scalability (e.g., RIP max hop count = 15).

**Analogy:**

- Like planning a road trip by asking your immediate neighbor which cities they can reach and how far they are. You trust what they say and add 1 mile to every distance they give.

## **# 2. DUAL (Diffusing Update Algorithm)**

**Used in:** EIGRP

**Working**

- Uses a **composite metric** (bandwidth, delay, load, reliability).
- Maintains:
    - **Topology table** (all known routes)
    - **Routing table** (best routes)
- Finds **successor (best route)** and **feasible successor (backup route)** to destinations.
- Only affected routers are updated when a change occurs (**partial updates**).

**Advantages**

- **Fast convergence** via precomputed backup paths.
- Loop-free by design.
- Efficient bandwidth usage via **incremental updates**.

**Disadvantages**

- Proprietary (Cisco-specific; limited multi-vendor support).
- More complex to understand and troubleshoot than RIP.

**Analogy:**

- Like having a GPS with live traffic that not only finds the best route but also keeps a backup route preloaded. If the main route is blocked, it immediately switches to the backup.

## **# 3. Dijkstra’s Shortest Path First (SPF)**

**Used in:** OSPF, IS-IS

**Working**

- Each router builds a complete **link-state database (LSDB)** of the entire network.
- Calculates the shortest path to all destinations using **Dijkstra’s algorithm**:
    - Starts from itself and iteratively finds the **lowest-cost node not yet processed**.
    - Updates the path costs of neighboring nodes.
- Updates are triggered by topology changes and sent via **LSAs (Link State Advertisements).**

**Advantages**

- **Very accurate routing decisions**.
- **Fast convergence**.
- Scales well in large enterprise networks.

**Disadvantages**

- High **CPU and memory usage**.
- Complex setup and **troubleshooting**.
- Requires careful **hierarchical design** (especially in OSPF with areas).

**Analogy**

- Imagine Google Maps downloading a full map of a city and then calculating the shortest driving route from your location to every other street.

## **# 4. BGP Best Path Selection (Policy-Based)**

**Used in:** BGP (Path Vector)

Working

- Routers (BGP speakers) exchange routes between **autonomous systems (ASes)**.
- Does **not use numerical metrics** like bandwidth or delay.
- Compares routes based on **policy attributes**:
    1. Highest **Local Preference**
    2. Shortest **AS Path**
    3. Lowest **Origin Type**
    4. Lowest **MED**
    5. eBGP over iBGP
    6. Lowest Router ID
- Admins can override default behavior using **route maps and policies**.

**Advantages:**

- Highly **scalable and customizable**.
- Ideal for **inter-AS (internet)** routing.
- Allows precise **policy control** over route selection.

**Disadvantages:**

- **Slow convergence** (not ideal for real-time adaptation).
- **Complex configuration** and debugging.
- Vulnerable to **misconfiguration and route hijacking**.

**Analogy:**

- Like shipping goods internationally by comparing various freight companies based on rules (shortest route, political alliances, costs, reliability), not just distance or speed.

## **# Comparsion Table**

| Algorithm | Used By | Type | Advantages | Disadvantages |
| --- | --- | --- | --- | --- |
| Bellman-Ford | RIP, IGRP | Distance Vector | Simple, low resource use | Slow convergence, routing loops |
| DUAL | EIGRP | Hybrid | Fast, loop-free, backup paths | Cisco proprietary, moderate complexity |
| Dijkstra SPF | OSPF, IS-IS | Link State | Accurate, fast, scalable | Resource intensive, complex to manage |
| BGP Selection | BGP | Path Vector | Scalable, policy-based, flexible interdomain use | Complex, slow convergence, vulnerable config |