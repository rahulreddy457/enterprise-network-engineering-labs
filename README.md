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

### 03 — HSRP First-Hop Redundancy with EIGRP

[View Lab →](03-hsrp-first-hop-redundancy/)

Implemented first-hop gateway redundancy using Cisco HSRP with EIGRP dynamic routing across a redundant three-router topology.

**Implemented:**
- HSRP Group 10
- Virtual default gateway `192.168.2.250`
- Active/Standby gateway redundancy
- HSRP priority and preemption
- EIGRP AS 90 dynamic routing
- Redundant routed paths to a remote network
- Gateway failure simulation
- Automatic HSRP failover
- End-to-end connectivity validation during failure
- Active-router recovery and preemption testing

**Validated failover:**

`R1 Active → R1 failure → R2 Active → R1 recovery → R1 Active`

During the simulated R1 gateway failure, PC1 continued reaching both the HSRP virtual gateway and the remote `8.8.8.8/32` destination through R2.

**Result:** HSRP successfully maintained first-hop gateway availability during the simulated failure, and preemption restored R1 as the preferred Active router after recovery.

### 04 — Site-to-Site IPsec VPN

[View Lab →](04-site-to-site-ipsec-vpn/)

Implemented and validated a policy-based Site-to-Site IPsec VPN between two remote LANs using Cisco IOS.

**Implemented:**
- IKE / ISAKMP Phase 1
- Pre-shared key authentication
- IPsec Phase 2
- ESP tunnel mode
- Extended ACL for interesting traffic
- Crypto map configuration
- Static routing between remote sites
- WAN-facing crypto map application
- IKE and IPsec security association verification
- Encrypted/decrypted packet counter validation
- End-to-end inter-site connectivity testing

**Protected Networks:**

`10.10.10.0/24 ↔ 20.20.20.0/24`

**Validated VPN:**

`PC1 → HYD → IPsec ESP Tunnel → BNG → PC2`

IKE reached an active `QM_IDLE` state, inbound and outbound ESP security associations became active, and IPsec counters confirmed encrypted and decrypted traffic with zero send/receive errors.

**Result:** Successfully established and validated encrypted communication between the HYD and BNG site networks.
