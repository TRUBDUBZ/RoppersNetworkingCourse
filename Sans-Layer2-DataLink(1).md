# Layer 2 - Data Link

The data link layer transfers data between adjacent network nodes

- Detect errors in the Physical Layer

- Only traverses a single network (i.e., not routed)

- A MAC address is a unique 6 byte identifier that is hard-coded in most networking cards
  
  - represented as six hex octets: 00:11:22:33:44:55
  - first 3 bytes are the OUI, which identifies the manufacturer 
  - can be spoofed

- Data travels in "frames" across a network segment 
  
  - each frame has a source and destination MAC address  

- Common devices include network switches, network bridges, and wireless access points

## Network Switch

- Switches keep track of which devices are connected to which ports
  
  - they watch traffic for MAC addresses and keep track 
  
- Switches use this information to decide which port to send packets to 

- A hub would forward to all ports, operating at layer 1

  - no intelligence  
  - simply repeats communication
  

## ARP 

- Computers need a way to map IP addresses (Layer 3) to MAC addresses (Layer 2) in order to communicate on the same physical network 

- Devices on the same same network use ARP (Address Resolution Protocol) to determine the MAC address associated with a given IP

- One system broadcasts an ARP request to all other systems asking who has a given IP address

- They system with that IP address answers with its MAC address

- Both systems store each others MAC addresses in their local ARP cache so they dont have to ask again for a while

### Other Uses of ARP 

- ARP Probe
  
  - An ARP message sent by a computer when it obtains a new IP address, to ensure it isnt already in use 
  
- Gratuitous ARP 

  - An ARP reply that is sent without a corresponding request 
  - Many OS's send an ARP announcement when they boot or change IP addresses 
  - Most systems will accept a gratuitous ARP reply and update their ARP cache 
  - Can also be used maliciously  
  
- ARP Spoofing
  - Can be used to pretend to be another system on the network 

### Review

  - True/False: Your MAC address will be recorded in the logs of an internet web server you access  - False - ARP traffic is not routed beyond the local network 
    
  - True/False: The first three octets of a MAC address identify the manufacture - True
  
  - True/False: A MAC address is hard-coded and cannot be spoofed - False


#### Exercise

  run `ping www.google.com`
  
  - it will run forever so use control + C to exit
  
  then run arp -a 


