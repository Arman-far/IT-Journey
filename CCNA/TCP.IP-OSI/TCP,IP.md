# TCP/IP (Transmission Control Protocol / Internet Protocol) is a standard set of communication rules that allows devices to communicate over a network .
---
## What is it ?
- A protocol suite used for communication on the internet and most modern networks.
## What does it do ?
- It  breaks data into packets, sends them to the correct destination, and ressembles them when they arrive.
## Why dows it exist ?
- To provide a common standard so different devices andd operating systems can communicate reliably with each other.
---
## TCP/IP-Layers :

### Application :
- Provide network services to applications and uses protocols like HTTP, HTTPS, DNS, FTP,... to communicate over the internet . ( makes data header )
### Transport :
- Provide communicate between application on different devices. It manages data delivery using protocols like TCP and UDP. (makes TCP or UDP header )
### Network :
- Responsible for moving data between different networks . It uses IP-Addresses to identify the source and destination devices and chooses the best path for it . ( make IP header )
### Data-Link :
- Responsible for delivering data between devices on the same local network(MAC).It uses MAC Adress to identify devices and create frames fo transmision.( makes header and trailer )
### Physical :
- Responsible for transmitting raw Bits(0and1) through the physical medium,such as cables or wireless signals.( transmit Data to 0 and 1 and sends )
---
## Example for how TCP/IP works and show what it addes :
- searched : https://example.com/index.html
## Application_Layer:
- Get/index.html              
- Host : example.com
- User Agent:Google.com
- Accept : text.html
- Accept_lanquage: en-US
- Connection : KeepAlive
## Transport_Layer :
- Source port : 52814                              (our computer sets this)
- Destination port : 443                           (https port)
- Sequence number : 148513500                      (max number of existed packets)  
- akhnowledment number : 147113901                 (number of arrived packets )     
- Flag : SYN (Synchronize-syn.ack)                 (TCP control flag used to start a new TCP connection)
- Window size : text.html                          (A value that tells the sender how much data the receiver can accept at one time.)
- Checksum : Detect and resend undeliverd packets  (TCP)
## Network_Layer : 
- Version : IPv4 or IPv6
- Header Lenght : (The header size)
- Total lenght : (Total packets size)
- TTL : 64       (each router subtrack 1 unit from it . if reaches to 0, packet will drop (to Prevents from Loop in network ))
- Header checksum : ( reciew the IP )
- Source IP :192.168.1.1
- Destination IP : 192.168.1.2
## DataLink_Layer : 
- Source MAC : ...                                    (My comp MAC address)(changes then arrives to a IS)
- Destination MAC : ...                               (The touter that my computer nows it )(changes then arrives to a IS)
- Ether type :0x0800=IPv4,0x86DD=IPv6,0x0806=ARP      (A field in the Ethernet header that indicates the encapsulated protocol)
- IP packet : ...                                     (An IP packet is the payload of an Ethernet frame)(So the data can be delivered between devices on the same local network (LAN) using MAC addresses)
- FCS : ...                                           (Checkes the packet before sends it , if is there a problem => Drop and replace it )
## Physical_Layer :
- Bits :...                                           (change whole packet to Bits,Fiber pulses or radio frequencys)
---
## Encapsulation , Decapsulation : 
- each layer add a header from 1 to 4 (5 is physical) then datalink layer encapsulating it and sends .
- | Frame | Ip | TCP or UDP | Data | Frame |
     4      3        2         1       4         
---
## Words need to know : 
- TCP = in Transport layer = Segment 
- UDP = in Transport layer = Datagram
- IP = in Network Layer = Packet 
- LH = in Datalink Layer = Frame