# OSI Model

## Overview

### What is the OSI Model?

- Open Systems Interconnection (OSI) model is a standard (ISO 7498) for connecting systems in a network

- There are 7 layers in the OSI model and we can use the OSI model as a reference model while troubleshooting to categorize our problems into different layers to help develop a solution

- The 7 layers of the OSI model are listed below from top to bottom (highest to lowest layer):
    
    - Application (Layer 7)
    - Presentation (Layer 6)
    - Session (Layer 5)
    - Transport (Layer 4)
    - Network (Layer 3)
    - Datalink (Layer 2)
    - Physical (Layer 1)

- The OSI model doesn't cleanly map to the way our modern networks operate nowadays because our networks typically follow the TCP/IP model and protocols, while the OSI model attempts to describe how ALL networks operate

    - Some parts of our TCP/IP model map to and/or operate at multiple levels of the OSI model

- When we communicate data across a network, we can give it more descriptive names as it flows through the various layers of the OSI model

- The different, more specific names for data as it flows top-to-bottom (highest to lowest layer) through the OSI model are as follows:
    
    - Data (Application)
    - Data (Presentation)
    - Data (Session)
    - Segments (Transport)
    - Packets (Network)
    - Frames (Datalink)
    - Bits (Physical)


## Physical Layer (OSI Model Layer 1)

### What is the Physical Layer?

- The physical layer of the OSI model is the layer where transmission of bits (logical zeroes and ones) across the network occurs and it includes the physical and electrical network characteristics

    - These physical and electrical network characteristics are things such as copper cabling, fiber optic cabling, and the various electrical voltages (in the case of copper cabling) or photons (in the case of fiber optic cabling) that travel across them and represent bits (logical zeroes and ones)

    - If wifi (wireless networking) is used, then radio frequencies act as the physical layer instead of copper or fiber optic cabling

- Transition modulation is the changing of either voltages (in the case of copper cabling), photons (in the case of fiber optic cabling), or radio frequencies (in the case of wifi wireless networking) that represent bits (logical zeroes and ones)

- If we're using copper wire in the form of CAT5 or CAT6 cables, there are two standards in which the physical network is wired

    - TIA/EIA-568A
    - TIA/EIA-568B

- Some times we use crossover cables with different connectors on each end that flip between the two standards

- Othertimes we use straight-through and/or patch cables that use the TIA/EIA-568B standard on both sides

- Layer 1 devices view networks from a physical topology perspective

    - Bus
    - Ring
    - Star
    - Spoke-and-hub
    - Mesh
    - Hybrid (usually combo of mesh and spoke-and-hub)

### How is Communication synchronized on the Physical Layer?

- Communication can be either synchronous or asynchronous

- Asynchronous communication uses start and stop bits to indicate when the transmissions occur from the sender to the receiver

    - An example of asynchronous communication is sending a text message or leaving a voice message for your friend to listen to later

- Synchronous communication uses a reference clock (common time source) to coordinate the transmissions by both sender and receiver

    - An example of synchronous communication is a phone call with your friend, where both parties are required to be active on their devices at the same time

### How is Bandwidth utilized on the Physical Layer?

- The two main ways of utilizing bandwidth on the physical layer are broadband and baseband

- Broadband divides bandwidth into separate channels

    - An example of broadband is cable television, which is a single cable that often carries two hundred or more different channels that the user filters through to choose a single channel to watch

- Baseband uses all available frequencies on a medium (often a cable, but not always) to transmit data

    - An example of baseband is a landline phone, which uses all of the bandwidth allocated to that phoneline to make a phone call and there is no extra bandwidth available for additional calls on that same line

    - Baseband uses a reference clock to coordinate the transmisison of data from both sender and receiver at a certain time, so this is an example of synchronous communication

    - Another example of baseband is a wired home ethernet network, which uses all available bandwidth on the cable to maximize transmission speed compared to a broadband network

