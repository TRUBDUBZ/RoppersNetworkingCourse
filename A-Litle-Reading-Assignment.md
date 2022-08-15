# Practical Networking Assignment 1

 Read this on [An Intro to Networking Terminology, Interfaces, and Protocols](https://www.digitalocean.com/community/tutorials/an-introduction-to-networking-terminology-interfaces-and-protocols)

 Read this on [Routing Tables](https://www.geeksforgeeks.org/routing-tables-in-computer-network/)


1. What is an **interface**?

- In networking, an interface is a communication endpoint. each interface within a network is associated with either a physical(ethernet) or virtual(wireless internet card) device. 

- Networks usually consist of two different kinds of interfaces one for local area connections and one for internet traffic 

- The "loopback" or localhost interface is used as an interface to connect applications and processes on a single computer to other applications and processes. You can see this referenced as the “lo” interface in many tools.


2. What is **IPV4** vs **IPV6**?

- IP addresses are unique on each network and they allow machines to address each other across a network. It is implemented on the internet layer in the IP/TCP model.

- Networks can be linked together, but traffic must be routed when crossing network boundaries. This protocol assumes an unreliable network and multiple paths to the same destination that it can dynamically change between.

- The most common IP protocols are IPv4 and IPv6

    -  IPv4 has a theoretical limit of 4.3 billion addresses, which was more than enough in 1980. But as the internet grew and went global, we quickly ran out of addresses, especially in today’s era of smartphones and IoT devices.
    - The internet has been running out of IPv4 addresses since the 1990s. While clever engineers have found ways around the problem, it wasn’t long before a more permanent fix was needed. Developed to solve these capacity issues for good, IPv6 was needed when IPv4 could no longer support the load.
   - At present, IPv4 coexists on the internet with its newer version, though eventually, everything will use IPv6. Replacing old IPv4 equipment would be prohibitively expensive and disruptive, and so IPv6 is being slowly rolled out as older IPv4 hardware is retired.


  - Internet Protocol version 6, or IPv6 was first introduced in the late 1990s as a replacement for IPv4. It uses 128-bit addresses formatted as eight groups of four hexadecimal numbers separated by colons. IPv6 is the solution that addresses the relatively limited number of IP addresses possible under IPv4. Under IPv6, there will no longer be a shortage of the total number of possible addresses.
  - IPv6 allows for a theoretical 340,282,366,920,938,463,463,374,607,431,768,211,456, or 340 undecillion addresses. This means that every device on the internet can have a unique IPv6 address. An example IPv6 address looks like this — 2002:0de6:0001:0042:0100:8c2e:0370:7234 — but there are ways to abbreviate this rather clunky notation.


3. What is a **MAC Address**?

- Medium Acess Control is a communications protocol, its purpose is to distinguish devices from one another. Each device gets a unique **Media Access Control address** (MAC Address) when it gets manufactured. This address is used to identify devices from one another.
- Addressing hardware by the MAC address allows you to reference a device by a unique value even when the software on top may change the name for that specific device during operation.


4. How do **Routing Tables** work?

- When a packet arrives at a Router, it examines the destination IP address of a received packet and makes routing decisions accordingly. Routers use **Routing Tables** to determine out which interface the packet will be sent. A routing table lists all networks for which routes are known. Each router’s routing table is unique and stored in the RAM of the device.
- A routing table is a set of rules, often viewed in table format, that is used to determine where data packets traveling over an Internet Protocol (IP) network will be directed. All IP-enabled devices, including routers and switches, use routing tables.

- Routing Tables provide devices with instructions for sending packets to the next hop on its route across networks.

- When a router receives a packet, it examines the destination IP address, and looks up into its Routing Table to figure out which interface packet will be sent out.


5. What is a **protocol**? What are some common protocols?

- In networking a protocol is a set of rules for formatting and processing data. Protocols are like a common language. The devices within a network use different software and hardware; however, the use of protocols enables them to communicate with eachother regardless of their differences. 

- Some examples of common protocols:

  - Network Time Protocol - **NTP** - a protocol that synchronizes the clocks of computer systems over data networks. 

  - Domain Name System - **DNS** - Resolves a Uniform Resource Locator (URL) or website address to the IP address of the site. When users type a web address into the search bar, they rely on DNS servers to resolve the actual IP address of that destination. DNS translates domain names to IP addresses.  

  - Dynamic Host Control Protocol - **DHCP** - Dynamic Host Control Protocol (DHCP) uses a server to allocate an IP address and other configuration information to network devices. As a result, the device is getting a permission slip from the DHCP server to use the network. DHCP enables users to send a request to the DHCP server whenever they connect to a network. The server recognizes by providing an IP address to the user. DHCP is also known as RFC 2131.  

 
