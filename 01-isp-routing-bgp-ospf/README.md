# ISP-Style Multi-Router Network — OSPF & BGP

## Project Overview

This project simulates an ISP-style multi-router network using Cisco IOS in GNS3. The lab demonstrates internal and external routing, route propagation, end-to-end connectivity, and systematic network troubleshooting.

## Technologies Used

- Cisco IOS
- GNS3
- OSPF
- BGP
- Static Routing
- IPv4 Addressing
- DHCP
- NAT/PAT
- Cisco CLI
- Network Troubleshooting

## Network Objectives

- Build a multi-router ISP-style topology.
- Configure IPv4 addressing across router interfaces.
- Establish internal routing using OSPF.
- Configure BGP between different autonomous systems.
- Advertise and verify network prefixes.
- Provide LAN clients with network connectivity.
- Validate end-to-end communication.
- Troubleshoot routing and connectivity failures.

## Network Topology

The topology represents a multi-area OSPF network inside **AS 100**, with an external BGP connection to **AS 200**.

![ISP-Style Multi-Router OSPF and BGP Network Topology](network-topology.png)

### Topology Highlights

- **AS 100** represents the internal enterprise/service-provider routing domain.
- **AS 200** represents an external network reachable through BGP.
- **R1** acts as the primary edge/core router connecting AS 100 to AS 200.
- **OSPF Area 0** provides the backbone routing area.
- Additional OSPF areas demonstrate multi-area routing.
- Router loopback interfaces are used to represent stable network prefixes.
- **PC1** represents an end-user LAN host used for end-to-end connectivity testing.
- The `8.8.8.8/32` loopback on R8 represents an external destination used for reachability testing.

## Configuration

Router configurations will be documented in the `configs` directory.

Topics include:

- Interface configuration
- IPv4 addressing
- Static and default routes
- OSPF configuration
- BGP neighbor relationships
- Network advertisement
- DHCP
- NAT/PAT

## Verification

Network operation is verified using commands such as:

```text
show ip interface brief
show ip route
show ip ospf neighbor
show ip ospf database
show ip bgp
show ip bgp summary
ping
traceroute
```

## Troubleshooting

The lab includes troubleshooting scenarios involving:

- Missing routes
- Incorrect next-hop configuration
- OSPF adjacency problems
- BGP neighbor and prefix advertisement issues
- Return-path routing failures
- NAT configuration issues
- End-to-end connectivity failures

## Key Skills Demonstrated

- Cisco Routing & Switching
- OSPF
- BGP Fundamentals
- IPv4 Addressing
- Routing Table Analysis
- Network Troubleshooting
- Fault Isolation
- Cisco IOS CLI
- GNS3 Network Simulation

## Project Status

🚧 Documentation and configurations are being added.
