# RIP Dynamic Routing Lab – Cisco Packet Tracer

![Cisco](https://img.shields.io/badge/Cisco-Networking-blue)
![Packet Tracer](https://img.shields.io/badge/Tool-Cisco%20Packet%20Tracer-green)
![Routing](https://img.shields.io/badge/Routing-RIP%20v2-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

A beginner-friendly networking lab demonstrating **Dynamic Routing using RIP Version 2** in Cisco Packet Tracer.

This project simulates a small routed network where multiple routers exchange routing information using RIP to allow communication between two separate LAN networks.

---

# Network Topology

![Network Topology](topology.png)

> Replace `topology.png` with the screenshot of your Packet Tracer topology.

---

# Project Overview

This lab demonstrates:

- Dynamic routing using **RIP Version 2**
- Communication between **two different LAN networks**
- Basic **router interconnections**
- **DHCP configuration** for automatic IP assignment
- End-to-end connectivity testing using **ping**

The network consists of **five routers connected in a ring topology** with two LAN networks on the edges.

---

# Network Structure

## Left LAN

Network: `192.168.1.0 /24`

| Device | IP Address |
|------|-------------|
| PC0 | 192.168.1.2 |
| PC2 | 192.168.1.3 |
| Router A | 192.168.1.1 |

Router A acts as the **default gateway** for this LAN.

---

## Right LAN

Network: `200.200.200.0 /24`

| Device | IP Address |
|------|-------------|
| PC3 | 200.200.200.2 |
| PC1 | 200.200.200.3 |
| Router C | 200.200.200.1 |

Router C acts as the **default gateway**.

---

# Router Interconnections

| Link | Network |
|-----|--------|
| Router A ↔ Router B | 10.0.0.0 |
| Router B ↔ Router C | 11.0.0.0 |
| Router C ↔ Router D | 12.0.0.0 |
| Router D ↔ Router E | 13.0.0.0 |
| Router E ↔ Router A | 14.0.0.0 |

These connections create a **ring topology** between routers.

---

# RIP Configuration

All routers run **RIP Version 2** to exchange routing information.

Example configuration:

#Router A
```bash
enable
configure terminal
router rip
version 2
network 192.168.1.0
network 10.0.0.0
network 14.0.0.0
no auto-summary
exit
