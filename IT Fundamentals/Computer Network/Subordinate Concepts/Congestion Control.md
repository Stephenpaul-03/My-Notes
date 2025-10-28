## **Definition**

- Congestion control refers to the techniques and mechanisms used to prevent network overload, ensuring smooth data flow and efficient use of network resources.
- When too much data is sent simultaneously, it causes congestion which leads to delays, packet loss, and degraded network performance. Congestion control manages the traffic to avoid overwhelming the network and maintain stable operation.

## **Types**

### # **Open-loop congestion control:**

- These are preventive policies applied to avoid congestion before it happens.
- They include
    - Retransmission policies (timing retransmissions carefully)
    - Window policies (using selective repeat to avoid unnecessary retransmissions)
    - Discarding policies (discarding less sensitive or corrupted packets)
    - Acknowledgment policies (sending acknowledgments efficiently)
    - Admission policies (checking traffic requirements before admitting flows) .

### # **Closed-loop congestion control:**

- This approach acts after congestion occurs using feedback from the network to adjust traffic rates.
- Mechanisms include:
    - Backpressure:
        - Congested nodes stop receiving packets from upstream nodes until congestion clears.
    - Choke packets:
        - Congested routers send warning packets to the source to reduce transmission rate.
    - **Implicit and explicit signaling**:
        - The source or receiver detects congestion from symptoms or explicit network signals to throttle sending rates .