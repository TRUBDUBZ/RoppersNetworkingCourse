# SANS - Layer 3 - Routing

## Routing
  
  - Routing is the process of moving packets between networks 
    
    - Routers are connected to two or more networks simultaneously
    
    - Routers have multiple network interfaces, each with their own IP address on whichever network they're connected to.   
      
    - Each router between the source and destination is called a "hop" 
  
        - for each hop, the IP TTL decrements by 1
        
        - If the TTL reaches 0, the packet expires in transit
        
          - this prevents infinite routing loops
                              
    - Routers are able to communicate with each other to share routing information or can have manually configured (static) routing tables
      
## Routing Tables

  - Routing tables are used to decide which hop to send a packet to next
  
  - Routing tables contain a list of known networks, the network interface they are on, and an default route
  
  - If a router is directly connected to the destination network, it sends the packet there; otherwise it consults the routing table to determine the next hop 
    
  - If there is no specific route to the next hop, the router sends the packet to its default gateway
  
  - If there is more than one route to a given destination, the one with the largest subnet mask should be chosen
  
    - If there is still more than one route, the one with the smallest metric should be tried first   
        
## Routing Protocols

  - Manually configuring routing tables on a large network would be very burdensome, if not impossible
    
  - Routers have several protocols they use to communicate routes to each other on a regular basis
  
    - They can dynamically adapt to network changes
        
  - Common examples include RIP, OSPF, and BGP
    
  - Many of these protocols can be abused to route traffic maliciously, such as by injecting a route to a router the attacker controls or injecting an ivalid route to block access to a resource 
    
    - Routers trust each other to be telling the truth!
  
### Interior Gateway Protocols

  - RIP (Routing Information Protocol)
    
    - Uses distance-vector routing  
    
    - Employs hop count as a metric (limited to 15 hop networks)
    
    - Broadcasts routing tables every 30 seconds
      
    - RIPv2 added support for CIDR, MD5 authentication, and uses multicast to transmit the routing tables instead of broadcasting to the entire network   
    
  - OSPF (Open Shortest Path Firts)
    
    - Uses link state routing   
    
    - Quickly detects changes in toplogy (such as link failures) and routes around them
        
    - very widely used in large enterprise networks   
        
  - EIGRP (Enhanced Interior Gateway Routing Protocol)
    
    - Cisco-proprietary advanced distance-vector protocol    

### Border Gateway Protocol (BGP)

  - BGP is the most widely used Exterior Gateway Protocol, responsible for propagating routes between Autonomous Systems (i.e., across the entire Internet)
    
    - It is also used internally in some very large private networks   
        
  - It is a path-vector protocol 
    
  - Major ISP's use BGP to determine the best routes to reach each other, allowing the Internet to funtion 
  
  - Routers always trust BGP updates, allowing a malicious ISP to pretend to be the best route to an arbitrary destination 
  
### Fragmentation

  - Some networks have a lower maximum packet size than others 
    
  - Internet Protocol (version 4) allows for fragmentation, which breaks a packet up into smaller packets 
  
    - The IP header has fields to accommodate this, allowing fragmented packets to specify the order of reassembly
      
  - IPv6 does not fragment packets 
  
  - Fragmentation should not occur in properly configured networks  
  
  - Commonly used by attackers to evade IDS and IPS
  
### IDS / IPS Evasion

  - Fragmentation reassembly timeout attacks 
    
      - The IDS/IPS has a different timeout than the target
  
  - TTL-based atttacks
    
      - Attacker manipulates TTL on fragments such that a router between the IDS/IPS and the victim drops them 
            
  - Overlapping fragments
    
      - Fragments contain overlapping payloads
          
      - Attack takes advantage of different systems reassembling the packets in a different order

### Network Address Translation

  - NAT is a technique for translating an IP address to one or more other IP addresses
  
  - It is very commonly used in home networks to allow multiple computers to share a single public IP addres  - 
  
    - This specific usage is also called Port Address Translation (PAT) because it requires changing the port numbers in the IP packet   
      
  - NAT can also be used to map a public IP address to a single private IP address
    
  - NAT helps alleviate IPv4 address exhaustion 
  
  - Requires changing IP headers
    

