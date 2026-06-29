# Networking-basics-notes
My notes while learning networking and cloud computing.
# Networking Basics Notes

# DAY 1
## SECTIONS 

### What is a Network?
A network is a group of devices connected together to share information.

### What is an IP Address?
An IP address identifies a device on a network.

### What is DNS?
DNS translates website names into IP addresses.

### My Goal
I am learning networking, Linux, AWS, GitHub, and Cloud Architecture.
### Practical Lab: Building a LAN in Cisco Packet Tracer
- Added 3 PCs (PC0, PC1, PC2)
- Added a switch
- Connected the PCs using Copper Straight-Through cables
- Configured IPv4 addresses:
  - PC0: 192.168.1.10
  - PC1: 192.168.1.20
  - PC2: 192.168.1.30
- Tested connectivity using `ping`
- Result: 0% packet loss and successful communication between all PCs.

### What I Learned Today
- Devices on the same subnet can communicate through a switch.
- `ping` is used to test network connectivity.
- Correct IP addressing is necessary for communication.

# DAY 2 – Router Configuration
## SECTIONS

### What I learned
- How to connect a router to two networks.
- How to assign IP addresses to router interfaces.
- How to enable interfaces using `no shutdown`.
- How to configure default gateways on PCs.
- How to test connectivity using `ping`.

### Router Commands
enable
configure terminal

interface gigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface gigabitEthernet0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit

do show ip interface brief

### Lab Summary
Network 1: 192.168.1.0/24
Network 2: 192.168.2.0/24

## Result:
✅ PCs on different networks can communicate through the router,because the router forwards traffic between the two subnets.

Network 1: 192.168.1.0/24
Network 2: 192.168.2.0/24

PC1:
IP Address: 192.168.1.10/24
Default Gateway: 192.168.1.1

PC2:
IP Address: 192.168.2.10/24
Default Gateway: 192.168.2.1

Connectivity Test:
ping 192.168.2.10

### Result
✅ 4 packets sent  

✅ 4 packets received  

✅ 0% packet loss  

✅ PCs on different networks can communicate through the router because the router forwards traffic between the two subnets.

# DAY 3: ROUTER CONFIGURATION AND DHCP SETUP
## SECTIONS 

## Router Information
Router IP Address: 192.168.10.1
Network Address: 192.168.10.0/24

## DHCP Assignments
- PC0: 192.168.10.10
  
- PC1: 192.168.10.11
  
- PC2: 192.168.10.12

## Verification Commands
```text
Router# show ip dhcp binding

Router# show ip interface brief
```

## Result
All PCs successfully obtained IP 
addresses automatically from the 
router's DHCP server and communicated 
successfully on the network. The 
router interface GigabitEthernet0/0 
was up with IP address 192.168.10.1, 
confirming successful DHCP 
configuration.

## Conclusion
The router was successfully configured 
as a DHCP server for the 
192.168.10.0/24 network, and all 
devices received IP addresses 
automatically.

# DAY 4: DNS CONFIGURATION AND NAME RESOLUTION
## SECTIONS

## Network Information
- Router IP Address: 192.168.10.1
- DNS Server IP Address: 192.168.10.2
- Network Address: 192.168.10.0/24

## DNS Record
- Domain Name: www.networklab.com
- IP Address: 192.168.10.10

## Verification Commands
```text```
ping 192.168.10.1
ping www.networklab.com
nslookup www.networklab.com

## ✅ RESULT


All devices successfully communicated
on the network. The DNS server
successfully resolved the domain name
`www.networklab.com` to
`192.168.10.10`, confirming that DNS
configuration and name resolution are
working correctly.

# DAY 5: INTER-NETWORK COMMUNICATION TESTING USING STATIC ROUTING
## SECTIONS

# Objective 

To verify that devices on different 
networks can communicate successfully 
after configuring static routes.

# Activities Performed

Verified router interfaces were up.
Tested connectivity between routers 
using the ping command.
Tested communication between PCs on 
different networks.
Confirmed that static routing was 
functioning correctly.

# Results

✓ Ping to 192.168.1.1 successful.

✓ Ping to 10.0.0.2 successful.

✓ Ping to 192.168.2.1 successful.

✓ Ping to 192.168.2.2 successful.

✓ End-to-end communication between both networks was achieved.

# Conclusion

The network was successfully
configured, and devices on different 
subnets were able to communicate 
through the routers using static 
routing.

# Day 6 – Switch Configuration and VLANs

## VLAN Configuration
VLAN 10 → Fa0/1, Fa0/2

VLAN 20 → Fa0/3, Fa0/4

## IP Addresses
PC0: 192.168.10.2/24

PC1: 192.168.10.3/24

PC2: 192.168.20.2/24

PC3: 192.168.20.3/24

## Ping Results
✅ PC0 → PC1 = Success

❌ PC0 → PC2 = Failed

## Conclusion
Devices in the same VLAN can communicate.
Devices in different VLANs need a router or Layer 3 switch to communicate.

VLAN 10 Network: 192.168.10.0/24

Gateway: 192.168.10.1

VLAN 20 Network: 192.168.20.0/24

Gateway: 192.168.20.1

Router-on-a-Stick allows one physical router interface to route traffic between multiple VLANs using subinterfaces and 802.1Q encapsulation.

✅ VLANs created successfully

✅ Trunk configured successfully

✅ Router subinterfaces configured successfully

✅ PCs can communicate within and across VLANs

✅ Inter-VLAN routing is working

# Day 7 - DHCP and Dynamic IP Addressing

DHCP = Dynamic Host Configuration Protocol.

DHCP automatically assigns:
- IP Address
  
- Subnet Mask
  
- Default Gateway
  
- DNS Server

DORA Process:
1. Discover
2. Offer
3. Request
4. Acknowledge

Router Configuration:

interface gig0/0
ip address 192.168.1.1 255.255.255.0
no shutdown

ip dhcp excluded-address 192.168.1.1 192.168.1.10

ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8

✅ DHCP configured successfully.

✅ PC0 and PC1 obtained IP addresses automatically.

✅ Ping test successful.

✅ 0% packet loss.


# Day 8 - Static Routing

Router0
Interface G0/0: 192.168.1.1/24

Interface G0/1: 10.0.0.1/30

ip route 192.168.2.0 255.255.255.0 10.0.0.2

Router1
Interface G0/0: 192.168.2.1/24

Interface G0/2: 10.0.0.2/30

ip route 192.168.1.0 255.255.255.0 10.0.0.1

Test:
ping 192.168.2.10

Result:

✅ 4 packets sent

✅ 4 packets received

✅ 0% packet loss
