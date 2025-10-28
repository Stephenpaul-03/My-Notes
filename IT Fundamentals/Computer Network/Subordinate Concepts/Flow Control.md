## **Definition**

- **Flow control** in computer networks is a set of techniques used to manage the rate of data transmission between a sender and a receiver to ensure that the receiver is not overwhelmed by data it cannot process in time.
- Flow control is crucial for reliable communication, optimizing throughput, preventing data loss, and managing buffer usage in networks where devices can operate at vastly different speeds.

## **Purpose of Flow Control**

- **Prevents data loss** by avoiding receiver buffer overflow.
- **Ensures reliable, in-order data delivery** by aligning sender speed with receiver capacity.
- **Optimizes throughput** and network resource usage.
- **Reduces congestion**, retransmissions, and packet loss
## **Working**

- The sender transmits data only as fast as the receiver can process it.
- If the receiver's buffer is nearly full, it can signal the sender to slow down or pause transmission.
- This feedback loop helps maintain stable, efficient communication and avoids dropped packets due to buffer overflow.
- Buffer management is central - larger buffers may delay the need for flow control but don't eliminate it.

## **Main Flow Control Techniques**

### # 1. **Stop-and-Wait Flow Control**

- **Mechanism:** The sender transmits one frame at a time and waits for an acknowledgment (ACK) from the receiver before sending the next frame.
- **Advantages:** Simple to implement.
- **Disadvantages:** Inefficient over long distances or high-latency links, as the sender remains idle while waiting for ACK, resulting in poor resource utilization
### # 2. **Sliding Window Flow Control**

- **Mechanism:** The sender can transmit multiple frames before needing an acknowledgment, based on a predefined window size.
- **Types:**
    - **Go-Back-N:** If an error is detected, all frames from the erroneous one onward are retransmitted.
    - **Selective Repeat:** Only the erroneous frames are retransmitted, improving efficiency.
- **Advantages:** Keeps the sender busy, improves throughput and network utilization.
- **Disadvantages:** More complex implementation (requires buffer management and sequencing)
### # 3. **Credit-Based (or Feedback-Based) Flow Control**

- **Mechanism:** The receiver grants “credits” to the sender, indicating how many frames can be sent before further permission is required.
- **Common Example:** Used in protocols like XON/XOFF for serial communication and sometimes in TCP.
- **Advantages:** Dynamically adjusts to the receiver’s buffer capacity.
- **Disadvantages:** May add latency if sender must wait for new credits.

### # 4. **Rate-Based Flow Control**

- **Mechanism:** The sender’s transmission speed is restricted by protocol-defined limits, not receiver feedback. Used where feedback is impractical or to avoid acknowledgement overhead
## **Flow Control in the Network Stack**

- **Data Link Layer:** Implements frame-level flow control for direct device-to-device communication (e.g., Stop-and-Wait, Sliding Window).
- **Transport Layer:** Implements end-to-end flow control (e.g., TCP uses windowing and advertised receive window).
- **Application Layer:** May also implement its own flow control for high-level protocols.

## **Why Flow Control Matters**

Without flow control:

- Fast senders can overwhelm slow receivers.
- Receiver buffers can overflow, causing data loss and poor throughput.
- Network congestion increases retransmissions and reduces reliability.

With flow control:

- Networks adapt to changing conditions and device speeds.
- Reliable, efficient data transmission is maintained across varying environments