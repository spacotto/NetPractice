# Subnet Mask Cheat Sheet (/16 to /32)

| CIDR | Dotted Decimal | Total IPs | Usable Hosts | Typical Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **/16** | `255.255.0.0` | 65,536 | 65,534 | Large enterprise networks |
| **/17** | `255.255.128.0` | 32,768 | 32,766 | Half of a /16 |
| **/18** | `255.255.192.0` | 16,384 | 16,382 | Quarter of a /16 |
| **/19** | `255.255.224.0` | 8,192 | 8,190 | |
| **/20** | `255.255.240.0` | 4,096 | 4,094 | |
| **/21** | `255.255.248.0` | 2,048 | 2,046 | |
| **/22** | `255.255.252.0` | 1,024 | 1,022 | |
| **/23** | `255.255.254.0` | 512 | 510 | |
| **/24** | `255.255.255.0` | 256 | 254 | Standard local network (LAN) |
| **/25** | `255.255.255.128` | 128 | 126 | Half of a /24 |
| **/26** | `255.255.255.192` | 64 | 62 | Quarter of a /24 |
| **/27** | `255.255.255.224` | 32 | 30 | Eighth of a /24 |
| **/28** | `255.255.255.240` | 16 | 14 | Small department / segment |
| **/29** | `255.255.255.248` | 8 | 6 | Small isolated gateway network |
| **/30** | `255.255.255.252` | 4 | 2 | Point-to-point link (router to router) |
| **/31** | `255.255.254` | 2 | 2* | Specialized point-to-point (RFC 3021) |
| **/32** | `255.255.255.255` | 1 | 1 | Single host route / Loopback |

## Core Rules & Formulas

**Calculating Usable Hosts**
The formula to determine the number of usable hosts for any given subnet mask is:
$2^{(32 - \text{CIDR})} - 2$

* **The base 2:** Represents binary (0 or 1).
* **32 - CIDR:** Gives you the number of bits remaining for host addresses.
* **The -2:** Subtracts the two reserved addresses in every standard subnet:
    1.  **Network Address:** The first IP in the block (all host bits are `0`).
    2.  **Broadcast Address:** The last IP in the block (all host bits are `1`).

>[!WARNING]
>**The /31 Exception:** Modern routing equipment sometimes uses `/31` masks for point-to-point links to save IP addresses. In a `/31`, there is no network or broadcast address; both IPs are assigned directly to the two connected interfaces.

