# CIDR Explained

Let’s break down CIDR (Classless Inter-Domain Routing) in super simple terms, using a formula and an example.

### 1. **CIDR Notation and Formula**:
- CIDR uses the format `IP address/prefix length`.
   - Example: `192.168.1.0/24`

Here’s what this means:
- **IP Address**: The IP address is `192.168.1.0`. This represents the network.
- **Prefix Length**: The `/24` means that the first 24 bits are dedicated to the network, and the remaining bits (in this case, 8 bits) are for the hosts (devices like computers, phones, etc.).

### **Formula to Understand CIDR**:
To calculate how many devices (hosts) you can have in a network, use this formula:

```
Formula: 

Number of Hosts = 2 ^ ( 32 - Prefix Length) - 2

Example: 192.168.1.0/24

Number of Hosts = 2 ^ ( 32 − 24 ) − 2 = 2 ^ 8 − 2 = 256 − 2 = 254
```

Where:
- 32 is the total number of bits in an IPv4 address.
- Subtract 2 because one IP is reserved for the **network address** and another for the **broadcast address**.

---

### 2. **Example**: Breaking Down `192.168.1.0/24`
Let’s apply this to `192.168.1.0/24`:

- **Prefix Length**: `/24` means the first 24 bits are for the **network**.
  - In binary, `192.168.1.0` looks like this: 
    ```
    11000000.10101000.00000001.00000000
    ```
    The first 24 bits (bolded) represent the network portion:
    ```
    11000000.10101000.00000001.**** ****
    ```

- **Host Bits**: The remaining 8 bits (because `32 - 24 = 8`) are for **hosts**.

- **Number of Hosts**: Using the formula:

```
Number of Hosts = 2 ^ ( 32 − 24 ) − 2 = 2 ^ 8 − 2 = 256 − 2 = 254
```

So, with a `/24` subnet, you can have **254 devices** (hosts) on the network.

```
Stats:

 - Netmask:                  255.255.255.0
 - CIDR Base/Network IP:     192.168.1.0
 - Broadcast IP:             192.168.1.255
 - Total Available IP Count: 256
 - Total Usable IP Count:    254 (Excludes CIDR Base/Network IP and Broadcast IP)
 - First Usable IP:          192.168.1.1
 - Last Usable IP:           192.168.1.254
```

---

### 3. **What Does the Subnet Look Like?**
- The range of IP addresses you can assign to devices in the `192.168.1.0/24` network would be from:
  - **192.168.1.1** to **192.168.1.254** (remember, `192.168.1.0` is reserved for the **network address**, and `192.168.1.255` is reserved for the **broadcast address**).

---

### 4. **If You Change the Prefix**:
- Let’s say you change it to `/25`, the formula becomes:

```
Number of Hosts = 2 ^ ( 32 − 25 ) − 2 = 2 ^ 7 − 2 = 128 − 2 = 126
```

With a `/25`, you now have 126 available IPs for devices, and the network is split into two equal parts.

---

### 5. **Example**: Breaking Down `172.31.0.0/16`

Let’s apply this to `172.31.0.0/16`:

- **Host Bits**: The remaining 16 bits (because `32 - 16 = 16`) are for **hosts**.

- **Number of Hosts**: Using the formula:

```
Number of Hosts = 2 ^ ( 32 − 16 ) − 2 = 2 ^ 16 − 2 = 65536 − 2 = 65534
```

So, with a `/16` subnet, you can have **65534 devices** (hosts) on the network.

```
Stats:

 - Netmask:                  255.255.0.0
 - CIDR Base/Network IP:     172.31.0.0
 - Broadcast IP:             172.31.255.255
 - Total Available IP Count: 65,536
 - Total Usable IP Count:    65,534 (Excludes CIDR Base/Network IP and Broadcast IP)
 - First Usable IP:          172.31.0.1
 - Last Usable IP:           172.31.255.254
```
---

### Quick Summary:
- **CIDR Notation**: `IP Address/prefix length`
- **Prefix Length**: How many bits are used for the network (the rest are for hosts).
- **Formula**: To find how many hosts you can have, use `2^(32 - Prefix Length) - 2`.

This method helps efficiently manage and split IP addresses in a network.

---

### YouTube Links:
 - Understanding CIDR Ranges and dividing networks- https://www.youtube.com/watch?v=MmA0-978fSk
 - IP Addressing Complete Tutorial | Easiest Tutorial of IP Address in Hindi - https://www.youtube.com/watch?v=yP4yePOjJBg
 - Understanding CIDR Block in AWS VPC : Classless Interdomain Routing - https://www.youtube.com/watch?v=I_LXaIg6mkM

---

### URL Links:
 - Interactive IP / CIDR Calculator - https://cidr.xyz/
 - Subnet Calculator - https://mxtoolbox.com/subnetcalculator.aspx

---
