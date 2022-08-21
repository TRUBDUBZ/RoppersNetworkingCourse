# SANS - Layer 3 - Network, Part 1: Addressing & Masking

**The Network Layer**

- The network layer enables individual networks to be connected together by routing packets between those networks    
  
  * It adds Layer 3 addresses to Layer 2 frames to form packets  

- Routers operate at the Network Layer 

- IP addresses are used to identify hosts at the Network Layer 

## Binary Numbers 

- Binary numbers work just like decimal (base 10) numbers, except instead of having the digits 0-9 to work with, there are only 0 and 1

- Instead of having "1's place", a "10's place", etc, there is a "1's place", a "2's place", a "4's place", and so on for powers of 2.

- To convert a binary number to decimal, add the decimal number corresponding to each bit that is 1. For example, here is the number 166 represented in binary:

1    0    1    0    0    1    1    0    = 166
128  64   32   16   8    4    2    1    = 128 + 32 + 4 + 2 = 166 


## IP Addresses

- An IP address uniquely identifies your computer on a network
  
  - typically assigned automatically or by an administrator 

- IP addresses are used to route packets between network
  
  - On the internet, data is encapsulated inside an IP packet with the source and destination IP addresses 
  
  - Routers use the destination address to forward packets to the next closest router on the path to the destination 
  
- Most computers will still us IPv4, but we are slowly moving towards IPv6

- Ip addresses are 32-bit numbers, typically represented in dotted-quad notation, which is a set of 4 octets (eg 192.168.101.42)
  
  - each octet represents 8 binary bits (eg 11000000)

- The first portion of the IP address denotes the network, and the rest denotes the address on that network (depending on the class or CIDR mask)

192.168.101.42

### IP Address Classes(1)

- Class A(0-127)(Netmask: 255.0.0.0) 
 
  - First 8 bits are the network portion, and the last 24 bits are the Host portion(ie, the IP address "10.20.30.40" is on the "10.0.0.0" network)
  - 128 possible networks, each with 16,777,214 possible host addresses 

- Class B(128-191)(Netmask: 255.255.0.0)
  
  - First 16 bits are the network portion, and the last 16 bits are the Host portion(ie the IP address "172.16.34.3" is on the "172.16.0.0" network)
  - 16,384 possible networks, each with 65,534 possible host addresses 

- Class C(192-223)(Netmask:255.255.255.0)
  
  - First 24 bits are the Network portion, and the last 8 bits are the Host portion(ie, the IP address "192.168.101.42" is on the "192.168.101.0" network) 
  - 2,097,152 possible networks, each with 254 possible host addresses 
  
- Class D(224-239)
  
  - Used for Multicast

- Class E(240-255)
  
  - Reversed

### Reversed Addresses

- Many addresses (or ranges of addresses) are reserved for special purposes

- The first address on any network is reserved as the network identifier

- The last address on any network is reserved as the broadcast address (such ass 255.255.255.255)

- 127.0.0.0-127.255.255.255 are reserved as your local loopback address

- 169.254.0.0-169.254.255.255 are reserved for link local addresses (APIPA) 

- 10.0.0.0 - 10.255.255.255, 172.16.0.0-172.31.255.255, and 192.168.0.0-192.168.255.255 are all reserved for use on private (internal) networks

### IPv6 Addresses

- IPv6 was developed due to IPv4 address exhaustion

- IPv6 addresses are 128 bits in length(4x larger than IPv4)

- IPv6 addresses are generally written as 8 groups of 16-bit hexadecimal values separated by colons
  
  - leading zeroes within a 16-bit group can be ommitted
  
  - groups of zeroes can be replaced with a double colon

- Example address: 2001:0db8:85a3:0000:0000:8a2e:0370:7334

- Shortened example: 2001:db8:85a3::8a2e:370:7334

### Review

1. 192.452.199.504 is an example of a:
  
  a. IPv4 address 
  b. IPv6 address
  c. MAC address
  d. None of the above xx

2. Ping the IP address 127.54.100.12 Does it respond? 
  
  a. That IP address is the NAT address of your windows firewall
  b. Youre pinging your loopback address, which is any address with the first octet being 127 xx
  c. That IP address for the Web based management interaace to the Windows Firewall 


## Subnet Masks 
 
- Subnet Masks (also called netmasks) are used to identify the different parts of the IP address(Network and Host portions)
  
    - - they identify which bits of an IP address refer to the network address 

- In binary form, the bits that make up the subnet mask correspond to the bits that make up the network address 

- - For example, here is an IP address on a standard class B network and its subnet mask (the first two octets are the network address)
  
  IP [10101100.00010000].00100010.00000011
  Netmask [11111111.11111111].00000000.00000000

### Binary / Bitwise AND

