# Routing Tables In Networking

## Routers:

A router is a networking device that forwards data packets between computer networks. This device is usually connected to two or more different networks. When a data packet comes to a router port, the router reads the address info in the packet to determine out which port the packet will be sent to. 

For example, a router provides you with internet access by connecting your LAN with the internet.

When a packet arrives at a Router, it examines the destination IP address of a received packet and makes routing decisions accordingly. Routers use *routing tables* to determine out which interface the packet will be sent. A routing table lists all networks for which routes are known. Each router's routing table is unique and stored in the RAM of the device. 

## Routing Tables:

A Routing Table is a set of rules, often viewed in table format, that is used to determine where data packets traveling over an Internet Protocol (IP) network will be directed. All IP-enabled devices, including routers and switches, use routing tabeles. See below a Routing Table:

`
Destination      Subnet mask         Interface
 128.75.43.0      255.255.255.0       Eth0
 128.75.43.0      255.255.255.128     Eth1
 192.12.17.5      255.255.255.255     Eth3
 default                              Eth2
`

The entry corresponding to the default gateway configuration is a network destination of 0.0.0.0 with a network mask (netmask) of 0.0.0.0. The Subnet Mask of default route is always 255.255.255.255 .

### Entries of an IP Routing Table:

A routing table contains the information necessary to forward a packet along the best path toward its destination. Each packet contains information about its origin and destination. Routing Table provides the device with instructions for sending the packet to the next hop on its route across the network.

Each entry in the routing table consists of the following entries:
------------------------------------
1. Network ID:
The network ID or destination corresponding to the route

2. Subnet Mask:
The mask that is used to match a destination IP address to the network ID

3. Next Hop:
The IP address to which the packet is forwarded

4. Outgoing Interface:
Outgoing interface the packet should go out to reach the destination network

5. Metric:
A common use of the metric is to indicate the minimum number of hops (routers crossed) to the network ID

------------------------------
Routing table entries can be used to store the following types of routes:

- Directly Attached Network IDs
- Remote Network IDs
- Host Routes
- Default Route
- Destination

`When a router receives a packet, it examines the destination IP address, and looks up into its Routing Table to figure out which interface packet will be sent out.`

#### How are Routing Tables Populated?
There are a few ways to maintain Routing Tables:

- Directly connected networks are added automatically 
- Using [Static Rounding](https://www.geeksforgeeks.org/difference-between-static-and-dynamic-routing/)
- Using [Dynamic Routing](https://www.geeksforgeeks.org/difference-between-static-and-dynamic-routing/)

- These Routing tables can be maintained manually or dynamically. In dynamic routing, devices build and maintain their routing tables automatically by using routing protocols to exchange information about the surrounding network topology. Dynamic routing tables allow devices to “listen” to the network and respond to occurrences like device failures and network congestion. Tables for static network devices do not change unless a network administrator manually changes them.- 

##### Route Determination Process (finding Subnet ID using Routing Table): 
Consider a network is [subnetted into 4 subnets](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-subnetting/) the IP address of the 4 subnets are:
`
200.1.2.0 (Subnet a)
200.1.2.64 (Subnet b)
200.1.2.128 (Subnet c)
200.1.2.192 (Subnet d) 
`

Then, **Routing table** maintained by the internal router looks like:

`
Destination	   Subnet Mask	    Interface

200.1.2.0	     255.255.255.192	   a
200.1.2.64	   255.255.255.192     b
200.1.2.128	   255.255.255.192	   c
200.1.2.192	   255.255.255.192	   d
Default        0.0.0.0             e
`


To find its right [subnet](https://www.geeksforgeeks.org/introduction-to-subnetting/) (subnet ID), router performs the bitwise ANDing of destination IP Address mentioned on the data packet and all the subnet masks one by one.

- If there occurs only one match, router forwards the data packet on the corresponding interface.

- If there occurs more than one match, router forwards the data packet on the interface corresponding to the longest subnet mask.

- If there occurs no match, router forwards the data packet on the interface corresponding to the default entry.

Example-1: [GATE-CS-2004 | Question 55](https://www.geeksforgeeks.org/gate-gate-cs-2004-question-55/)

Example-2: [GATE IT 2006 | Question 63](https://www.geeksforgeeks.org/gate-gate-it-2006-question-63/)

**Note** that the routing tables are not specific for Cisco devices. Even your Windows operating system has a routing table that can be displayed using the route print command


