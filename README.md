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

### DHCP Server (192.168.0.69)

![Screenshot 2024-10-15 164434](https://github.com/user-attachments/assets/062941dc-ce5d-4d20-a7e2-c7a1458530ec)

### Enabling DHCP Service & creating pools

![Screenshot 2024-10-15 164615](https://github.com/user-attachments/assets/03c67843-54ac-4f30-b982-9c384c4458ee)

- serverPool - from 192.168.1.0
- Pool-1 - from 192.168.2.0
- Pool-2 - from 192.168.3.0

### DNS Server (192.168.0.2)
![Screenshot 2024-10-15 164742](https://github.com/user-attachments/assets/f371d9c5-d8e2-4e9b-896a-6547d8d57dc4)

## Configuring Router & DHCP Relay
### Router Configuration

#### IP Addresses for each Interface
- G0/0 : 192.168.0.1 (Facing Server side)
- G1/0 : 192.168.1.1
- G2/0 : 192.168.2.1
- G3/0 : 192.168.3.1
> DNS Server Address: 192.168.0.2

### DHCP Relay setup for each Interface
```
Router# conf t
Router(config)# int g0/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int g1/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int g2/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int g3/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# exit
wr
```
## Setting IP addresses to DHCP for each client
![Screenshot 2024-10-15 165443](https://github.com/user-attachments/assets/4e426bf9-7dfd-4fa9-a60d-1a48b60cc54b)

## Overall Topology
![Screenshot 2024-10-15 165728](https://github.com/user-attachments/assets/0d776bab-f279-4dbe-bdec-e4a16321ed5b)

## Conclusion
With the setup of a DHCP and DNS server, IP address management and domain name resolution can be automated, streamlining network operations for dynamic and scalable environments.
