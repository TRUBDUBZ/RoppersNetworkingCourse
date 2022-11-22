# Basic Linux Commands: Capturing Packets Without WireShark 

- You won't always have Wireshark or tshark around, but you will always have a need to capture packets. That's where tcpdump comes in. It comes pre-installed on many Linux distros and has all of the same functionality and most of the same command line args for filtering. To get started, check out your list of available interfaces with:

`$ tcpdump -D`

- This will return a list of names that probably don't mean anything to you..

- So what are those interfaces anyway? Basically, they're meant to be human readable names for the various networking devices on the system. eth0, while a classic, has been sadly retired in favor of the wlp/enp family of names.

- There's some complexity here about that scattered series of letters and numbers being a predictable name that means something but whatever, just know whatever looks like that is going to be your public-facing interface.

- **Loopback** or **lo** will be your local interface for packets that never leave your machine, and all the other interfaces are usually not something you'll deal with unless you're doing some fairly specialized work. The exception is "any" which, you guessed it, can listen on all interfaces at once.

- To capture packets using tcpdump, run the command `$ tcpdump -i <interface>`

- Use `$  tcpdump -i <interface>  -w <fileName>` to write to a file.
    
    - Then you can later load that into Wireshark and analyze it.

## Figure Out Your IP Address

- Speaking of things that have been retired, the Linux world ran on the command 'ipconfig' for many years, but it has recently been deprecated in favor of the command 'ip'. I don't care enough about internet drama to tell you more, but it was a big deal to people who don't leave their house enough. 

- Anyway, IP has a lot of use cases and functionality, but the core use of IP is to get the list of addresses for each interface

`$ ip addr`

```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default 
link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
inet 127.0.0.1/8 scope host lo
valid_lft forever preferred_lft forever
inet6 ::1/128 scope host
valid_lft forever preferred_lft forever
2: eno1: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state 
link/ether f0:1f:af:05:0b:7d brd ff:ff:ff:ff:ff:ff
3: wlp3s0b1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP 
link/ether 08:3e:8e:3e:7a:0a brd ff:ff:ff:ff:ff:ff
inet 192.168.0.16/24 brd 192.168.0.255 scope global dynamic
valid_lft 2441sec preferred_lft 2441sec
inet6 2601:14d:8400:2570:6530:9fbe:ccf:4924/64 scope global temporary dynamic
valid_lft 7196sec preferred_lft 7196sec
inet6 2601:14d:8400:2570:8237:c825:38cf:d790/64 scope global 
valid_lft 7196sec preferred_lft 7196sec
inet6 fe80::e1fe:2a68:230d:e781/64 scope link noprefixroute
valid_lft forever preferred_lft forever
```

- Here we can see that for lo, loopback, our ip address is 127.0.0.1.... which is also yours, and every other computer on the planet's basically. Because these packets never leave our device, it's fine for everyone to have the same loopback address. 

- eno1 is my local wired ethernet adapter because I am using a real Linux desktop instead of a VM. If you are in a VM, you probably have something that looks like enp65s0, which will be the assigned name of the virtual adapter your VM gave you.

- The most exciting interface I have right now is wlp3s0b, which if you haven't guessed yet, is a wireless interface. (wl = wireless, en= ethernet). That has an (inet) ipv4 address = 192.168.0.16, an ethernet/link address = 08:3e:8e:3e:7a:0a, and a bunch of ipv6 addresses. There's also some broadcast stuff in there, but you can kind of ignore it for now.

- Another interesting command is $ ip neigh which returns your ARP cache. 

```
192.168.0.10 dev wlp3s0b1 lladdr f0:ef:86:05:7d:41 REACHABLE
192.168.0.1 dev wlp3s0b1 lladdr 78:d2:94:8f:1a:d3 REACHABLE
192.168.0.18 dev wlp3s0b1 lladdr f0:f0:a4:8d:fb:da STALE
fe80::7ad2:94ff:fe8f:1ad3 dev wlp3s0b1 lladdr 78:d2:94:8f:1a:d3 router STALE
```

- The last thing we will do here is $ ip route which prints your routing tables. There is a ton of information about what this command does, and all of the ip commands I just demonstrated in the man pages... once again proving there is no need to memorize this stuff.

- You can also use the ip command to change values, whether that is your ip, configure interfaces, or change routes. Don't worry about memorizing things, just google them or check a cheat sheet when they come up. For now, let's quickly change your MAC address!

- Figure out your external NIC's name with ip addr. Then throughout this,  change the $NIC out with the name of your NIC.

```
## Disable the NIC so you can modify it
$ ip link set dev $NIC down
## set new MAC address ##
$ ip link set dev $NIC address DE:AD:BE:EF:BA:BE
## Re-enable the NIC
$ ip link set dev $NIC up

```
- Then run ip addr again. You should see the change reflected. For bonus points, look in Wireshark while this is happening for the ARP request that contains the change!

### See what is running on ports (Without WireShark)

- Sometimes you don't need wireshark and are just looking for what processes are making connections on your box. This is a great time for some CLI tools.

- Before we run them, run the command $ nc -lp 1337. After you run the command, go look for the nc process... You should be able to find it! 

```
$ netstat --inet -ap
$ lsof -i
```

- For a pro-tip, anytime you want to look like a hcker, run these commands and you'll have a very cool looking display up.


