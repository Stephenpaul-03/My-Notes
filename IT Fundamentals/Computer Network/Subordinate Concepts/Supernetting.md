# **Supernetting in IPv4**

- Supernetting, also known as **route summarization** or **CIDR aggregation**, is the inverse of subnetting.
- Instead of breaking a network into smaller parts, supernetting **combines multiple smaller contiguous networks into a single larger network block**.
- This optimizes routing efficiency by reducing the number of entries in routing tables.

## **# **Purpose of Supernetting****

- **Reduce routing table size** (especially in BGP and large enterprise networks)
- **Improve routing performance**
- **Simplify route advertisements**
- **Enable hierarchical IP address allocation**

## **# **CIDR (Classless Inter-Domain Routing)****

CIDR allows IP addresses to be assigned with arbitrary-length prefixes (not confined to class A, B, or C), enabling both subnetting and supernetting.

For example:

- Class C networks: `192.168.0.0/24`, `192.168.1.0/24`, `192.168.2.0/24`, `192.168.3.0/24`
- These can be supernetted into a single **/22**:
    
    ```
    192.168.0.0/22 → covers:
    192.168.0.0 – 192.168.3.255
    
    ```
## **# **Supernetting Criteria****

To successfully supernet:

1. **Networks must be contiguous.**
2. **The number of networks must be a power of 2.**
3. **They must align on subnet boundaries.**

## **# **Calculation Process****

**Example**

Supernet `192.168.4.0/24` and `192.168.5.0/24`.

1. Convert to binary:
    - `192.168.4.0` → `11000000.10101000.00000100.00000000`
    - `192.168.5.0` → `11000000.10101000.00000101.00000000`
2. Compare bit by bit:
    - First 23 bits are common → `192.168.4.0/23`
3. Result:
    - Supernet: `192.168.4.0/23`
    - Covers:
        - `192.168.4.0 – 192.168.5.255`

# **Supernetting in IPv6**

## **# **Why Supernetting Is Less Emphasized****

In IPv6:

- The address space is *vast*, so fragmentation is not a concern.
- Supernetting is built into the **address allocation strategy** from the start.
- Routing hierarchy is planned using large block allocations (e.g., /32, /48).

IPv6 was architected with **built-in summarization logic** via **hierarchical addressing**.

## **# **Aggregation in IPv6****

IPv6 uses **prefix aggregation** to minimize routing entries:

## **# Example**

An ISP allocates:

- `2001:db8:1000::/48`
- `2001:db8:1001::/48`
- `2001:db8:1002::/48`
- `2001:db8:1003::/48`

These can be summarized as:

- `2001:db8:1000::/46` → covers all four
## **# **Requirements for IPv6 Aggregation****

Same principles as IPv4:

1. **Prefixes must be contiguous**
2. **Prefix length must support aggregation**
3. **Bit alignment is critical**

IPv6 addresses are in **hexadecimal**, but aggregation operates at the **binary** level.
## **# **Benefits in IPv6****

- **Core ISP routers** may advertise **one /32** for thousands of downstream customers.
- Reduces BGP route table size (critical at Tier-1 levels).
- Supports **provider-based addressing** for route compression.
## **# **Delegation Best Practices****

| Entity           | Typical Prefix | Purpose              |
| ---------------- | -------------- | -------------------- |
| RIR → ISP        | /32            | Regional delegation  |
| ISP → Customer   | /48 or /56     | Customer allocation  |
| Customer Subnets | /64            | Internal LAN subnets |

If customers are assigned sequential /48s:

- `2001:db8:3000::/48` to `2001:db8:3fff::/48`
- These can be aggregated to: `2001:db8:3000::/36`