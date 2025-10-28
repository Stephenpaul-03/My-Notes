## **# Definition**

- **Switching** is a technique used to **forward data from a source to a destination** by determining the optimal path across the network infrastructure. 
- It occurs at the **Data Link Layer (Layer 2)** and sometimes at **Layer 3 (Network Layer)** depending on the switch type.

## **# Summary Table**

| Switching Type | Path Setup | Delay Type | Best For | Example Use Case |
| --- | --- | --- | --- | --- |
| Circuit Switching | Dedicated path | Minimal after setup | Real-time voice/video | PSTN (Public Switched Telephone Network) |
| Packet Switching (Datagram) | No path setup | Variable | Internet data | IP-based communication |
| Packet Switching (Virtual Circuit) | Logical path setup | Less variable | Reliable data flow | ATM, Frame Relay |
| Message Switching | No path setup | High (store & forward) | Non-time-critical data | Email systems (older) |

## **# Feature Summary**

| Feature | Circuit Switching | Datagram Switching | Virtual Circuit Switching | Message Switching |
| --- | --- | --- | --- | --- |
| Connection Setup | Required | Not required | Required | Not required |
| Resource Allocation | Fixed | Dynamic | Logical | Dynamic |
| Latency | Low (after setup) | Variable | Medium | High |
| Efficiency | Low | High | Moderate | Moderate |
| Packet Ordering | In-order | May be out-of-order | In-order | Entire message |
| Fault Tolerance | Low | High | Moderate | Low |
| Real-Time Suitability | High | Medium | High | Low |

## **Types**


### **Circuit Switching**

![CircuitSwitching.png](.png)

#### **# Concept**

- Circuit switching establishes a **dedicated communication path** between the sender and receiver before data transfer begins.
- This circuit remains reserved for the duration of the session, regardless of actual data transmission.
- It is Deterministic and Connection-Oriented

#### **# Working Steps:**

1. **Call Setup**: A path is established through the network by allocating switches and physical channels.
2. **Data Transfer**: Data flows continuously along the established circuit.
3. **Tear Down**: After communication ends, the circuit is released.

#### **# Characteristics**

- **Guaranteed bandwidth**.
- **Fixed latency**.
- **High reliability** during transmission.

#### **# Advantages**

- Suitable for **real-time voice/video** (with low latency).
- Simple error handling (no need to reorder packets).
- Once established, performance is predictable.

#### **# Disadvantages**

- **Resource inefficiency**: Idle circuit still consumes bandwidth.
- **Scalability issues**: Difficult to manage at large scale.
- **High setup time**: Unsuitable for short or bursty communications.


### **Packet Switching**

Packet switching is the **foundation of modern data communication** and is used in the Internet and virtually all modern networks.

![image.png](image%2016.png)


#### **Datagram Packet Switching**

##### **# Concept**

Each packet is **treated independently** and is routed separately, possibly taking different paths to the destination. There's **no pre-established path**.

##### **# Characteristics**

- **Connectionless protocol** (e.g., UDP, IP).
- **Stateless routers**.
- Each packet carries full header info.

##### **# Advantages**

- **Resilient** to network failures; rerouting is possible.
- **Efficient** for bursty traffic (like web browsing).
- No circuit setup delay.

#### **# Disadvantages**

- **Packets may arrive out of order**.
- Higher complexity at endpoints (must handle reassembly).
- **Variable latency** and jitter.


#### **Virtual Circuit Packet Switching**

##### **# Concept**

Establishes a **logical connection** before packet transmission. All packets follow the same path and arrive in order.

##### **# Technologies**

- **Frame Relay**, **X.25**, and **MPLS (Multi-Protocol Label Switching)**.

##### **# Characteristics**

- Connection-oriented.
- Packets are tagged with a **virtual circuit identifier (VCI)**.
- Less overhead per packet compared to datagram mode.

##### **# Advantages**

- **In-order delivery**.
- Lower per-packet processing (less routing lookup).
- More predictable performance than datagram switching.

##### **# Disadvantages**

- **Setup delay**.
- Less flexible than pure datagram switching in dynamic environments.

### **Message Switching**

![image.png](image%2017.png)

#### **# Concept**

The message is treated as a single block. The entire message is stored at each intermediate node before being forwarded to the next hop.

#### **# Characteristics:**

- No connection setup required.
- Messages are buffered at each node.
- Operates in **store-and-forward** mode.

#### **# Example**

Early telegraphy systems; sometimes used conceptually in **email routing**.

#### **# Advantages**

- No circuit setup overhead.
- Better resource usage than circuit switching.

#### **# Disadvantages**

- **High latency**, especially for large messages.
- Requires **significant buffer space** at intermediate nodes.
- Not suitable for real-time communication.
