# Cisco Packet Tracer: Basic Static Routing Lab

A foundational Cisco networking lab demonstrating how to establish communication between two isolated Local Area Networks (LANs) using static routing via Cisco IOS.

## Topology Diagram
![Network Topology](topology.png)

## Network Architecture & IP Schema
* LAN 1: 192.168.1.0/24
* LAN 2: 192.168.2.0/24
* Inter-Router Link: 10.0.0.0/30
    * Router 0 Interface: 10.0.0.1
    * Router 1 Interface: 10.0.0.2

## Router Configurations

### Router 0 Configuration:
![Router 0 Config](Router0_config1.png)

### Router 1 Configuration:
![Router 1 Config](Router1_config1.png)

## Verification
* Successful end-to-end ping execution from PC0 to PC2.
* Verified path mapping via tracert.

### Ping Verification Result:
![Ping Verification](ping_verification.png)