- Efficient usage of baseband requires several different strategies

    - Time-Division Multiplexing (TDM) has each session take a turn, using timeslots, to share the medium between all users, although this often leads to wasted timeslots

    - Statistical Time-Division Multiplexing (StatTDM) dynamically allocates timeslots on an as-needed basis, reducing the amount of wasted timeslots

    - Frequency-Division Multiplexing (FDM) divides the medium into channels based on frequencies and each session is transmitted over a different channel, and thus transforms baseband into broadband, with each channel having a fraction of the total bandwidth of the medium

### Examples of Physical Layer Devices

- Different types of media devices make up the Physical Layer

- Cables

    - Fiber Optic
    - Ethernet
    - Coaxial

- Radio Frequencies

    - Bluetooth
    - Wi-Fi
    - NFC

- Infrastructure Devices (that operate at the bit layer, without logic, and simply repeat their inputs as outputs)

    - Hubs
    - Access Points
    - Media Converters

## Datalink Layer (OSI Model Layer 2)

### What is the Datalink Layer?

- The Datalink Layer packages data (bits from the physical layer) into frames and transmits those frames on the network.

    - Additionally, the Datalink Layer also performs some error detection and correction, identifies unique network devices using MAC addresses, and provides some flow control

### What is a MAC Address?

- MAC address is short for Media Access Control address

    - Media Access Control addressing is a system of physical addressing of devices which allows them to operate on a logical topology

    - MAC addresses are unique 48-bit addresses that are assigned to Network Interface Cards (NIC) when produced by manufacturers

    - MAC addresses are always represented by 12 hexidecimal numbers (48 bits), with the first 6 numbers (24 bits) representing the manufacturer of the device and the last 6 numbers (24 bits) representing the unique number of the device

    - For example, in a MAC address of D2:51:F1:3A:34:65, the D2:51:F1 portion of the MAC address represents the vender code (the manufacturer of the device) and 3A:34:65 represents the unique number of the device produced by that manufacturer

### What is Logical Link Control?

- Logical Link Control (LLC) provides connection services and allows acknowledgement of reciept of messages

    - It is the most basic form of flow control by limiting the amount of data a sender can send at once to prevent the receiver from being overwhelmed

    - It allows a device to make a request for either less information at a time or for a replay of that information

    - It provides basic error control functions by allowing the receiver to inform the sender that a dataframe wasn't received or if it was received corrupted, which it can verify through the use of a checksum (adding up all the bits and then verifying the parity of the result)

### How is Communication synchronized on the Datalink Layer?

- Communication can be synchronized across the Datalink Layer using three different schemes

    - Isochronous mode, where network devices use a common reference clock source and create time slots for transmission

    - Synchronous mode, where network devices agree on clocking method to indicate beginning and end of frames and can use control characters

    - Asynchronous mode, where network devices reference their own internal clocks and use start and stop bits


### Examples of Datalink Layer Devices

- Different types of media devices make up the Datalink Layer

    - Network Interface Cards (using MAC addresses)
    - Bridges
    - Switches


## Network Layer (OSI Model Layer 3)

### What is the Network Layer?

- The Network Layer forwards traffic (also known as routing) with logical addresses

- Two examples of logical addressing are IPV4 and IPV6, although there are many more types of logical addressing

- A common point of confusion when it comes to the Network Layer (Layer 3) is that this layer handles *switching*, which is another term for routing, while the Datalink Layer (Layer 2) uses physical *switches*, which are the physical devices used to move frames (packages of bits (logical zeroes and ones)) across a network

- In general, the Network Layer manages the following

    - Logical Addressing
    - Switching
    - Route Discovery and Selection
    - Connection Services
    - Bandwidth Usage
    - Multiplexing Strategies

### What is Logical Addressing?

- Devices needed a system of logical addressing to identify eachother on networks

- Historical examples of logical addressing on the Network Layer include AppleTalk (for Apple devices) and IPX (Internetwork Packet Exchange) (for Windows or Novell Network devices), both of which were popular in the 1980s/1990s

- IPV4 and IPV6 became the common standard that replaced other Network Layer logical addressing systems, while some of the older systems of logical addressing may still exist in legacy devices and networks within corporations and governments

