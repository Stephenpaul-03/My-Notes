## **Definition**

- Buffer management is the strategic handling of main memory (RAM) used to temporarily store disk pages , area is known as the **buffer pool**.
## **Role of the Buffer Manager**

The **buffer manager** is the system component responsible for:

- **Loading pages** from disk into memory when requested.
- **Tracking page usage** to detect which data should remain in memory.
- **Deciding eviction strategy** when the buffer pool is full (known as a **replacement policy**).
- **Serving memory-resident data** quickly upon a buffer hit; retrieving from disk otherwise (a **miss**).

## **Buffer Management Techniques**

### # **1. LRU (Least Recently Used)**

- **Principle:** Evict the page that has not been used for the longest time.
- **Use Case:** Assumes recently accessed data is likely to be used again soon.
- **Analogy:** Clearing the table of the customer who hasn’t ordered in a while.

## # **2. MRU (Most Recently Used)**

- **Principle:** Evict the page most recently used.
- **Use Case:** Optimal in scenarios where recently accessed pages are unlikely to be reused immediately (e.g., sequential scans).
- **Note:** Contrasts with LRU; less common but effective in certain workloads.

## # **3. FIFO (First-In, First-Out)**

- **Principle:** Remove the oldest page in the buffer pool, regardless of usage frequency.
- **Use Case:** Simple, low-overhead policy. Risk: frequently accessed old pages may be evicted.

## # **4. Clock (Second-Chance Algorithm)**

- **Principle:** A practical approximation of LRU using a circular buffer (like a clock).
- **Mechanism:** Each page has a reference bit. The clock hand sweeps through, and:
    - If the bit is 1, it is reset to 0 (second chance).
    - If the bit is 0, the page is evicted.
- **Use Case:** Balances efficiency and approximation of recency.

## # **5. LFU (Least Frequently Used)**

- **Principle:** Evict pages that are accessed the least often over time.
- **Use Case:** Suitable for workloads with strong frequency locality.
- **Downside:** Requires tracking usage counters, which adds overhead.
