## **Definition**

- **Multiplexing** is a technique that allows **multiple data streams** (signals, sessions, or logical connections) to **share the same physical medium or channel**. 
- It’s a form of **resource optimization** where a single transmission path carries multiple simultaneous transmissions.
## **# Use**

Multiplexing occurs at multiple layers but is **most relevant at the Transport Layer (Layer 4)** and the **Physical/Data Link Layers (Layers 1 and 2)** - though the concept spans across layers in different forms:

| OSI Layer | Multiplexing Type            | Purpose                                              |
| --------- | ---------------------------- | ---------------------------------------------------- |
| Layer 1   | **WDM, FDM, TDM**            | Shares physical media (fiber, copper, radio)         |
| Layer 2   | **Statistical TDM (STDM)**   | Shares logical link between multiple sources         |
| Layer 4   | **Port-based multiplexing**  | Enables multiple app sessions on a single IP address |
| Layer 7   | **Application multiplexing** | Encodes multiple logical services over one session   |

## # **a) Time Division Multiplexing (TDM)**

**Working**

- TDM **allocates fixed time slots** to each data stream in a **cyclic, sequential fashion**.
- Each sender transmits during its assigned time slot, one after the other, over a shared channel.

**Types**

- **Synchronous TDM**:
    - Fixed slots, even if sender has no data → leads to idle bandwidth.
- **Statistical TDM (STDM)**:
    - Dynamically allocates slots based on data availability → more efficient.

**Use Cases**

- **Digital telephony (T1/E1 lines)**
- **SONET/SDH networks**
- **Serial communications (UARTs)**

**Advantages:**

- Predictable timing.
- Simple demultiplexing at receiver end.

**Limitations:**

- Inefficient if senders are idle (in synchronous).
- Requires tight clock synchronization.

## # **b) Frequency Division Multiplexing (FDM)**

**Working**

- The total bandwidth is split into **non-overlapping frequency bands**.
- Each signal modulates a **unique carrier frequency**, transmitting simultaneously.

**Use Cases**

- **Analog radio and TV broadcasting**
- **Cable television**
- **DSL (splits voice and internet)**
- **FM radio (88 MHz to 108 MHz band)**

**Advantages**

- Continuous signal flow (no slot gaps).
- Low latency for analog signals.

**Limitations**

- **Guard bands** are required to prevent interference.
- Subject to **crosstalk and intermodulation distortion**.
- Inefficient for digital burst traffic.

## # **c) Wavelength Division Multiplexing (WDM)**

**Working**

- Similar to FDM but for **optical signals**: different **wavelengths (colors of light)** carry different data streams on a single optical fiber.
- Requires **multiplexers (MUX)** and **demultiplexers (DEMUX)** with **precise optical filters**.

**Use Cases**

- **Fiber-optic backbones**
- **Data center interconnects**
- **High-throughput telco networks**

**Types**

- **CWDM (Coarse WDM)**: Fewer, widely spaced wavelengths.
- **DWDM (Dense WDM)**: Up to 80+ channels with tight spacing (used in long-haul).

**Advantages**

- Massive capacity scaling without new fibers.
- Can carry **terabits per second** over one strand.

**Limitations**

- High CAPEX (cost of optical components).
- Sensitive to wavelength drift and temperature.

## # **d) Code Division Multiplexing (CDM / CDMA)**

**Working**

- Each sender is assigned a **unique orthogonal code**.
- All users transmit over the **same frequency band simultaneously**.
- The receiver uses the matching code to isolate the intended signal.

**Use Cases**

- **3G mobile networks (CDMA2000, WCDMA)**
- **Military radio systems**
- **GPS satellite communications**

**Advantages**

- **Highly resilient to interference and eavesdropping**.
- Supports multiple users in the same bandwidth.

**Limitations**

- **Processing overhead** (spread-spectrum).
- Requires **precise code synchronization**.
- **Capacity-limited** by mutual interference (code orthogonality).

## # **e) Port-Based Multiplexing (Layer 4 - TCP/UDP)**

**Working**

- Uses **port numbers** to distinguish between **multiple simultaneous sessions** over a single IP address.
- TCP/UDP headers contain source and destination ports.

**Use Cases**

- **Web servers hosting multiple services (HTTP, HTTPS, FTP)**
- **Client devices running multiple apps concurrently**
- **NAT (Network Address Translation)** and firewall filtering

**Advantages**

- Simple and widely supported in networking stacks.
- Enables full multiplexing at the transport layer without added bandwidth.

**Limitations**

- Port exhaustion under heavy load.
- Can’t distinguish **applications** beyond port number → layer 7 is needed for deep inspection.
