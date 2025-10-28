## **Definition**

- **Data transmission** refers to the process of sending digital or analog data over a communication medium from one device (sender) to another (receiver).
- It underpins all forms of networking and telecommunications, whether wired or wireless.

## **1. **Types of Data Transmission****

### # a) **Analog Transmission**

- Transmits data in the form of continuous signals.
- Utilized primarily in traditional telephony and radio broadcasting.
- **Example:** AM/FM radio, analog telephone lines.

### # b) **Digital Transmission**

- Transmits data as discrete binary signals (0s and 1s).
- Highly reliable and efficient for computer networks.
- **Example:** Ethernet, Wi-Fi, fiber-optic communication.

## 2. **Transmission Modes**

### # a) **Simplex**

- **Direction:** Unidirectional (one-way).
- **Use Case:** Keyboard to CPU, broadcast radio.
- **Limitation:** No feedback from receiver.

### # b) **Half-Duplex**

- **Direction:** Bidirectional, but one direction at a time.
- **Use Case:** Walkie-talkies.
- **Limitation:** Cannot send and receive simultaneously.

### # c) **Full-Duplex**

- **Direction:** Simultaneous two-way communication.
- **Use Case:** Telephone calls, modern network switches.
- **Advantage:** Maximizes bandwidth utilization.

## 3. **Transmission Media**

### # a) **Wired**

- also known as **Guided Media**
- **Twisted Pair Cable:** Inexpensive, used in LANs.
- **Coaxial Cable:** Higher bandwidth; used in cable TV.
- **Fiber Optic Cable:** Extremely high bandwidth; immune to EMI; ideal for long-distance/high-speed communication.

### # b) **Wireless**

- also known as **Unguided Media**
- **Radio Waves:** Wi-Fi, Bluetooth.
- **Microwaves:** Line-of-sight communication (e.g., satellite links).
- **Infrared:** Short-range, line-of-sight (e.g., TV remotes).

## 4. **Transmission Techniques**

### # a) **Serial Transmission**

- Bits transmitted one at a time over a single channel.
- **Use Case:** USB, WAN links.
- **Advantage:** Simplifies hardware and reduces cost.

### # b) **Parallel Transmission**

- Multiple bits transmitted simultaneously over multiple channels.
- **Use Case:** Internal data buses.
- **Limitation:** Signal degradation over longer distances due to timing mismatch (skew).

## 5. **Transmission Types**

### # **a) Synchronous Transmission**

- Synchronous transmission sends data **in a continuous stream** with the sender and receiver **sharing a common clock signal**. This allows for faster and more efficient data transfer, especially over high-volume or long-distance communication systems.

 **Working:**

- Data is sent in large blocks or frames.
- A **clock signal** is embedded or shared between sender and receiver to ensure that both operate in lockstep.
- Synchronization is maintained throughout the session (using dedicated clock lines or embedded synchronization sequences).

**Features:**

- High-speed, bulk data transmission.
- No start or stop bits per byte.
- Requires **synchronization overhead** at the beginning of a transmission (preambles, sync bytes).

**Use Cases:**

- High-speed communications (e.g., Ethernet, DSL, Optical Fiber).
- Wide Area Networks (WANs).
- Digital Telephony (e.g., T1/E1 lines).

**Advantages:**

- **Efficient Bandwidth Utilization:** No per-character overhead means better use of line capacity.
- **High Throughput:** Ideal for large data transfers (e.g., file transfers, video streaming).
- **Low Latency:** Data flows without frequent interruptions.

**Disadvantages:**

- **Complex Timing Requirements:** Needs a shared or derived clock.
- **Loss of Synchronization Risk:** If clock signals drift, data corruption may occur.
- **Higher Setup Overhead:** Initial synchronization needs control bytes, headers, etc.

## # **b) Asynchronous Transmission**

- Asynchronous transmission sends data **one character (or byte) at a time**, with each unit framed by **start and stop bits** to indicate the beginning and end. It does **not require a shared clock** between sender and receiver.

**Working:**

- Each byte is transmitted with a **start bit** (logic 0) and **stop bit(s)** (logic 1).
- The receiver waits in an idle state until a start bit is detected.
- Timing is handled independently per byte.

**Features:**

- Low complexity and easy implementation.
- Tolerant to timing variations between sender and receiver.
- Commonly uses 8-bit frames with 1 start, 1 stop, and optional parity bits.

**Use Cases:**

- Serial ports (RS-232, UART).
- Keyboard input, mouse communication.
- Low-speed or sporadic data transmission.

**Advantages:**

- **Simple and Inexpensive:** Requires minimal timing circuitry.
- **Flexible:** Each character is self-contained.
- **Ideal for Sporadic Communication:** Efficient for occasional transmissions.

**Disadvantages:**

- **Lower Efficiency:** Start and stop bits add 20%+ overhead.
- **Slower Transmission Rates:** Not suited for large or time-critical data.
- **Potential Delay:** Each character incurs processing time.