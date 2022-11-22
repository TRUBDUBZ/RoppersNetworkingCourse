# Where do we Capture Network Traffic?

- see packets from client side / tap or span into server side 
    
    - maybe even have another capture point somewhere half way inbetween server and client

- capture with **SPAN** / monitor ports
 
    - tells switch to send data from 1 interface to another

- no access to taps or ports

    - install wireshark on client side to start to get a picture of what traffic is coming in / out

    - things can get wonky with timing
    
    - good way to BEGIN a traffic analysis

- on server side: ultimately trying to get a simultanious scan from both client and server

    - where is this server? virutla tap? virutal SPAN? avoid installing wireshark to the server / might overload 


