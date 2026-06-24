# Networking-basics-notes
My notes while learning networking and cloud computing.
# Networking Basics Notes

## Day 1

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

## Day 2 – Router Configuration

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

Result:
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

### DAY 3: ROUTER CONFIGURATION AND DHCP SETUP

# Router Information
Router IP Address: 192.168.10.1
Network Address: 192.168.10.0/24

# DHCP Assignments
- PC0: 192.168.10.10
  
- PC1: 192.168.10.11
  
- PC2: 192.168.10.12

# Verification Commands
```text
Router# show ip dhcp binding

Router# show ip interface brief
```

# Result
All PCs successfully obtained IP addresses automatically from the router's DHCP server.
All PCs can communicate with each other on the network.
The router interface GigabitEthernet0/0 is up with IP address 192.168.10.1, confirming proper DHCP and network configuration.
