# Enterprise Network Design & Implementation (CCNA Project)

##  Project Overview
This project demonstrates the design and implementation of a **secure, scalable enterprise network** using Cisco devices. It covers VLAN configuration, Inter-VLAN routing, DHCP, NAT, OSPF, and ACLs for departmental segmentation, secure routing, and controlled internet access.

---

##  Objectives
- Isolate departments using VLANs
- Allow controlled Inter-VLAN communication
- Enable automatic IP allocation via DHCP
- Provide internet access for all departments
- Secure routing using OSPF and NAT
- Restrict unauthorized access (ACL implementation)
- Implement fault-tolerant routing

---

## Network Scenario
**Departments:**
- HR Department
- Finance Department
- IT Department

**Requirements:**
- Each department must be in a separate VLAN
- Inter-VLAN routing for required communications
- DHCP for dynamic IP addresses
- Internet access for all departments
- HR should **not** access Finance servers
- Redundant routing for reliability

---

## Devices Used
- 2 × Routers (Cisco 2911)
- 2 × Layer-2 Switches (Cisco 2960)
- 1 × ISP Router (Simulated)
- 1 × Server
- Multiple PCs

---

## IP Addressing Scheme

| VLAN | Department | Network       | Gateway        |
|------|------------|---------------|----------------|
| 10   | HR         | 192.168.10.0/24 | 192.168.10.1 |
| 20   | Finance    | 192.168.20.0/24 | 192.168.20.1 |
| 30   | IT         | 192.168.30.0/24 | 192.168.30.1 |
| WAN  | Router Link | 10.10.10.0/30   | —            |

---

##  Step-by-Step Implementation

### 1️ VLAN Configuration on Switch
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name HR
Switch(config)# vlan 20
Switch(config-vlan)# name FINANCE
Switch(config)# vlan 30
Switch(config-vlan)# name IT
