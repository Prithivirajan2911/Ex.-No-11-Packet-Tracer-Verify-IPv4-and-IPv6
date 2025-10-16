# Ex. No: 11 – Packet Tracer: Verify IPv4 and IPv6 Addressing
## Date: 14-10-2025
## Name: Prithivirajan V
## RegNo: 212223100042
<br>

# Objective
To configure, verify, and test dual-stack (IPv4 and IPv6) addressing on a Cisco Packet Tracer network topology.<br>
Tasks:<br>
• Document IPv4 and IPv6 addressing details.<br>
• Test connectivity using ping for both protocols.<br>
• Trace the route of packets to verify end-to-end connectivity.<br>
<br>

# Apparatus / Tools Required
• Cisco Packet Tracer<br>
• 3 Routers (R1, R2, R3 – 2911 or equivalent)<br>
• 2 PCs (PC1, PC2)<br>
• Copper straight-through and Serial DCE/DTE cables<br>
<br>

# Network Topology Diagram
(Insert your Packet Tracer screenshot showing R1–R2–R3 in series and PCs connected to edge routers.)<br>
<br>

# Addressing Table

| Device |	Interface |	IPv4 Address / Subnet Mask |	IPv6 Address / Prefix |	Default Gateway |
|--------|------------|----------------------------|------------------------|-----------------|
| R1	   |G0/0   |	10.10.1.97 / 255.255.255.224   |	2001:db8:1:1::1/64    |	N/A             |
| R1	   |S0/0/1 |	10.10.1.6 / 255.255.255.252    |	2001:db8:1:2::2/64    |	N/A             |
| R2	   |S0/0/0 |	10.10.1.5 / 255.255.255.252    |	2001:db8:1:2::1/64    |	N/A             |
| R2	   |S0/0/1 |	10.10.1.9 / 255.255.255.252    |	2001:db8:1:3::1/64    |	N/A             |
| R3	   |G0/0   |	10.10.1.17 / 255.255.255.240   |	2001:db8:1:4::1/64    |	N/A             |
| R3	   |S0/0/1 |	10.10.1.10 / 255.255.255.252   |	2001:db8:1:3::2/64    |	N/A             |
| PC1	   |NIC    |	(IPv4 auto/DHCP)               |	(IPv6 auto-config)    |	R1 G0/0         |
| PC2	   |NIC    |	(IPv4 auto/DHCP)               |	(IPv6 auto-config)    |	R3 G0/0         |

## DHCP Configured IPs for PC1 and PC2
| Device |	Interface |	IPv4 Address / Subnet Mask |	IPv6 Address / Prefix |	Default Gateway |
|--------|------------|----------------------------|------------------------|-----------------|
| PC1	   |NIC    |	10.10.1.100              |	2001:DB8:1:4::A    |	R1 G0/0         |
| PC2	   |NIC    |	10.10.1.20               |	2001:DB8:1:1::A    |	R3 G0/0         |


<br>

# Procedure

## Part 1: Verify IPv4 and IPv6 Addressing
1.	On PC1, open Command Prompt → enter:<br>
2.	ipconfig /all<br>
Record IPv4 address, subnet mask, and gateway.<br>
3.	On PC2, repeat the same.<br>
4.	For IPv6 verification:<br>
5.	ipv6config /all<br>
Record IPv6 address, prefix, and default gateway for both PCs.<br>
<br>

## Part 2: Test Connectivity Using Ping
1.	From PC1, ping the IPv4 address of PC2.<br>
2.	ping 10.10.1.20<br>
o	Verify success (Reply from 10.10.1.20).<br>
3.	From PC2, ping the IPv6 address of PC1.<br>
4.	ping 2001:db8:1:1::a<br>
o	Verify success for IPv6 reachability.
<br>

## Part 3: Discover the Path Using Traceroute
1.	From PC1, trace route to PC2 using IPv4:<br>
2.	tracert 10.10.1.20<br>
Observe the hops across R1 → R2 → R3.<br>
3.	From PC2, trace route to PC1 using IPv6:<br>
4.	tracert 2001:db8:1:4::a<br>
Record IPv6 path hops.<br>
<br>

## Commands Used (Summary)
Purpose	Command<br>
Check IPv4 details	**ipconfig /all**<br>
Check IPv6 details	**ipv6config /all**<br>
Ping test (IPv4/IPv6)	**ping <IP>**<br>
Trace path (IPv4/IPv6)	**tracert <IP>**<br>
<br>

## Verification & Testing
• Successful ping replies indicate proper dual-stack connectivity.<br>
• Trace route confirms correct path through routers R1–R2–R3.<br>

<br>

# Output
## • ipconfig /all and ipv6config /all output for both PCs.<br>
### PC1
#### IPCONFIG V4
<img width="877" height="889" alt="Screenshot 2025-10-14 192347" src="https://github.com/user-attachments/assets/4fe53015-086a-47e4-9c61-77d539392097" />

#### IPCONFIG V6
<img width="738" height="392" alt="Screenshot 2025-10-14 192417" src="https://github.com/user-attachments/assets/7b1953d8-9447-482c-821a-cf310b3fc36c" />

### PC2
#### IPCONFIG V4
<img width="877" height="889" alt="Screenshot 2025-10-14 192522" src="https://github.com/user-attachments/assets/3b3aa110-e536-498a-8e38-574bf12cf44e" />

#### IPCONFIG V6
<img width="692" height="310" alt="Screenshot 2025-10-14 192542" src="https://github.com/user-attachments/assets/61ace31a-cbb8-4f10-870c-ffaa2214f39c" />

<br>

## • Ping results for IPv4 and IPv6.<br>
### PC1 to PC2
#### IPv4

<img width="589" height="224" alt="Screenshot 2025-10-14 192837" src="https://github.com/user-attachments/assets/b5e10c89-db80-42cd-96af-0b118c18948d" />

#### IPv6

<img width="627" height="221" alt="image" src="https://github.com/user-attachments/assets/6e9bafc8-5faa-4e98-ae31-129a6865637c" />

### PC2 to PC1
#### IPv4

<img width="569" height="225" alt="Screenshot 2025-10-14 193208" src="https://github.com/user-attachments/assets/6098633b-7b39-478c-81a8-faaa97902499" />

#### IPv6

<img width="567" height="227" alt="image" src="https://github.com/user-attachments/assets/8bc9967e-2b07-4016-acfd-d5a8070c8398" />

<br>

## • Traceroute results showing intermediate hops.<br>

### From PC1 Traceroute to PC2

<img width="583" height="173" alt="image" src="https://github.com/user-attachments/assets/8c6c16f5-a527-4e46-896b-9e3eac027bb3" />

### From PC2 Traceroute to PC1

<img width="567" height="175" alt="image" src="https://github.com/user-attachments/assets/763c4dde-3826-4b47-9c5b-9960e108f20d" />

<br>


# Result
The dual-stack IPv4 and IPv6 addressing scheme was successfully verified. Both addressing types achieved full connectivity between PC1 and PC2 through multiple routers, confirming correct configuration and routing.
