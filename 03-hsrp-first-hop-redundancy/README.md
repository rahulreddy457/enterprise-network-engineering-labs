# HSRP First-Hop Redundancy with EIGRP

## Overview

This lab demonstrates first-hop gateway redundancy using Cisco Hot Standby Router Protocol (HSRP) combined with EIGRP dynamic routing.

Two routers provide a shared virtual default gateway for the LAN. R1 operates as the preferred Active router because of its higher HSRP priority, while R2 operates as the Standby router.

A failure of R1's LAN-facing interface was simulated to verify automatic gateway failover. R2 successfully transitioned from Standby to Active while end-to-end connectivity remained available.

After R1 was restored, HSRP preemption allowed R1 to reclaim the Active role.

## Technologies

- Cisco IOS
- HSRP
- EIGRP
- First-Hop Redundancy
- Dynamic Routing
- Virtual Default Gateway
- Gateway Failover
- Preemption
- ICMP Connectivity Testing
- GNS3

## Network Topology

```text
                       R3
                Loopback0: 8.8.8.8
                    /          \
                   /            \
          192.168.13.0       192.168.23.0
                 /                \
               R1------------------R2
                 192.168.12.0
                 \                /
                  \              /
                      Switch
                     /      \
                   PC1      PC2

                 LAN: 192.168.2.0/24