- In networking, the bitwise AND operation can be used on the IP address and subnet mask to determine the network identifier- 

- The result of an AND is "1" if both bits being compared are 1; otherwise, the result is 0.

### Classless Inter-Domain Routing (CIDR)

- While IP address classes helped make IP assignments and subnetting more flexible enough

- Classless Inter-Domain Routing (or CIDR) allows for much more flexible subdivisions of network space by allowing any number of bits to define the network address

- A CIDR netmask is typically represented by a forward slash followd by the number of bits in the subnet mask that are set to 1. 

  - For example, 10.32.28.1/24 corresponds to the subnet mask 255.255.255.0, meaning the first 24 bits of the subnet are 1 

- By designm CIDR doesn't have to follow class rules

  - Arbitrary IP ranges can be split into smaller ones, and values other than /8, /16, and /24 are allowed

#### Review 

  1. What would the default subnet mask be for the IP range 172.16.0.0/16?
    
    a. 255.0.0.0  
    b. 255.255.0.0 xx - A "/16" CIDR mask corresponds to the subnet mask 255.255.0.0 because the first 16 bits are set to 1.
    c. 255.255.248.0
    d. 255.255.255.0
  
  2. There are two devices with the IP address 10.10.5.5 and 10.10.10.10 which of the following subnet masks will logically place both devices on the same network?
    
    a. 255.255.0.0 xx - Performing a Bitwise AND with each subnet mask would show that the only one places both IP addresses on the network is 255.255.0.0
    b. 255.255.255.0
    c. 255.255.255.128
    d. 255.255.255.248

### Default Gateways

- Computers are able to communicate directly with other systems on the same Layer 2 network segment 
  
  - Your computer can determine whether another system is on the same network by checking its own IP address and subnet mask 

- To communicate with systems on different networks, your computer needs to communicate through its **Defualt Gateway** 

- The default gateway is a router on your network that your computer will send traffic to that it doesn't know how to route itself
  
  - It routes traffic on to its destination
  
  - It is typically the closest router to the computer or device
    
#### Review 

  1. True/False: In order to communicate with devices on the same subnet, a computer must communicate with its Default Gateway
    
    a. False, computers on the same subnet can communicate directly with one another

  2. Host 1 (192.168.6.10/24) wants to send a packet to Host 2 (192.168.47.35/24). Which path will this packet take to reach its destination, assuming that both 192.168.6.0 and 192.168.47.0
  
    a. Host 1 -> default gateway -> Host 2
      - The two hosts are not on the same subnet, so the packet is first sent to the defualt gateway, which consults its routing table and sends the packet to destination host.
    

### DHCP - Dynamic Host Configuration Protocol

- Manually configuring the IP address, subnet mask, defualt gateway, etc. on a large number of computers can be time consuming

- DHCP is a protocol for networked devices to automatically determine their network configuration, such as their IP address, subnet mask, default gatway, and DNS servers

- On home networks, the default gateway generally acts as the DHCP server as well 

- DHCP servers assign (or "lease") an IP address for a limited period of time, after which clients are required to renew the lease

- If a DHCP server is unavailable, the computer will assign itself a link-local (APIPA) address between 169.254.1.0 and 169.254.254.255. The first and last 256 addresses of 169.254.0.0/16 are reserved per RFC 3927


#### DHCP Details

- When a client needs an IP address, it broadcasts a DHCP Discovery packet to the entire network

- Any DHCP server that sees the request and has IP addresses available will respond with a DHCP offer

- The client will respond to the first DHCP offer it receives with a DHCP Request, formally requesting the IP address it was offered

  - Race conditions for a malicious respons!
  
- The DHCP server will reply with a DHCP Acknowledgement, formally leasing the IP address to the client and also providing any other details the client needs, such as the subnet mask, default gateway, and DNS servers

**Remember DORA** 

##### Review 

What are the 4 steps followed by a DHCP Client to obtain an IP address?

1. DHCPDiscover, DHCPOffer, DHCPRequest, DHCPAck xx DORA

2. DHCPDiscover, DHCPOffer, DHCPAssign, DHCPAccept

3. DHCPRequest, DHCPReply, DHCPAssign, DHCPAccept

4. DCHPRequest, DCHPResponse, DHCPAssign, DHCPAccept

Several computers on your network are being assigned the wrong DNS server IP address. You visit them and verify that they are using DHCP. What might be a possible cause?

a. The DHCP server has issued all of the DNS server IP addresses in its pool

b. The DHCP server lease pool is exhausted

c. The DNS server is offline, so the DHCP server is redirecting traffic

d. Someone has setup another DHCP server xx = An attacker may have set up a rogue DHCP server in order to control the client computers network information, such as which DNS server they use. The attacker could point them to his or her own DNS server, allowing interception or manipulation of all traffic!





