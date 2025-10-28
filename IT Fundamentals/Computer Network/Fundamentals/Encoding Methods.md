## **Definition**

- Encoding methods define **how digital data (0s and 1s)** are translated into electrical, optical, or radio signals for transmission across physical media. Proper encoding ensures **data integrity, synchronization, and efficient use of bandwidth**.

**Need:**

- Prevents signal loss due to **long sequences of 0s or 1s** (lack of transitions).
- Facilitates **synchronization** between transmitter and receiver.
- Helps in **error detection and correction**.
- Reduces **DC bias** and electromagnetic interference

## # **a) Non-Return to Zero**

**Working**

- **Logical 1**: High voltage level
- **Logical 0**: Low voltage level
- Voltage **remains constant** throughout each bit interval.

**Variants:**

- **NRZ-Level (NRZ-L):** Level represents the bit.
- **NRZ-Inverted (NRZ-I):** A transition occurs for ‘1’; no change for ‘0’ (or vice versa).

**Advantages:**

- Simple to implement.
- High data rate efficiency (1 bit per baud).

**Disadvantages:**

- **Synchronization issues** during long strings of 0s or 1s (no transitions).
- No inherent error detection.
- High DC component.

## # **b) Manchester Encoding**

**Working:**

- Each bit has a **transition at the midpoint**.
- **Logical 1**: Low-to-high transition.
- **Logical 0**: High-to-low transition.
- Combines **clock and data** into one signal.

**Advantages:**

- **Self-synchronizing**: Transitions help receiver maintain clock alignment.
- Detects some basic errors (missing transitions).

**Disadvantages:**

- **Lower efficiency**: Requires **2 baud per bit** (50% bandwidth efficiency).
- More complex circuitry than NRZ.

## **# c) Differential Manchester Encoding**

**Working**

- Always a **mid-bit transition** for clocking.
- Bit value determined by **presence or absence of a transition at the start** of the bit interval:
    - **0**: Transition at the beginning.
    - **1**: No transition at the beginning.

**Advantages**

- Inherits all synchronization benefits of Manchester encoding.
- More **resistant to polarity reversals** and line noise.

Disadvantages:

- Same bandwidth inefficiency (2 baud/bit).
- More complex than NRZ and Manchester.

## **# d) 4B/5B Encoding**

**Working**

- Each **4-bit data group** is mapped to a **5-bit code** that ensures at least one transition per code.
- Then transmitted using NRZ-I or similar line code.
- Ensures **frequent transitions** for clock recovery.

**Advantages:**

- Reduces long run-lengths of 0s or 1s.
- More efficient than Manchester (80% efficiency vs. 50%).

**Disadvantages:**

- Requires encoding/decoding tables.
- Adds 25% overhead.

---

## # **e) 8B/10B Encoding**

**Working**

- **8 bits of data** encoded into **10 bits** with balanced transitions and limited run-lengths.
- Maintains **DC balance** and supports error detection.

**Advantages:**

- Strong clock synchronization.
- Prevents long runs without transitions.
- Supports **error detection** and DC balancing.

**Disadvantages:**

- 25% bandwidth overhead.
- Complex logic required.

## # **f) Multilevel Transmission**

**Working**

- Instead of binary 0/1, uses **multiple voltage levels** (e.g., 4 levels for PAM-4).
- Transmits **2 bits per symbol**, increasing throughput without increasing baud rate.

**Advantages:**

- Increases data rate **without increasing frequency**.
- Efficient in high-speed applications.

**Disadvantages:**

- **More susceptible to noise** due to smaller voltage differences.
- Requires **high signal-to-noise ratio (SNR)**.

## **# Comparison Table**

| Encoding Method | Transitions | Clock Recovery | Efficiency | Use Case |
| --- | --- | --- | --- | --- |
| NRZ | Few | Poor | 100% | USB, legacy serial protocols |
| Manchester | Every bit | Excellent | 50% | Ethernet (10Base-T), RFID |
| Differential Manchester | Every bit | Excellent | 50% | Token Ring, access cards |
| 4B/5B | Frequent | Good | 80% | FDDI, 100Base-TX |
| 8B/10B | Frequent | Excellent | 80% | PCIe, Fibre Channel |
| PAM-4 | Fewer | Moderate | 200%+ | 100GbE, modern SerDes links |