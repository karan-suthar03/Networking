# IP Address Hierarchy

- **IANA** → Owns all global IP addresses
- **RIR (APNIC for India)** → Gets IP blocks from IANA
- **ISP (Jio, Airtel, etc.)** → Gets IPs from RIR
- **Router (Home/Office)** → Gets 1 public IP from ISP
- **Devices (Mobile, Laptop, TV)** → Get private IPs from router

**Flow:** IANA → RIR → ISP → Router → Devices

## About 192.168.0.1

- 192.168.0.1 is a **PRIVATE IP**
- It is usually the **DEFAULT GATEWAY** (router IP)
- It does **NOT** decide how many devices can connect

## Why People Say "255 Devices"

Most home networks use:
- Network: 192.168.0.0/24
- Subnet Mask: 255.255.255.0

**IP Breakdown:**
- 192.168.0.0 → Network ID (not usable)
- 192.168.0.1 → Router (Gateway)
- 192.168.0.2 → Device
- ...
- 192.168.0.254 → Device
- 192.168.0.255 → Broadcast (not usable)

**Total IPs:** 256
**Usable IPs:** 254

## Important Rule

**Gateway IP does NOT decide device count**

**Subnet mask (/24) decides device count**

## More Than 254 Devices?

Yes, by using a bigger subnet:
- /23 → 510 devices
- /16 → 65,534 devices

Example: 10.0.0.0/16

## One-Line Summary

192.168.0.1 is just the router address.
Subnet size decides how many devices can connect.
