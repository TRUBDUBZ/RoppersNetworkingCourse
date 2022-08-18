# Basics Of Networking 

## IP Addresses and Basic Networking 

- Just think of it as the way other computers know who you are, and based off of a complicated routing system, how computers in between you and whatever you are talking to knows how to transport things back and forth.

- To find out your IP address, run the command `ip addr`. For now, focus on the IP addresses, the items in the form 127.0.0.1, 192.168.20.45, 182.16.10.100, 10.2.5.24 etc...

- Addresses in that form are known as **IPv4** addresses. Note that there is also **IPv6** but not important for basics.

- You should only have a few of them, so look for your 127.0.01 address. This is called your localhost, aka, your computer's local IP address. It is completely internal, and all computers have a localhost at 127.0.0.1. This means that you can't talk to someone else's localhost address and it is non-routable.

- You should have at least one more IP address listed, likely in the format 10.x.x.x, 192.168.x.x, or 172.x.x.x. These address ranges are known as "local" addresses. Long story short, there aren't enough IPV4 addresses. If you want to read more about this, the [wikipedia article](https://en.wikipedia.org/wiki/IPv4_address_exhaustion) is decent.

- To get around the lack of IPV4 addresses, most private networks use these local addresses for all the computers on it, so that they don't need to own all the IP address space required for all of their computers (what? people own IP addresses? Yeah it's super complicated, we're gonna ignore that for now. There's also something called IPv6 which looks like this 2001:db8::8a2e:370:7334 but we are going to ignore all of those addresses for now)

- So when you see those local IPV4 addresses, what you are seeing is the IPV4 address your network has assigned to you to use locally (and only locally).

- 
