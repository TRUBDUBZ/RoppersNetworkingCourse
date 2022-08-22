# Sans - Introduction and Layer 1

[SANS - CyberAces - Networking - Intro and Layer 1](https://www.sans.org/cyberaces/networking)


- Humans need certain things to communicate
  - a medium, such as air or paper, a language, and a set of rules or "protocols" for how to behave and interact
  
- Computers also need these things to communicate

- Protocols establish a set of rules and procedures for how systems interact with eachother

  - "first ill send a SYN, then you send a SYN-ACK, then ill send and ACK."
  

## Introduction to the OSI Model

    7. Application
    6. Presentation
    5. Session
    4. Transport
    3. Network 
    2. Data Link
    1. Physical
    

  - The osi model divides networking protocols into 7 layers, each representing a layer of encapsulation between the highest level. (an application) and the lowest level (physical signals)

  - The OSI model divides networking protocols into 7 layers, each representing a layer of encapsulation between the highest level. (an application) and the lowest level (physical signals)

    
  - Many devices do not need to communicate at all layers. e.g. a network switch doesn't need to understand HTTP
 
  - Data is encapsulated like so:  
    - Data  ->  Segment Data  ->  Packet  ->  Frame  ->  Bits(0010101001010)
    
### Review 

  1. HTTP is a protcol that operates at what layer of the OSI model?
      
    - Layer 3
    - Layer 4
    - Layer 6
    - Layer 7  x
  
  2. In which layer do switches operate? 
   
    - Layer 1
    - Layer 2  x
    - Layer 3
    - Layer 4 
 
#### Physical Layer (1)

    - The physical layer is how we physically connect devices 
    
      - volatage on a cable, radio frequency in the air, etc.      
    
      - primarily defines how a single device interacts with a medium
      

    - Major functions and services
        
        - establishment and termination of a connection to a medium
        
        - Resource sharing (such as contention resolution and flow control)
        
        - Modulation (converting digital data into a physical signal)
        
#### Physial Layer (2)

  - Ethernet cards and network hubs operate at the Physical Layer, physically connecting network cables together
    
  - Wifi also operates at the physical layer, since signals are being transmitted in the phyiscal world
    
  - Devices are reffered to by the highest layer they can understand
      
    - Even though a router has physical connections, it is considered a Layer 3 devices because it implements Layers 1, 2, and 3
      
##### Physical Layer Devices


  - **Network Hub**  
    - connects multiple networked devices together, sending data received on one port to all other ports
  
  - **Network Adapter** 
    - connects a device such as a computer to a network    
  
  - **Modem** 
    - MOdulates and DEModulates signals to be transmitted through different mediums, such as a telephone or cable line

**Network Topology**

##### Star Topology

  - Each node is connected to a central node (such as a hub or switch)
  
  - Star topologies provide better performance, isolation of devices, and easy expansion
    - however, they have a single point of failure (if the central node loses connection, all other devices that it supplies will also be without a connection)
  
##### Ring Topology

  - Each node is connected to two other nodes
  
  - Data travels in one direction, passing through each node to reach its destination 
  
  - No central node  
  
  - If one node breaks, it can disrupt the entire network  
  
##### Bus Topology

  - Each node is connected to a single cable, which all nodes share
  
  - The signal travels in both directions to all nodes  
  
  - Only one node can transmit at a time  
  
  - Since all nodes share the same bandwidth, performance degrades as more nodes are added 
  
  - The bus is a single point of failure  

###### Review 2

  1. Which of the following devices operates at ONLY the physical layer?
    a. Router 
    b. Network Firewall
    c. Network Hub X
    d. Network Switch

  2. Which of the following describes a star toplogy network? 
    a. All devices are connected to a central device, such as a network switch **X**
    b. Each device is directly connected to every other device
    c. All devices are connected to a single cable
    d. Each device is directly connected to two other devices, such that data can flow through a series of devices to get between two points
    
