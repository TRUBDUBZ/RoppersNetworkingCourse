# Network Terminology And Protocols

## Networking Terminology


- Connection

    - In networking, a connection refers to pieces of related information that are transfered through a network. This generally infers that a connection is built before the data transfer (by following the procedures laid out in a protocol) and then is deconstructed at the at the end of the data transfer.

- Packet

    - A packet is, generally speaking, the most basic unit that is transfered over a network. When communicating over a network, packets are the envelopes that carry your data ( in pieces ) from one end point to another.

 - Network Interface

    - A network interface can refer to any kind of software interface to networking hardware. For instance, if you have two network  cards in your computer, you can control and configure each network interace associated with them individually.

- LAN

    - LAN stands for “local area network”. It refers to a network or a portion of a network that is not publicly accessible to the greater internet. A home or office network is an example of a LAN.  

- WAN

    - WAN stands for "Wide Area Network". It means a network that is much more extensive than a LAN. While WAN is the relevant term to use to describe large, dispersed networks in general, it is usually meant to mean the internet, as a whole. If an interface is said to be connected to the WAN, it is generally assumed that it is reachable through the internet.

- Protocol

    - A protocol is a set of rules and standards that basically define a language that devices can use to communicate. There are a great number of protocols in use extensively in networking, and they are often implemented in different layers.

    - Some low level protocols are TCP, UDP, IP, and ICMP. Some familiar examples of application layer protocols, built on these lower protocols, are HTTP (for accessing web content), SSH, TLS/SSL, and FTP. 

- Port

  - A port is an address on a single machine that can be tied to a specific piece of software. It is not a physical interface or location, but it allows your server to be able to communicate using more than one application.

- Firewall

  - A firewall is a program that decides whether traffic coming into a server or going out should be allowed. A firewall usually works by creating rules for which type of traffic is acceptable on which ports. Generally, firewalls block ports that are not used by a specific application on a server.

- NAT

  - NAT stands for network address translation. It is a way to translate requests that are incoming into a routing server to the relevant devices or servers that it knows about in the LAN. This is usually implemented in physical LANs as a way to route requests through one IP address to the necessary backend servers.

- VPN

  - VPN stands for virtual private network. It is a means of connecting separate LANs through the internet, while maintaining privacy. This is used as a means of connecting remote systems as if they were on a local network, often for security reasons.


## Interfaces

  - Interfaces are networking communication points for your computer. Each interface is associated with a physical or virtual networking device.

  - Typically, your server will have one configurable network interface for each Ethernet or wireless internet card you have.
  
   - In addition, it will define a virtual network interface called the “loopback” or localhost interface. This is used as an interface to connect applications and processes on a single computer to other applications and processes. You can see this referenced as the “lo” interface in many tools. 
   
  - Many times, administrators configure one interface to service traffic to the internet and another interface for a LAN or private network. 
  
  - In DigitalOcean, in datacenters with private networking enabled, your VPS will have two networking interfaces (in addition to the local interface). The “eth0” interface will be configured to handle traffic from the internet, while the “eth1” interface will operate to communicate with the private network. 

## Protocols 
 
 - Networking works by piggybacking a number of different protocols on top of each other. In this way, one piece of data can be transmitted using multiple protocols encapsulated within one another. 

 - We will talk about some of the more common protocols that you may come across and attempt to explain the difference, as well as give context as to what part of the process they are involved with. 
  
 - We will start with protocols implemented on the lower networking layers and work our way up to protocols with higher abstraction.

## Medium Acess Control 

 - Medium access control is a communications protocol that is used to distinguish specific devices. Each device is supposed to get a unique media access control address (MAC address) during the manufacturing process that differentiates it from every other device on the internet. 
  
 - Addressing hardware by the MAC address allows you to reference a device by a unique value even when the software on top may change the name for that specific device during operation. Medium access control is one of the only protocols from the link layer that you are likely to interact with on a regular basis. 

## IP 

 - The IP protocol is one of the fundamental protocols that allow the internet to work. IP addresses are unique on each network and they allow machines to address each other across a network. It is implemented on the internet layer in the IP/TCP model. 

 - Networks can be linked together, but traffic must be routed when crossing network boundaries. This protocol assumes an unreliable network and multiple paths to the same destination that it can dynamically change between.

 - There are a number of different implementations of the protocol. The most common implementation today is IPv4, although IPv6 is growing in popularity as an alternative due to the scarcity of IPv4 addresses available and improvements in the protocols capabilities.


## ICMP 

 - ICMP stands for internet control message protocol. It is used to send messages between devices to indicate the availability or error conditions. These packets are used in a variety of network diagnostic tools, such as ping and traceroute.

- Usually ICMP packets are transmitted when a packet of a different kind meets some kind of a problem. Basically, they are used as a feedback mechanism for network communications.

## TCP

- TCP stands for transmission control protocol. It is implemented in the transport layer of the IP/TCP model and is used to establish reliable connections.

TCP is one of the protocols that encapsulates data into packets. It then transfers these to the remote end of the connection using the methods available on the lower layers. On the other end, it can check for errors, request certain pieces to be resent, and reassemble the information into one logical piece to send to the application layer.

## UDP 

- UDP stands for user datagram protocol. It is a popular companion protocol to TCP and is also implemented in the transport layer.

- The fundamental difference between UDP and TCP is that UDP offers unreliable data transfer. It does not verify that data has been received on the other end of the connection. This might sound like a bad thing, and for many purposes, it is. However, it is also extremely important for some functions.

- Because it is not required to wait for confirmation that the data was received and forced to resend data, UDP is much faster than TCP. It does not establish a connection with the remote host, it simply fires off the data to that host and doesn’t care if it is accepted or not.

- Because it is a simple transaction, it is useful for simple communications like querying for network resources. It also doesn’t maintain a state, which makes it great for transmitting data from one machine to many real-time clients. This makes it ideal for VOIP, games, and other applications that cannot afford delays.

## HTTP

  - HTTP stands for hypertext transfer protocol. It is a protocol defined in the application layer that forms the basis for communication on the web.

  - HTTP defines a number of functions that tell the remote system what you are requesting. For instance, GET, POST, and DELETE all interact with the requested data in a different way.
    
## FTP 

  - FTP stands for file transfer protocol. It is also in the application layer and provides a way of transferring complete files from one host to another.

  - It is inherently insecure, so it is not recommended for any externally facing network unless it is implemented as a public, download-only resource.

## DNS

  - DNS stands for domain name system. It is an application layer protocol used to provide a human-friendly naming mechanism for internet resources. It is what ties a domain name to an IP address and allows you to access sites by name in your browser.

## SSH

  - SSH stands for secure shell. It is an encrypted protocol implemented in the application layer that can be used to communicate with a remote server in a secure way. Many additional technologies are built around this protocol because of its end-to-end encryption and ubiquity.

  - There are many other protocols that we haven’t covered that are equally important. However, this should give you a good overview of some of the fundamental technologies that make the internet and networking possible.

## Conclusion 

  - At this point, you should be familiar with some basic networking terminology and be able to understand how different components are able to communicate with each other. This should assist you in understanding other articles and the documentation of your system.
