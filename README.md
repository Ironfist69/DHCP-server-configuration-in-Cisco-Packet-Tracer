# DHCP and DNS Server configuration using Cisco Packet Tracer
## Objective
The primary objective of this project was to configure a DHCP server in Cisco Packet Tracer, allowing network clients to automatically receive IP addresses and necessary network configurations.
## Devices used
- 1 DHCP Server
- 1 DNS Server
- 4 Switches
- 1 Router
- 15 PCs

## Arranging Network Topology

![Screenshot 2024-10-15 164328](https://github.com/user-attachments/assets/deeb4dce-0590-476d-aab7-db71bdb243bf)

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
- F0/0 - 192.168.0.1
- F1/0 - 192.168.1.1

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
