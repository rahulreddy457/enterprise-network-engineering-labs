# Enterprise Network Engineering Labs

Hands-on network engineering portfolio demonstrating practical experience with Cisco routing and switching, dynamic routing protocols, network services, troubleshooting, packet analysis, security, and network automation.

These labs are built and tested primarily using Cisco IOS, GNS3, Packet Tracer, Wireshark, Linux, and Python.

## Labs

### 01 — ISP-Style Multi-Area OSPF & BGP Routing

Built a multi-router ISP-style topology integrating an internal multi-area OSPF network with an external BGP autonomous system.

**Technologies:** Cisco IOS, GNS3, OSPF, BGP, DHCP, route redistribution, IPv4, ICMP, traceroute

**Key implementations:**
- Multi-area OSPF using Areas 0, 20, and 18
- Area Border Routers (ABRs)
- eBGP peering between AS 100 and AS 200
- BGP-to-OSPF route redistribution
- DHCP services for the client LAN
- Internal LAN advertisement through BGP
- End-to-end route verification
- Routing-table and return-path troubleshooting

**Validated path:**

`PC1 → R5 → R4 → R2 → R1 → R8 → 8.8.8.8`

**Result:** End-to-end connectivity successfully verified with ICMP and traceroute.

➡️ [View Lab 01](01-isp-routing-bgp-ospf/)

---

## Skills Demonstrated

`Cisco IOS` `Routing & Switching` `OSPF` `BGP` `TCP/IP` `DHCP` `Route Redistribution` `Network Troubleshooting` `GNS3` `Packet Analysis`

## Repository Roadmap

Additional hands-on labs will cover switching, redundancy, network security, troubleshooting, packet analysis, and network automation.

### 02 — Enterprise Switching, VLANs & RSTP

[View Lab →](02-enterprise-switching-stp/)

Built a redundant Layer 2 enterprise switching topology using Cisco switches and Rapid-PVST+.

**Implemented:**
- VLAN 10 user segmentation
- IEEE 802.1Q trunking
- Rapid-PVST+ (RSTP)
- Primary and secondary root bridge engineering
- STP Root, Designated, and Alternate port analysis
- PortFast and BPDU Guard on endpoint-facing ports
- Redundant Layer 2 path failover
- RSTP reconvergence testing
- Native VLAN and BPDU Guard troubleshooting
- End-to-end VLAN connectivity validation

**Validated failover:**

`SW3 → SW1` primary path failure caused the redundant `SW3 → SW2 → SW1` path to automatically transition to forwarding.

**Result:** RSTP successfully prevented a Layer 2 loop, maintained redundant connectivity, and reconverged when the primary path was restored.
