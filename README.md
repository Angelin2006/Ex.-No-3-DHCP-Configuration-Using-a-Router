## Ex. No: 3  DHCP Configuration Using a Router
Date:
________________________________________
# Objective
To configure a router to automatically assign IP addresses to client PCs using the Dynamic Host Configuration Protocol (DHCP).
________________________________________
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Router<br>
•	1 Switch<br>
•	2 PCs<br>
•	Straight-through Ethernet cables<br>
________________________________________
# Network Topology Diagram
Description:<br>
•	PC0 and PC1 are connected to Switch0.<br>
•	Switch0 is connected to Router0 on FastEthernet0/0.<br>
•	The router acts as a DHCP server for the connected LAN.<br>
(Insert screenshot of your Packet Tracer setup here)<br>
________________________________________
# IP Addressing Table
Device	Interface	IP Address	Subnet Mask<br>
Router0	FastEthernet0/0	192.168.50.1	255.255.255.0<br>
PC0	NIC	DHCP (Auto)	Assigned by DHCP<br>
PC1	NIC	DHCP (Auto)	Assigned by DHCP<br>
DHCP Pool:<br>
•	Network Address: 192.168.50.0<br>
•	Subnet Mask: 255.255.255.0<br>
•	Default Gateway: 192.168.50.1<br>
•	DNS Server: 8.8.8.8<br>
•	Excluded IP Range: 192.168.50.1 to 192.168.50.9<br>
________________________________________
# Procedure
1.	Open Cisco Packet Tracer and add 2 PCs, 1 Switch, and 1 Router.<br>
2.	Connect both PCs to the Switch using straight-through cables.<br>
3.	Connect the Switch to Router0’s FastEthernet0/0.<br>
4.	Assign the IP address 192.168.50.1 to the router’s FastEthernet0/0 interface.<br>
5.	Enable the interface using the no shutdown command.<br>
6.	Configure the router as a DHCP server:<br>
o	Define the DHCP pool with network address, default gateway, and DNS.<br>
o	Exclude gateway and reserved addresses from the pool.<br>
7.	Set both PC0 and PC1 to obtain their IP address via DHCP (auto).<br>
8.	Verify that each PC receives an IP address dynamically.<br>
9.	Use the ping command to test connectivity between the two PCs.<br>
________________________________________
# Commands Used (Router CLI)
bash<br>
CopyEdit<br>
Router> enable<br>
Router# configure terminal<br>
Router(config)# interface fastethernet0/0<br>
Router(config-if)# ip address 192.168.50.1 255.255.255.0<br>
Router(config-if)# no shutdown<br>
Router(config-if)# exit<br>

Router(config)# ip dhcp excluded-address 192.168.50.1 192.168.50.9<br>

Router(config)# ip dhcp pool MYPOOL<br>
Router(dhcp-config)# network 192.168.50.0 255.255.255.0<br>
Router(dhcp-config)# default-router 192.168.50.1<br>
Router(dhcp-config)# dns-server 8.8.8.8<br>
Router(dhcp-config)# exit<br>
________________________________________
# Output (Screenshots)

<img width="1366" height="768" alt="Screenshot 2026-10-27 160824" src="https://github.com/user-attachments/assets/594d27ff-3adb-44f3-9f74-79d555bed112" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 160848" src="https://github.com/user-attachments/assets/a43a9b87-a00f-4865-b4e3-c1981e8275a8" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 160859" src="https://github.com/user-attachments/assets/1b8b0f6d-b2c3-4c49-b32f-35dbb0e4204c" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 160912" src="https://github.com/user-attachments/assets/08a8c41b-0438-4102-9dca-9eff36b8f3e0" />

<img width="1365" height="768" alt="Screenshot 2026-10-27 160934" src="https://github.com/user-attachments/assets/effb92da-9119-42cc-a667-738b7732e522" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 160953" src="https://github.com/user-attachments/assets/8aafe904-0af2-4f2e-a347-7671fb1c480b" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 161039" src="https://github.com/user-attachments/assets/e96392e8-ae6a-4d12-a057-8fdf8062f2dc" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 161106" src="https://github.com/user-attachments/assets/9d9d1c77-0231-4010-b06d-a77f257e009e" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 161122" src="https://github.com/user-attachments/assets/d4f8e27a-f7fb-4622-86f8-a72fe2cccac4" />

<img width="1366" height="768" alt="Screenshot 2026-10-27 161141" src="https://github.com/user-attachments/assets/09251fb8-66c5-43e8-8755-3702061ce660" />
______________________________________
# Result
Successfully configured a DHCP server on the router. PCs were dynamically assigned IP addresses and were able to communicate over the network.
