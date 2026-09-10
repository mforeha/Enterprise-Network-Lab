# Enterprise Network Lab

## Overview

This project demonstrates the design and configuration of a small
enterprise network using Cisco Packet Tracer.

The network was designed to support three departments:

- Administration
- Sales
- IT

The network uses VLAN segmentation, trunking, router-on-a-stick
inter-VLAN routing, and DHCP.

## Network Architecture

[Topology image goes here]

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- VLANs
- 802.1Q trunking
- Inter-VLAN routing
- Router-on-a-stick
- DHCP
- IPv4
- Basic network troubleshooting

## Network Topology

The network consists of:

- 1 Cisco 2911 router
- 2 Cisco 2960 switches
- 6 PCs

The router provides:

- Inter-VLAN routing
- Default gateways
- DHCP services

The switches provide:

- VLAN segmentation
- Access ports
- Trunk connections

## VLAN and IP Addressing

| VLAN | Department | Network | Gateway |
|------|------------|---------|---------|
| 10 | Administration | 192.168.10.0/24 | 192.168.10.1 |
| 20 | Sales | 192.168.20.0/24 | 192.168.20.1 |
| 30 | IT | 192.168.30.0/24 | 192.168.30.1 |

## Configuration

### VLAN Configuration

VLAN 10 was created for Administration.

VLAN 20 was created for Sales.

VLAN 30 was created for IT.

### Trunking

Trunk links were configured between:

- R1 and SW1
- SW1 and SW2

The trunks carry VLANs 10, 20, and 30.

### Inter-VLAN Routing

Router-on-a-stick was implemented using router subinterfaces:

- G0/0.10
- G0/0.20
- G0/0.30

Each subinterface acts as the default gateway for its respective VLAN.

### DHCP

DHCP pools were configured on R1 so that PCs automatically receive:

- IP addresses
- Default gateways
- DNS server information

## Verification

The following commands were used to verify the network:

```text
show vlan brief
show interfaces trunk
show ip interface brief
show ip route
show ip dhcp binding