- IPV4 addresses are commonly represented in dotted octet notation, e.g. 172.16.254.1

### What is Switching?

- Switching is the process of routing data on the Network Layer

- The three main ways to route data on the Network Layer are the following

    - Packet Switching
    - Circuit Switching
    - Message Switching

- Packet Switching involves dividing data into packets and then forwarding them on to the intended receiving device

    - Each packet may take a different path across the network as long as it reaches the recipient

- Circuit Switching involves creating a dedicated communication link between two devices

    - Data takes the same path each time during an established connection

- Message Switching involves dividing data into messages which can be stored and forwarded

    - Unlike packet switching, where data is destroyed if it cannot reach the intended recipient, message switching will store the data so that delivery can be attempted later

- Almost all networks nowadays use Packet Switching, because we have other methods (outside of Message Switching) that allow us to check if data is reaching the recipient correctly and resend if necessary along the same path or a different path of the network

    - Only big, backend networks typically use ciruit switching and message switching in addition to packet switching

    - Our home networks, small office networks, and most of the internet use packet switching

### What is Route Discovery?

- Routers maintain a routing table to understand how to forward how to forward a packet based on the destination IP address

    - These routes can be manually configured as a static route

    - Alternatively, the routes can be dynamically discovered and assigned using a routing protocol like RIP, OSPF, EIGRP, or many others

### What Connection Services are provided by the Network Layer?

- Connection Services in the Network Layer build on top of the connection services provided in the Datalink Layer (flow control, error correction, etc.) and add the following functionality:

    - Flow Control (in addition to Datalink Layer flow control), which prevents the sender from sending data faster than the receiver can receive it

    - Packet Reordering, which allows data to be divided into small packets that each might take a different path on the network and arrive out of order at different times, but then be reassembled in the correct order at the final destination

### What is the Internet Control Message Protocol (ICMP)?

- Internet Control Message Protocol (ICMP) is used to send messages and operational information to an IP destination for troubleshooting

    - The most common ICMP diagnositic tool is **ping**, but **traceroute** is also used

### Examples of Network Layer Devices and Protocols

- Different types of devices make up the Network Layer

    - Routers
    - Multilayer Switches

- Multilayer Switches work like a Datalink Layer (Layer 2) switch and a Network Layer (Layer 3) router combined into one device

- Different types of protocls make up the Network Layer

    - Internet Control Message Protocl (ICMP)
    - Internet Protocol Version 4 (IPV4)
    - Internet Protocol Version 6 (IPV6)

## Transport Layer (OSI Model Layer 4)

### What is the Transport Layer?

- The Transport Layer is responsible for sending **Segments** and **Datagrams** across a network

- The Transport Layer also introduces reliability features such as **windowing** and **buffering**

- Two examples of common protocols making up the Transport Layer are **Transmission Control Protocol (TCP)** and **User Datagram Protocol (UDP)**

### What is Transmission Control Protocol (TCP)?

- Transmission Control Protocol (TCP) is a reliable way to transport segements across a network because it asks for an acknowledgement for each segment and will resend segments if it does not receive an acknowledgement for a given segement

- Transmission Control Protocol is a **connection-oriented** protocol because it requires verification that segments were received

- Transmission Control Protocol (TCP) works with a three-way handshake

    - The client sends a **SYN (synchronization)** packet to the server

    - The server sends a **SYN-ACK (sychronization acknowledgement)** packet back to the client

    - The client sends an **ACK (acknowledgement)** packet back to the server in addition to any data that it was going to send in the form of segements (collections of packets)

### What is User Datagram Protocol (UDP)?

- User Datagram Protocol (UDP) is an unreliable (and faster) way to transport segements across a network

- User Datagram Protocol (UDP) is a **connectionless** protocol because it doesn't have to wait for connections or the verification of received datagrams (no three way handshake, unlike TCP)

- When using User Datagram Protocol (UDP) in the Transport Layer (Layer 4), we use the term **datagram** instead of segment (while continuing to use the term segment for any data related to TCP and other Layer 4 protocols)

