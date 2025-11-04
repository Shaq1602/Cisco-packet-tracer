1. Project Overview

This project demonstrates a Hybrid Topology integrating five known topologies:
Bus, Star, Ring, Mesh, and Extended Star.
The design was implemented using Cisco Packet Tracer to simulate a realistic network connecting multiple departments, switches, routers, and PCs.

2. Objectives

Integrate multiple network topologies into a single hybrid design.

Assign IP addresses using IPv4.

Configure inter-device communication (ping, messaging, VLANs).

Demonstrate message transmission from one PC to another.

Analyze performance and topology advantages.

Network Components
| Device Type | Quantity | Example Device Name                 | Description                                      |
| ----------- | -------- | ----------------------------------- | ------------------------------------------------ |
| PCs         | 10       | PC0 – PC9                           | Workstations connected across the hybrid network |
| Switches    | 4        | Switch0 – Switch3                   | Used in Star and Extended Star segments          |
| Routers     | 2        | Router0, Router1                    | Connects different topologies/subnets            |
| Servers     | 1        | Server0                             | Centralized service (DHCP, DNS, or Web)          |
| Cables      | Multiple | Copper straight-through, Serial DCE | Used to connect PCs, switches, and routers       |

Core Network Services
| Device                 | IPv4 Address  | Subnet Mask   | IPv6 Address         | Prefix | Default Gateway |
| ---------------------- | ------------- | ------------- | -------------------- | ------ | --------------- |
| **HTTP Server**        | 192.168.1.100 | 255.255.255.0 | fd00:db8:face:1::100 | /64    | 192.168.1.1     |
| **DNS Server**         | 192.168.1.101 | 255.255.255.0 | fd00:db8:face:1::101 | /64    | 192.168.1.1     |
| **3550 Switch (Core)** | 192.168.1.1   | 255.255.255.0 | fd00:db8:face:1::1   | /64    | -               |


Star Department (VLAN 10 – Staff)
| Device                      | IPv4 Address  | Subnet Mask   | IPv6 Address         | Prefix | Default Gateway |
| --------------------------- | ------------- | ------------- | -------------------- | ------ | --------------- |
| **PC7**                     | 192.168.10.10 | 255.255.255.0 | fd00:db8:face:10::10 | /64    | 192.168.10.1    |
| **PC8**                     | 192.168.10.11 | 255.255.255.0 | fd00:db8:face:10::11 | /64    | 192.168.10.1    |
| **Star-sw (Access Switch)** | 192.168.10.1  | 255.255.255.0 | fd00:db8:face:10::1  | /64    | -               |

| Device  | IPv4 Address  | Subnet Mask   | IPv6 Address         | Prefix | Default Gateway |
| ------- | ------------- | ------------- | -------------------- | ------ | --------------- |
| **PC5** | 192.168.20.10 | 255.255.255.0 | fd00:db8:face:20::10 | /64    | 192.168.20.1    |
| **PC6** | 192.168.20.11 | 255.255.255.0 | fd00:db8:face:20::11 | /64    | 192.168.20.1    |

Topology Design

The Star segment connects PCs to a central switch.

The Ring section connects three switches in a closed loop.

The Bus segment connects PCs on a single linear backbone.

The Mesh segment interconnects routers for redundancy.

The Extended Star links the Star and Bus segments through an additional switch.

Results & Observations

All PCs successfully communicated across subnets.

Routers properly routed packets between topologies.

Hybrid structure improved reliability and reduced congestion

Challenges Faced

Misconfigured IP addresses caused initial ping failures.

Loop prevention in Ring topology required switch configuration.

Packet loss observed before enabling router interfaces.

Conclusion

This project successfully implemented a hybrid network integrating multiple topologies. The design promotes scalability, redundancy, and efficient communication — essential characteristics of real-world enterprise networks.
