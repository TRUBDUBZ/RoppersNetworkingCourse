# The OSI Model and Encapsulation

## The OSI Model

  - The OSI Model (aka the Open Systems Interconnection model but you'll never see that) is a useful mental model of how internet communications system work and interact with each other.

  - Basically, the idea is that each level  of the model is a different part of what is necessary for data to be transferred from one place to another. We will learn all about it as we go, so don't worry about memorizing anything... yet. 

  - The competitor to OSI is the TCP/IP model, which is basically the same thing, but with less layers. It all shows the same thing, just with different levels of specificity. 

  - The 7 layers :

- Application: The application layer is the layer that the users and user-applications most often interact with. Network communication is discussed in terms of availability of resources, partners to communicate with, and data synchronization.

- Presentation: The presentation layer is responsible for mapping resources and creating context. It is used to translate lower level networking data into data that applications expect to see.

- Session: The session layer is a connection handler. It creates, maintains, and destroys connections between nodes in a persistent way.

- Transport: The transport layer is responsible for handing the layers above it a reliable connection. In this context, reliable refers to the ability to verify that a piece of data was received intact at the other end of the connection.

  This layer can resend information that has been dropped or corrupted and can acknowledge the receipt of data to remote computers.

- Network: The network layer is used to route data between different nodes on the network. It uses addresses to be able to tell which computer to send information to. This layer can also break apart larger messages into smaller chunks to be reassembled on the opposite end.

- Data Link: This layer is implemented as a method of establishing and maintaining reliable links between different nodes or devices on a network using existing physical connections.

- Physical: The physical layer is responsible for handling the actual physical devices that are used to make a connection. This layer involves the bare software that manages physical connections as well as the hardware itself (like Ethernet).

## Encapsulation

- One useful thing we can use those models for is to visualize how encapsulation works. Encapsulation is the process of wrapping a piece of data in the routing information required to pass to the next level of the networking stack. Once it gets to the bottom of the stack at the physical layer and is actually sent across the network, once it is received "de-encapsulation" occurs, and each level of encapsulation is removed. Eventually, the data, as sent from the first computer finally reaches its destination. 

- What does that mean? How does it work? Don't worry for now, you'll be great at it soon enough.

-   
