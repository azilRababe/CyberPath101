## 🌐 Core Network Protocols

### 📡 DHCP (Dynamic Host Configuration Protocol)

- Application layer protocol
- Uses UDP
- Server listens on **UDP port 67**
- Client uses **UDP port 68**

#### DHCP Process: DORA

1. **Discover**
   Client broadcasts a DHCPDISCOVER message to locate a DHCP server.

2. **Offer**
   Server replies with a DHCPOFFER containing an available IP address.

3. **Request**
   Client sends a DHCPREQUEST to accept the offered IP.

4. **Acknowledge**
   Server sends a DHCPACK confirming the IP assignment.

---

## 🔗 ARP (Address Resolution Protocol)

- Maps IP addresses to MAC addresses
- Operates at **Layer 2**
- Used within local networks
- Enables communication over Ethernet

---

## ⚠️ ICMP (Internet Control Message Protocol)

- Used for network diagnostics and error reporting
- Operates at the Network layer

### Common ICMP Tools

- **ping**
  Tests connectivity and measures round trip time using ICMP.

- **traceroute / tracert**
  Discovers the path packets take from source to destination using ICMP.

---

## 🧭 Routing Protocols

### OSPF (Open Shortest Path First)

- Link state routing protocol
- Routers share topology information
- Each router builds a complete network map
- Calculates the shortest path using cost metrics

---

### EIGRP (Enhanced Interior Gateway Routing Protocol)

- Cisco proprietary protocol
- Hybrid routing protocol
- Uses bandwidth and delay metrics
- Shares reachable networks and associated costs

---

### BGP (Border Gateway Protocol)

- Primary routing protocol of the Internet
- Used between autonomous systems
- Exchanges routing information between ISPs
- Focuses on policy based routing

---

### RIP (Routing Information Protocol)

- Distance vector routing protocol
- Uses hop count as the metric
- Maximum of 15 hops
- Common in small or legacy networks
