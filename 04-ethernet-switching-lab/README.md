# Ethernet Switching Lab

## Objective

This lab demonstrates basic Ethernet switching and dynamic MAC address learning using two Cisco switches and four PCs.

## Topology

- 2 Cisco 2960 switches
- 4 PCs
- Network: 192.168.1.0/24

![Network Topology](topology.png)

## IP Addressing

| Device | IP Address | Subnet Mask |
|--------|------------|-------------|
| PC1 | 192.168.1.1 | 255.255.255.0 |
| PC2 | 192.168.1.2 | 255.255.255.0 |
| PC3 | 192.168.1.3 | 255.255.255.0 |
| PC4 | 192.168.1.4 | 255.255.255.0 |

## MAC Address Table Before Traffic

The dynamic MAC address table was cleared before generating network traffic.

```text
SW1# clear mac address-table dynamic
SW1# show mac address-table
