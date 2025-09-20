# Small Enterprise Network Configuration

**Author:** John C.  
**Date:** September 2025  

## Overview

This repository documents a small enterprise network topology featuring an ASUS RX3000 router and a Cisco 3650 Layer 3 switch. It supports inter-VLAN routing, centralized internet access, and static route propagation for full bidirectional communication.

## Topology Diagram

![Network Topology](topology/topology-diagram.png)

## Components

- `configs/core-switch.conf`: Cisco 3650 switch configuration
- `configs/asus-static-routes.txt`: Static routes for ASUS RX3000
- `docs/ip-scheme.md`: VLAN IP addressing scheme
- `topology/topology-diagram.png`: Visual layout of the network

## VLAN Summary

| VLAN | Purpose         | Subnet             | Gateway IP       |
|------|------------------|--------------------|------------------|
| 1    | Uplink to Router | 192.168.1.0/24     | 192.168.1.2      |
| 10   | Desktops         | 192.168.10.0/24    | 192.168.10.1     |
| 30   | Access Points    | 192.168.30.0/24    | 192.168.30.1     |
| 40   | Phones           | 192.168.40.0/24    | 192.168.40.1     |
| 50   | Servers          | 192.168.50.0/24    | 192.168.50.1     |
| 60   | DVR              | 192.168.60.0/24    | 192.168.60.1     |

## Notes

- Cisco switch handles inter-VLAN routing via SVIs.
- ASUS RX3000 provides NAT and internet access.
- Static routes on ASUS ensure return traffic reaches VLANs.
- Firewall rules must permit traffic from all VLANs.

---

© 2025 John C.