- User Datagram Protocol is commonly used for audio and video streaming because it uses less bandwidth and some data loss is tolerable and likely not noticable when streaming audio and video

### Summarizing the Differences Between TCP and UDP

- Transmission Control Protocl (TCP)

    - Reliable
    - Connection-oriented
    - Segment retransmission and flow control through windowing
    - Segment sequencing
    - Acknowledges segments

- User Datagram Protocl (UDP)

    - Unreliable
    - Connectionless
    - No windowing or retransmission
    - No sequencing
    - No acknowledgement

### What is Windowing?

- Windowing allows the client to adjust the amount of data in each segment as it goes through the transmission

    - If the number of retransmissions small or zero, client will send more data in each segment (increasing the size of the window)

    - If the number of retransmissions is large, client will send less data in each segement (decreasing the size of the window)

### What is Buffering?

- Buffering occurs when devices allocate memory to store segments if bandwidth isn't readily available

    - Routers have memory that allows them to store segements if bandwidth isn't readily available for transmission, which is then emptied and transmitted when the bandwidth eventually becomes available again

    - When buffers fill up and a router runs out of memory, segements will be dropped

### Examples of Transport Layer Devices and Protocols

- Different types of devices make up the Transport Layer

    - WAN accelerators
    - Load balancers
    - Firewalls

- Different types of protocols make up the Transport Layer

    - TCP
    - UDP


## Session Layer (OSI Model Layer 5)

### What is the Session Layer?

- The Session Layer keeps connections and data flows separate to prevent the intermingling of data from different sources

- The Session Layer sets up sessions, maintains sessions, and tears down sessions

    - Setting up a session involves checking user credentials and assigning numbers to sessions to help identify them

    - Maintaining a session involves transferring data across the network, back and forth, over and over again, and also involves re-establishing dropped connections and acknowledging receipts

    - Tearing down a session involves ending a session after the transfer of data is complete (through mutual agreement) or when the other party disconnects

### Examples of Session Layer Devices, Protocols, and Standards

- The Session Layer does not necessarily have devices, because operations at this layer occur logically/digitally through protocols and standards rather than physical devices

- Different types of protocols and standards make up the Session Layer

  - Real-time Transport Protocol (RTP)

      - H.323 is a standard used to set up, maintain, and tear down voice and video connections (typically VoIP telephony and video conferencing), and it can be used at the Session Layer and operate over Real-time Transport Protocol (RTP)

      - H.264 (also referred to as Advanced Video Coding (AVC)) is a standard used for video compression, and similarly to H.323 can be used at the Session Layer and operate over Real-time Transport Protocol (RTP)

  - NetBIOS Protocol

      - Previously NetBIOS Frames (NBF) Protocol over IPX (pre-IP era)

      - Currently NetBIOS over TCP/IP (NBT) Protocol

      - Both versions of the protocol allow for communication of data for files and printers at the Session Layer (Layer 5) and it is an API only, not a networking protocol


## Presentation Layer (OSI Model Layer 6)

### What is the Presentation Layer?

- The Presentation Layer formats data that will be exchanged and secures data with proper encryption

### Data Formatting

- Data Formatting is done so that data will be compatable across different devices

- Some common data formats are as follows:

    - American Standard for Computer Information Interchange (ASCII)
    - Graphics Interchange Format (GIF)
    - Joint Photographic Experts Group (JPEG)
    - Portable Network Graphics (PNG)

- Data formatting that occurs on the Presentation Layer (Layer 6) allows us to negotiate data transfer syntax for the Application Layer (Layer 7)

### Encryption

- Encryption is used to keep data secure in transit and provide data confidentiality as it crosses the network and as it is stored

    - Transport Layer Security (TLS) is an example of encryption being used to secure data before transit

### Examples of Presentation Layer Devices, Formats, Protocols, and Standards

- The Presentation Layer does not necessarily have devices, because operations at this layer occur logically/digitally through formats, protocols, and standards rather than physical devices

