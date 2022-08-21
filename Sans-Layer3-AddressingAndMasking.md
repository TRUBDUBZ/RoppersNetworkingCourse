# SANS - Layer 3 - Network, Part 1: Addressing & Masking

## The Network Layer

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

Ip addresses are 32-bit numbers, typically represented in dotted-quad notation, which is a set of 4 octets (eg 192.168.101.42)
  - each octet represents 8 binary bits (eg 11000000)

The first portion of the IP address denotes the network, and the rest denotes the address on that network (depending on the class or CIDR mask)

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
  a. IPv4 address xx
  b. IPv6 address
  c. MAC address
  d. None of the above

2. Ping the IP address 127.54.100.12 Does it respond? 
  a. That IP address is the NAT address of your windows firewall
  b. Youre pinging your loopback address, which is any address with the first octet being 127
  c. That IP address for the Web based management interaace to the Windows Firewall 


## Subnet Masks 

- Subnet Masks (also called netmasks) are used to identify the different parts of the IP address(Network and Host portions)
  - they identify which bits of an IP address refer to the network address 

- In binary form, the bits that make up the subnet mask correspond to the bits that make up the network address 
- For example, here is an IP address on a standard class B network and its subnet mask (the first two octets are the network address)
  
  IP [10101100.00010000].00100010.00000011
  Netmask [11111111.11111111].00000000.00000000

### Binary / Bitwise AND

- In networking, the bitwise AND operation can be used on the IP address and subnet mask to determine the network identifier- 

- The result of an AND is "1" if both bits being compared are 1; otherwise, the result is 0.

**TO BE CONTINUED** 
