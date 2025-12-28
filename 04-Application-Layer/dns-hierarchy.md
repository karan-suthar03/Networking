# DNS Hierarchy - Who knows what?

**NO SINGLE SERVER KNOWS EVERYTHING**

## Root DNS Servers
- Top of DNS hierarchy
- Know ONLY where TLD servers are
- **They know:**
  - .com → list of .com TLD servers
  - .org → list of .org TLD servers
  - .in → list of .in TLD servers
- **They DO NOT know:**
  - Domain names (google.com)
  - IP addresses
- **Purpose:** Answer: "Who handles this TLD?"

## TLD Servers (.com, .org, .in)
- Middle layer of DNS
- **They know:**
  - Which authoritative DNS servers manage a domain
  - Example: google.com → ns1.google.com, ns2.google.com
- **They DO NOT know:**
  - Website IP addresses
- **Purpose:** Answer: "Who is authoritative for this domain?"

## Authoritative DNS Servers (Source of Truth)
- Owned/configured by domain owner
- **They know:**
  - Actual DNS records:
    - A / AAAA → IP address
    - CNAME → alias
    - MX → mail server
  - Example: google.com → 142.250.x.x
- **Purpose:** Answer: "Here is the final IP address"

## Recursive DNS Resolvers (Google, Cloudflare)
- Examples: 8.8.8.8, 1.1.1.1
- Not authoritative
- **They know:**
  - Cached DNS answers (temporary)
- **They do:**
  - Query Root → TLD → Authoritative
  - Cache results using TTL
  - Serve users quickly
- **They do NOT own:**
  - Domain information
- **Purpose:** Answer: "I will find the answer and remember it"

## Who is Authoritative?
- Root → authoritative for TLD locations
- TLD → authoritative for domain → nameserver mapping
- Authoritative DNS → authoritative for actual IPs
- Recursive Resolver → NOT authoritative
