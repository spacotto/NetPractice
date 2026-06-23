# Level 1

![start](https://github.com/spacotto/NetPractice/blob/main/imgs/l01.png)

## Achieve Goal 1

### The Issue

- **Goal:** *Host* **my PC** needs to communicate with host my little brother's computer.
- **Status:** KO - No forward way, try again ...
- **Network:** Connect `host A` (my PC) to `host B` (my little brother's computer).

### The Solution

Because `Host B`'s interface (`B1`) is locked (`'ip_edit':'false'`), we must modify `Host A`'s interface (`A1`) to match `Host B`'s network parameters. The **subnet mask** `255.255.255.0` dictates that the first three octets (`104.98.23`) represent the **network ID** and must be identical on both machines. **Only the last digit can be unique to identify the specific host**.
- **IP Address:** `104.98.23.12`
- **Subnet Mask:** `255.255.255.0`

To join `Host B`'s network, `Host A`'s IP must **start** with `104.98.23.`, and **end** with any **valid host number from 1 to 254** (**excluding 12**, which `Host B` is already using).

## Achieve Goal 2

### The Issue

- **Goal:** *Host* **my Mac** needs to communicate with host my little sister's computer.
- **Status:** KO - No forward way, try again ...
- **Network:** Connect `host C` (my Mac) to `host D` (my little sister's computer).

### The Solution
