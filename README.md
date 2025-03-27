# Dynamic-VLAN-assignemnt-in-a-wireless-network
Dynamic VLAN Assignment in a Wireless Network using a Core Multilayer Switch
Introduction
This project focuses on designing a wireless network with dynamic VLAN assignment using a core multilayer switch, distribution switches, a DHCP server, a Wireless LAN Controller (WLC), and access points. The goal is to implement VLAN segmentation per department (IT, HR, Finance) while ensuring proper interconnectivity, security, and scalability. The core switch performs inter-VLAN routing and DHCP relay functions, allowing seamless wireless client connectivity.
________________________________________
Key Configurations in the Multilayer Core Switch
1. VLAN Segmentation
•	VLAN 10 (Management) → 192.168.10.1/24
•	VLAN 20 (HR Department) → 192.168.20.1/24
•	VLAN 30 (Finance Department) → 192.168.30.1/24
•	VLAN 99 (Infrastructure & Management) → 192.168.99.3/24
2. IP Routing & Default Gateway
•	ip routing enabled for Layer 3 functionality.
•	Default route to 192.168.99.1, ensuring internet access.
3. DHCP Relay (IP Helper)
•	ip helper-address 192.168.99.100 configured for all VLANs.
•	Allows VLAN 10, 20, 30, and 99 clients to receive IP addresses from the DHCP server.
4. Trunk and Access Port Configuration
•	Trunk ports (Fa0/9, Fa0/10, Fa0/11, Fa0/12, Fa0/13, Fa0/24, Gi0/1) enable VLAN tagging.
•	Native VLAN 99 used for trunk ports.
•	Access ports assigned to VLANs where needed, such as Admin PC (VLAN 99) and DHCP Server (VLAN 99).
5. Wireless LAN Controller (WLC) Integration
•	WLC connected to VLANs 10, 20, and 30, allowing wireless devices to dynamically join VLANs based on authentication.
6. Spanning Tree Protocol (STP)
•	PVST (Per-VLAN Spanning Tree) Mode enabled to prevent loops.
________________________________________
Summary of Network Features Implemented
Feature	Description
VLAN Segmentation	Network divided into VLANs for IT, HR, Finance, and Management.
DHCP Relay (IP Helper)	Allows VLAN clients to receive IPs from a central DHCP server.
Inter-VLAN Routing	Core switch routes traffic between VLANs.
Trunk Links	Enables VLAN traffic across switches and WLC.
WLC Integration	Wireless clients dynamically assigned VLANs.
Security Features	VLAN separation ensures department-wise security.
Default Gateway & Static Routing	Provides internet connectivity and routes external traffic.
________________________________________
This setup ensures scalability, security, and efficiency, making it ideal for corporate networks, universities, or enterprise environments needing wireless VLAN segmentation and dynamic access control.

