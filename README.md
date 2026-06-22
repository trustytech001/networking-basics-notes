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
### Lab Summary
Network 1: 192.168.1.0/24
Network 2: 192.168.2.0/24

Result:
✅ PCs on different networks can communicate through the router.