- Scripting languages, Markup languages, and Stylesheet languages operate at the Presentation Layer, because they format data before it is displayed or transported across a network

    - HTML (Markup Language)
    - CSS (Stylesheet Language)
    - JavaScript (Scripting Language)
    - PHP (Scripting Language)

- Text formats operate at the Presentation Layer

    - ASCII
    - Unicode
    - EBCDIC

- Image formats operate at the Presentation Layer

    - GIF
    - JPG (JPEG)
    - TIF
    - SVG
    - PNG

- Video formats

    - MP4
    - MPG
    - MOV

- Encryption protocols

    - Transport Layer Security (TLS) protocol
    - Secure Sockets Layer (SSL) (deprecated)

## Application Layer (OSI Model Layer 7)

### What is the Application Layer?

- The Application Layer provides application-level services where users communicate with the computer

### What are Application Services?

- Application Services are protocols and their associate processes that allow user software to send and receive information across a network and sychronizes communication across user software (e.g. SMTP for email, FTP for file transfer, or HTTP for hypertext transfer)

### What is Service Advertisement?

- Service Advertisement is the action of sending out announcements on a network to state the services that a device offers

### Examples of Application Layer Devices, Formats, Protocols, and Standards

- The Application Layer does not necessarily have devices, because operations at this layer occur logically/digitally through formats, protocols, and standards rather than physical devices

- Different types of protocols and standards make up the Session Layer

  - Email Protocols
      - Post Office Protocol 3 (POP3)
      - Internet Message Access Protocol (IMAP)
      - Simple Mail Transfer Protocol (SMTP)

  - Web Browsing Protocols
      - HyperText Transfer Protocol (HTTP)
      - HyperText Transfer Protocol Secure (HTTPS)

  - Domain Name Service (DNS)

  - File Transfer Protocols
      - File Transfer Protocol (FTP)
      - File Transfer Protocol Secure (FTPS)
      - SSH File Transfer Protocol (SFTP)

  - Remote Access Protocols
      - Teletype Network Protocol (Telnet)
      - Secure Shell Protocol (SSH)

  - Network Management Protocols
      - Simple Network Management Protocol (SNMP)


## Encapsulation and Decapsulation

### What is Encapsulation?

- Encapsulation is the process of putting headers and sometimes trailers around your data

### What is Decapsulation?

- Decapsulation is the process of removing headers and sometimes trailers from our data

### Encapsulation vs Decapsulation

- Encapsulation occurs as data moves from the highest layer of the OSI model (Layer 7) (Application Layer) to the lowest layer of the OSI model (Layer 1) (Physical Layer)

- Decapsulation occurs as data moves from the lowest layer of the OSI model (Layer 1) (Physical Layer) to the highest layer of the OSI model (Layer 7) (Application Layer)

### What are Protocol Data Units (PDUs)?

- Protocol Data Units are single units of information transmitted in a computer network

- In the OSI model, Protocol Data Units are referred to by their layer number and then the abbreviation PDU, e.g. L7 PDU

- In the OSI model, there are special names for Protocol Data Units in Layer 1 (Physical Layer), Layer 2 (Datalink Layer), Layer 3 (Network Layer), and Layer 4 (Transport Layer)

    - Bits (Physical Layer)
    - Frames (Datalink Layer)
    - Packets (Network Layer)
    - Segments (TCP) or Datagrams (UDP) (Transport Layer)

- The headers added at layers 4, 3, 2, and 1 help our message reach its final destination

### PDU Headers

#### Transport Layer Headers (Layer 4 Headers)

- One common Transport Layer protocol is Transmission Control Protocol (TCP)

- The TCP header has 10 mandatory fields, totaling 20 bytes of information:

    - Source Port
    - Destination Port
    - Sequence Number
    - Acknowledgement Number
    - Offset
    - Reserved
    - TCP Flags
    - Window
    - Checksum
    - Urgent Pointer
    - mTCP (optional)

