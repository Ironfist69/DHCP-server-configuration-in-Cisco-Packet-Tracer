# DHCP configuration using Cisco Packet Tracer
## Objective
The primary objective of this project was to configure a DHCP server in Cisco Packet Tracer, allowing network clients to automatically receive IP addresses and necessary network configurations.
## Devices used
- 1 DHCP Server
- 3 Switches
- 2 Routers
- 15 PCs

![Screenshot 2024-10-13 164945](https://github.com/user-attachments/assets/36ebc9b5-ed09-46fe-9dcd-ea0bc1c8b6fd)

## Arranging Network Topology

![Screenshot 2024-10-13 165754](https://github.com/user-attachments/assets/b52a2ae6-49f7-4aa0-89f3-511b1e06d921)

## Setting IP Addresses

### DHCP Server IP (192.168.0.69)
![Screenshot 2024-10-13 170029](https://github.com/user-attachments/assets/3520d8e2-9ca0-4793-8ad9-66d162e7daac)

### Enabling DHCP Service & creating pools
![Screenshot 2024-10-13 200034](https://github.com/user-attachments/assets/6d6aa1d9-0330-4d36-b1a2-db2f6ddb919d)

- serverPool - from 192.168.0.0
- serverPool1 - from 192.168.1.0
- serverPool2 - from 192.168.2.0

## Configuring Routers & DHCP Relay
### Router0 interfaces
F0/0 - 192.168.0.1
F1/0 - 192.168.1.1

### Router0 DHCP Relay setup
```
Router# conf t
Router(config)# int f0/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int f1/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# exit
wr
```
