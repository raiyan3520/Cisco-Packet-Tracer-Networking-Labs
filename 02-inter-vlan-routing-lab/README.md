# Inter-VLAN Routing Lab

## Objective

The objective of this lab is to allow communication between two separate VLANs using router-on-a-stick inter-VLAN routing.

## Concepts Covered

- VLANs
- Trunk port
- Router subinterfaces
- Default gateway
- Inter-VLAN routing

## Topology

Devices used:

- 1 Cisco router
- 1 Cisco switch
- 4 PCs

## VLAN Design

| VLAN ID | VLAN Name | Devices | Network |
|---|---|---|---|
| 10 | Admin | PC0, PC1 | 192.168.10.0/24 |
| 20 | User | PC2, PC3 | 192.168.20.0/24 |

## IP Addressing Table

| Device | VLAN | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|
| PC0 | VLAN 10 | 192.168.10.10 | 255.255.255.0 | 192.168.10.1 |
| PC1 | VLAN 10 | 192.168.10.11 | 255.255.255.0 | 192.168.10.1 |
| PC2 | VLAN 20 | 192.168.20.10 | 255.255.255.0 | 192.168.20.1 |
| PC3 | VLAN 20 | 192.168.20.11 | 255.255.255.0 | 192.168.20.1 |

## Switch Port Assignment

| Switch Port | Connected Device | Mode | VLAN |
|---|---|---|---|
| Fa0/1 | PC0 | Access | VLAN 10 |
| Fa0/2 | PC1 | Access | VLAN 10 |
| Fa0/3 | PC2 | Access | VLAN 20 |
| Fa0/4 | PC3 | Access | VLAN 20 |
| Fa0/5 | Router G0/0 | Trunk | VLAN 10, VLAN 20 |

## Switch Configuration

```bash
enable
configure terminal

vlan 10
name Admin
exit

vlan 20
name User
exit

interface fa0/1
switchport mode access
switchport access vlan 10
exit

interface fa0/2
switchport mode access
switchport access vlan 10
exit

interface fa0/3
switchport mode access
switchport access vlan 20
exit

interface fa0/4
switchport mode access
switchport access vlan 20
exit

interface fa0/5
switchport mode trunk
exit

end
write memory
```
##Router Configuration
 ```bash
enable
configure terminal

interface gigabitEthernet0/0
no shutdown
exit

interface gigabitEthernet0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
exit

interface gigabitEthernet0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
exit

end
write memory
```

##Verification Commands
```bash
show vlan brief
show interfaces trunk
show ip interface brief

```
