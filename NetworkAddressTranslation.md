# Network Address Translation NAT

`$traceroute google.com`

What is NAT or Network Address Translation? 
  
  - NAT is a method of mapping one IP address to another by modifying packets while they are in transit. 
  
  - It's hella complicated how it works, but what matters to us, the end users, is that our local address is stored by some NAT server which ensures that any responses to traffic from us that leaves our network, comes back to our locally assigned IP. 
  
  - On the other hand, nobody should be able to connect into a box behind NAT because they will not know the local IP address and either way, a local address shouldn't be routed across the internet. So just remember for now, NAT allows connections out and responses back, but does not allow connections in. 
  
## VM Networking

  - So how does this all tie back into practical application? Well your Virtualization Software will have an option to switch your VM between a NAT'd IP address and a Bridged IP address.
    
  - Bridged IP addresses are IP addresses assigned by your local router, which will be NAT'd by the router when you try to connect out. 
    
  - NAT'd IP addresses are IP addresses assigned by your virtualization software, which puts that box behind a NAT.
    
  - This means that if you are NAT'd, another local computer will not be able to connect to you, but if you are Bridged, your IP address will be routable. You're still both behind a router NAT, but it's the same NAT so you'll share the same IP address prefix.
  
  - Depending on your Virtualization Software, switch between the different networking modes and see how your IP address (and routing) changes. Run the $ ip addr command to check.
   
  - If you are having troubels switching, assume that is is because  Windows Hyper-V is doing bad things (even if you aren't using it). It's possible to fix Hyper-V issues by "disable network interfaces hyper-v" (there's your search term), but it's mostly a pain that pops up every once in a while.
  
    - VMWare
    - Virutal Box    
    - UTM 
    - Hyper V - Dont try to do the hyperv one its a nightmare juse use VMWare
      

  
