## **# Definition**

- Subnetting is the process of dividing a larger IP network into smaller, manageable sub-networks (subnets).
- It’s fundamental to **network design, routing efficiency, address conservation**, and **security segmentation**.
- While the core concept is similar across IPv4 and IPv6, the techniques, constraints, and benefits differ significantly due to the size and structure of the address spaces.

# **# IPv4 Address**

## **# IPv4 Address Basics**

- **IPv4 Address Size**: 32 bits (4 octets)
- **Notation**: Dotted decimal, e.g., `192.168.10.15`
- **CIDR Notation**: `192.168.10.15/24` — where `/24` indicates the number of bits in the **network prefix**.

## **# **Subnetting Mechanics****

define how many bits are used for the network versus the host portion.

| Subnet Mask     | CIDR | Hosts/Subnet | Example Range               |
| --------------- | ---- | ------------ | --------------------------- |
| 255.255.255.0   | /24  | 254          | 192.168.1.1 - 192.168.1.254 |
| 255.255.255.128 | /25  | 126          | 192.168.1.1 - 192.168.1.126 |
| 255.255.255.192 | /26  | 62           | ...                         |
- **Usable Hosts = 2ⁿ - 2**, where `n = 32 - prefix length`
    - Subtracting 2 for **network** and **broadcast** addresses.

## **# **Subnetting Calculation****

**Goal**: Divide `192.168.10.0/24` into 4 equal subnets. 
- **/24** = 256 addresses
- Need 4 subnets → 2² = 4 → Use 2 more bits
- New subnet prefix: `/26` (24 + 2)
- **Subnet mask**: `255.255.255.192`

| Subnet | Subnet Address    | Range                 | Broadcast Address |
| ------ | ----------------- | --------------------- | ----------------- |
| 0      | 192.168.10.0/26   | 192.168.10.1 - .62    | 192.168.10.63     |
| 1      | 192.168.10.64/26  | 192.168.10.65 - .126  | 192.168.10.127    |
| 2      | 192.168.10.128/26 | 192.168.10.129 - .190 | 192.168.10.191    |
| 3      | 192.168.10.192/26 | 192.168.10.193 - .254 | 192.168.10.255    |

**Key Formulae:**

- `# of Subnets = 2^borrowed_bits`
- `# of Hosts per Subnet = 2^host_bits - 2`

## **# **VLSM (Variable Length Subnet Masking)****

Allows subnets of **different sizes** in the same network — used for optimizing address allocation. Example: `/30` for point-to-point links, `/26` for small LANs.

## **# **Tools and Techniques****

### **# **Binary Subnetting (IPv4)****

- Convert IP and subnet mask to binary.
- Use logical AND to find network address.
- Determine subnet ranges via bit arithmetic.

**Example:**

IP: `192.168.1.130` → `11000000.10101000.00000001.10000010`

Subnet Mask: `255.255.255.192` → `/26`

- Network portion = first 26 bits
- Subnet block = 64 addresses (2⁶)
- Subnet = `192.168.1.128 - 192.168.1.191`

# **IPv6 Subnetting**

## **# IPv6 Address Basics**

- **Address size**: 128 bits
- **Notation**: Hexadecimal with colons, e.g., `2001:db8:abcd:0012::1/64`
- **Standard subnet size**: `/64`
	- 64 bits network + 64 bits interface ID (typically EUI-64 or randomly generated)

## **# Key Differences from IPv4**

- **No broadcast addresses**
- **Vast address space** - focus is on **routing hierarchy**, **administrative boundaries**, not address conservation
- Each subnet can support **2⁶⁴ hosts** - over 18 quintillion.

## **# Subnetting Calculation**

**Goal**: Subnet `2001:db8:abcd::/48` into /64 subnets 
- A `/48` allocation leaves **16 bits** for subnetting (`64 - 48 = 16`)
- Number of subnets = `2¹⁶ = 65,536`

```
2001:db8:abcd:0000::/64
2001:db8:abcd:0001::/64
...
2001:db8:abcd:ffff::/64
```

## **# Custom Prefixing Examples**

If a `/56` is received from an ISP and want to assign `/64` to each LAN segment:

- You have `64 - 56 = 8 bits` to subnet → `2⁸ = 256` subnets
- Subnet IDs: `::00` through `::ff`

| Subnet | Address |
| --- | --- |
| 0 | 2001:db8:abcd:00::/64 |
| 1 | 2001:db8:abcd:01::/64 |
| ... | ... |
| 255 | 2001:db8:abcd:ff::/64 |

## **# Larger Subnets (non-/64)****

- Use **/112** or **/120** for point-to-point links or loopbacks
- These are not standard, but are accepted when appropriate
- Hosts must be statically configured or use DHCPv6

## **# IPv6 Subnet Planning

| Use Case              | Prefix Size  |
| --------------------- | ------------ |
| Global Unicast Prefix | /48, /56     |
| Subnet Allocation     | /64          |
| Point-to-point Links  | /127 or /126 |
| Loopback              | /128         |
| Mobile/IoT networks   | /64          |

## **# Tools and Technique**

### **# Hex Math (IPv6)****

- Use hexadecimal math to increment subnet IDs.
- Each hex digit represents 4 bits.
- Example:
    - `/60` subnet: 4 bits → 16 subnets per /64
    - `2001:db8:abcd:0000::/60`
        - Subnet 0: `2001:db8:abcd:0000::/64`
        - Subnet 1: `2001:db8:abcd:0001::/64`
        - ...
        - Subnet F: `2001:db8:abcd:000F::/64`