- The TCP Control Flags are 6 different flags that are used to manage data flow before and during communication, and also to stop the communication when finished

    - SYN
        - The synchronization flag is used to synchronize connection during the three-way handshake
    - ACK
        - The acknowledgement flag is used during the three-way handshake and also used to acknowledge successful receipt of packets
    - FIN
        - The finished flag is used to tear down virtual connections created with the three-way handshake and SYN flag
    - RST
        - The reset flag is used when a client or server receives a packet that it was not expecting during the current connection
    - PSH
        - The push flag is used to ensure that data is given priority and processed at the sending or receiving ends (and is most often added to a packet at the beginning or end of a data transfer)
    - URG
        - The urgent flag is like the push flag and identifies incoming data as urgent (and it is an indication for the receiver to process the data immediately, unlike the push flag which simply indicates a higher priority)

- Another common Transport Layer protocol is User Datagram Protocol (UDP)

- The UDP header has 3 mandatory fields totaling 8 bytes of information:

    - Source Port
    - Destination Port
    - Length
    - Checksum (optional)

#### Network Layer Headers (Layer 3 Headers)

- One common Network Layer protocol is Internet Protocol (IP) (IPv4 and IPv6)

- The IPv4 header contains 12 mandatory fields, totaling between 20 and 60 bytes of information:

    - Version
        - A 4-bit version field which is always equal to 4 for IPv4
    - Internet Header Length (IHL)
        - Length of the header
        - Minimum value of 5 (5 x 32 bits = 20 bytes)
        - Maximum value of 15 (15 x 32 bits = 60 bytes)
    - Differentiated Services Code Point (DSCP)
        - Originally defined as Type of Service (ToS)
        - This field specifies differentiated services (DiffServ)
        - Real-time data streaming such as Voice over IP (VoIP) makes use of this field
    - Explicit Congestion Notification (ECN) (optional)
        - Allows end-to-end notification of network congestion without dropping packets
        - Only available when both endpoints support it and effective when supported by underlying network
    - Total Length
        - A 16-bit field that defines the entire packet size in bytes, including header and data
        - Minimum size is 20 bytes (header without data)
        - Maximum size is 65,535 bytes
        - All hosts are required to be able to reassemble packets up to 576 bytes, but modern hosts often handle larger packets
    - Identifier
        - Primarily used for uniquely identifying group of fragments of a single IP packets
    - Flags
        - A 3-bit field used to control or identify fragments
    - Fragment Offset
        - Specifies the offset of a particular fragment relative to the beginning of the original unfragmented datagram
    - Time to Live
        - An 8-bit field used to limit a packet's life to prevent network failure in the event of a routing loop
        - Specified in seconds and times less than one second are rounded up to one
        - In practice, the field is used as a hop count - when the packet arrives at a router this field is decremented by one and discards the packet if the field hits zero
    - Protocol
        - Defines the protocol used in the data portion of the packet
    - Header Checksum
        - A 16-bit field used for error checking of the header
        - Errors in the data portion of the packet are handled separately by the encapsulated protocol
        - This field needs to be re-calculated by routers when they decrement the Time to Live field
    - Source IP Address
        - A 32-bit field representing the IPv4 address of the sender
    - Destination IP Address
        - A 32-bit field representing the IPv4 address of the receiver
    - Options and Padding (optional)

#### Datalink Layer Headers (Layer 2 Headers)

- One common Datalink Layer protocol is Ethernet

- The Ethernet header contains 3 mandatory fields, totaling X bytes of information:

    - Destination MAC Address
        - A physical address used to identify the network card on a local area network
    - Source MAC Address
        - A physical address used to identify the network card on a local area network
    - EtherType
        - A field used to indicate which protocol is encapsulated in the frame, frequently IPv4 or IPv6
    - VLAN Tag (Optional)
        - Minimum frame payload (in addition to the header) is 42 bytes if VLANs are being used
        - Minimum frame payload (in addition to the header) is 46 bytes if no VLANs are being used

- By default, Ethernet has a maximum payload of 1500 bytes, referred to as a Maximum Transmission Unit (MTU)
    - This can be increased up to 9000 bytes, known as a Jumbo Frame (any frame between 1500 and 9000), or even larger up to a theoretical maximum of 65,535 bytes, known as a Super Jumbo Frame (any frame over 9000)