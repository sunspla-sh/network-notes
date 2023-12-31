# IP Addressing

## Overview

### What is an IP Address?

- IP Addresses, also known as Internet Protocol Addresses, are assigned numerical labels that are used to identify internet-communicating devices on computer networks

    - IP Addresses are used at the Network Layer (OSI Model Layer 3) and are also used by routers to be able to send data from one network to another network

### Layer 2 vs Layer 3 Addressing

- Layer 2 Addressing is done between two devices that are internal to our own network/LAN using MAC addresses

    - Any data is forwarded around the internal network using switches

- Layer 3 Addressing is done between two different networks or subnets using IP adresses

    - Any data is forwarded between networks using routers

### IP Address Formats

- IP Addresses come in two formats

    - IPV4

    - IPV6

## IPV4 Addressing

### Dotted Decimal Notation

- IPV4 Addresses are typically displayed in **dotted decimal notation**, which is divided into 4 sections with each section representing an *octet* (8 bits) between decimal numbers 0 and 255

    - When these 4 *octets* are combined, we have a total addressable space of 32 bits

- IPV4 Address Example

    - Dotted Decimal Notation

        - 192.168.1.4

    - Binary Notation

        - 11000000 10101000 00000001 00000100

### Subnet Masks

- Subnet Masks are a secondary 32 bit addressable space (in the case of IPV4) that are also divided into 4 *octets* like an IPV4 address

    - Subnet masks divide an existing IPV4 address into network and host portions, with network portions represented by the decimal number 255 (or 11111111 in binary) and the host portions represented by 0 (or 00000000 in binary)

    - An example of a subnet mask for an IPV4 address is 255.255.255.0, which means that the first three octets of any associated IPV4 address refers to the network, and the fourth (last) octet refers to a unique host on the network

        - In this example (255.255.255.0 subnet mask), two IPV4 Addresses on the *same network* would be the following (because their first 3 octets are used to define the network)

            - **192.168.1**.3

            - **192.168.1**.4

        - In this example (255.255.255.0 subnet mask), two IPV4 Addresses on a *different network* would be the following (because their first 3 octets are used to define the network)

            - **192.168.1**.3

            - **192.168.2**.4

### IPV4 Classes

- IPV4 Addresses can be categorized into 5 different classes, listed below in the following format:

        CLASS

            FIRST OCTET VALUE

                DEFAULT SUBNET MASK

                POSSIBLE HOSTS

                CIDR NOTATION

            SPECIAL CASES AND EXTRA INFORMATION

    - Class A

        - 1-127

            - 255.0.0.0

            - 16.7 million (256x256x256)

            - /8

    - Class B

        - 128-191

            - 255.255.0.0

            - 65,536 (256x256)

            - /16

    - Class C

        - 192-223

            - 255.255.255.0

            - 256

            - /24

    - Class D

        - 224-239

            - No default subnet mask

            - No default possible hosts

        - *Class D addresses are Multicast Addresses, which are reserved for multicast or multicast routing*

            - *Multicast Addresses are logical identifiers for a group of hosts in a computer network*

            - *In simple terms, multicast addresses can be duplicative (non-unique) and treated like a "group chat", where more than one machine or service on the network is expected to receive the same message*

    - Class E

        - 240-255

            - No default subnet mask

            - No default possible hosts

        - *Class E addresses are reserved for experimental purposes, to be used for research, development, and study only*

            - *Class E addresses have about 268 million addresses that are reserved for future use*

            - *Most networks consider any Class E address to be invalid as a source or destination address*

#### Classful Masks

- Classful Masks are the default subnet masks for a given class of IP Address

    - Classful Masks are **not** required and different subnet masks can be chosen for a given class of IP Address

#### Classless Inter-Domain Routing (CIDR)

- Classless Inter-Domain Routing allows for borrowing some host bits and re-assigning them to the network portion of an IPV4 Addresses

    - For example, suppose we have a subnet mask of 255.255.255.0, which allows for 256 possible hosts on a given network (e.g. 192.168.1.**1**, 192.168.1.**5**, 192.168.1.**8**, etc)

        - We can use Classless Inter-Domain Routing (CIDR) to divide this space into 4 smaller networks of 64 possible hosts each by using two of the host bits as network bits in our subnet mask, which changes from 255.255.255.0 (11111111 11111111 11111111 00000000) into 255.255.255.192 (11111111 11111111 11111111 11000000)

- Classless Inter-Domain Routing Notation (CIDR Notation) consists of a regular IPV4 address, followed by a slash, and then a decimal number representing how many bits are used by the network portion of the address

    - For example, IPV4 Address of 192.168.1.4 and subnet mask of 255.255.255.0 (11111111 11111111 11111111 00000000) can be shortened into 192.168.1.4/24

    - Additional example, IPV4 Address of 192.168.1.4 and subnet mask of 255.255.255.192 (11111111 11111111 11111111 11000000) can be shorted into 192.168.1.4/26

### Public (Routable) IPs vs Private (Non-routable) IPs

#### Public IPs

- Public (routable) IP Addresses can be accessed over the internet and are assigned to a network by an internet service provider

    - These IPs are publicly routable across the entire internet and are globally managed by the Internet Corporation for Assigned Names and Numbers (ICANN)

#### Internet Corporation for Assigned Names and Numbers (ICANN)

- ICANN globally manages and leases publically routable IP addresses

- ICANN consists of 5 different groups underneath them which are responsible for distributing IP Addresses depending on your location

    - ARIN (North America)

    - LACNIC (Latin America)

    - AFNIC (Africa)

    - APNIC (Asia Pacific)

    - RIPE (Europe)

- ICANN or their 5 subgroups will not directly leasing individual IPs to individuals, only large blocks of IPs (256 addresses or larger, also known as /24 blocks in CIDR notation) to individuals or companies

    - Individuals that want to lease a single IP address must contact a reseller, typically their internet service providers

#### Private IPs

- Private (non-routable) IP addresses can be used by anyone at any time, but only within their own local area network

    - Private IP ranges typically start with 10, 172, or 192

    - Private IPs are converted to Public IPs using Network Address Translation (NAT) when accessing the public internet

#### Network Address Translation (NAT)

- Network Address Translation allows the routing of private IPs through a public IP

#### RFC 1918

- RFC 1918 (short for Request For Comment 1918) is a document outlining how organizations can conduct address allocation for private internets (now known as intranets)

#### Private IP Address Classes

        CLASS

            STARTING VALUE

                IP RANGE

                POSSIBLE HOSTS

- Class A

    - 10

        - 10.0.0.0-10.255.255.255

        - 16.7 million (256x256x256)

- Class B

    - 172.16-172.31

        - 172.16.0.0-172.31.255.255

        - 1.05 million (16x256x256)

- Class C

    - 192.168

        - 192.168.0.0-192.168.255.255

        - 65,536 (256x256)


### Specialized IP Addresses

- There are two types of specialized IP addresses

    - Loopback 

        - 127.0.0.1

        - Creates a loopback to the host and is often used in troubleshooting and testing network protocols on the system

        - Technically it consists of the entire 127.0.0.0-127.255.255.255 range

        - Also referred to as **localhost**

    - APIPA

        - 169.254.0.0-169.254.255.255
    
        - Automatic Private IP Addresses (APIPA) are used (dynamically assigned by the operating system) when a device does not have a static IP address or cannot reach a DHCP server

        - When a device boots up, it attempts to get an IP address through a process known as DORA

            - Discover

            - Offer

            - Request

            - Acknowledge

                - If the DORA process fails, the computer will pick its own IP Address from the APIPA range (169.254.0.0-169.254.255.255)

### Virtual IP Addresses (VIP or VIPA)

- Virtual IP Addresses are IP addresses that do not correlate to an actual physical network interface

- Virtual IP Addresses are typically used for the following cases:

    - Network Address Translation (NAT)

    - Fault-Tolerance

    - Virtualization

- Network Interface Cards can technically only be configured with one IP Address per card, but Virtual IP Addresses can allow multiple IP addresses to be configured for one card

- Routers will often use Virtual IP Addresses to provide redundancy in their connectivity options as well

    - Default Gateways can be assigned a Virtual IP, with multiple routers able to respond on behalf of that Virtual IP so that a secondary router can take over in case the primary router fails

### Subinterfaces

- Subinterfaces are virtual interfaces that are created by dividing up one physical interface into multiple logical interfaces

## IPV4 Data Flows

### Three Types of IPV4 Data Flows

- There are three different ways data can flow using the IPV4 protocol:

    - Unicast

        - Data travels from a single source to a single destination

    - Multicast

        - Data travels from a single source to multiple (but specific) destination devices

    - Broadcast

        - Data travels from a single source to all devices on a network

## Assigning IP Addresses

### Overview

- There are two methods for assigning IP addresses

    - Static

        - Manually typing in the IP address for the host, its subnet mask, default gateway, and DNS server

    - Dynamic

        - Programmatically assigning IP addresses when hosts join a network

- Regardless of the method chosen for assigning an IP address, the following 4 components are required

    - IP Address

    - Subnet Mask

    - Default Gateway

        - Typically this is the IP address of your router

    - Server Address

        - This is for either DNS or WINS

#### Domain Name System (DNS)

- Domain Name System (DNS) is a system that converts domain names used by websites to the IP addresses of their servers

#### Windows Internet Name Service (WINS)

- Windows Internet Name Service (WINS) is a system that identifies NetBIOS systems on a TCP/IP network and converts those NetBIOS names to IP addresses

    - Similar to DNS, but only works on Windows environments and networks

### Dynamic IP Address Assignment Methods

- There are 4 common methods of dynamically assigning IP addresses

    - Bootstrap Protocol (BOOTP)

    - Dynamic Host Configuration Protocol (DHCP)

    - Automatic Private IP Addressing (APIPA)

    - Zero Configuration (ZeroConf)

#### Bootstrap Protocol (BOOTP)

- Bootstrap Protocol (BOOTP) dynamically assigns IP addresses and allows a workstation to load a copy of their boot image over the network

- Originally introduced in 1985 for use in diskless UNIX workstations because it could dynamically assign IP addresses and then allow the workstation to load a copy of a boot image over a network

- Used a static database of IP addresses and MAC addresses, where the connecting client would be issued an IP address by a server based on the result of the server looking up the client's MAC address in the database

- The oldest and least used of the options

#### Dynamic Host Configuration Protocol (DHCP)

- Dynamic Host Configuration Protocol (DHCP) assigns an IP address to clients based on an assignable scope or pool of addresses and provides the ability to configure and assign other options such as the subnet mask, default gateway (IP address), and DNS/WINS server (IP address)

- Each IP is leased by a client for a period of time and returns to the pool when the lease expires

- Originally introduced in 1993 to replace BOOTP

- Commonly used in modern networks

#### Automatic Private IP Addressing (APIPA)

- Automatic Private IP Addressing (APIPA) is used when a device does not have a static IP address, cannot reach a DHCP server, or the DHCP server has run out of assignable addresses

    - Assigned from the 169.254 scope

    - For example, if 10 computers are all connected through a switch with no configuration, APIPA will allow them to each pick their own IP address from the 169.254 range (which by default is a Class B Address), so they will all be automatically able to communicate with eachother

    - APIPA does not assign a default gateway, so a computer that has been automatically configured with APIPA cannot reach external networks (such as the Internet)

#### Zero Configuration (ZeroConf)

- Zero Configuration (ZeroConf) is based on APIPA, but with additional features

    - Assigns IPV4 link-local addresses to clients

    - Resolves computer names to IP addresses without DNS by using mDNS (multicast domain name service)

    - Performs service discovery on a network

        - For example, ZeroConf can find printers, scanners, and shared file systems

- There are often different implementations of ZeroConf with different names depending on the product line. Some will be listed below in the following format:

        PRODUCT LINE

            ZEROCONF IMPLEMENTATION NAME

    - Apple

        - Bonjour

    - Windows

        - Link-Local Multicast Name Resolution (LLMNR)

    - Linux

        - SystemD (System Daemon Service)

            - Specifically, the **systemd-resolved** background service within SystemD

## Computer Mathematics

### Overview

- Computers count in binary, not decimal

- Figure out how to count in binary on your own, I'm not showing you how to do it here

## Subnetting

### Overview

- Subnetting is the process of taking a larger network and splitting it into smaller networks

- The default classful subnet is rarely the optimal subnet size for our network

    - We use subnet masks to modify subnets and create better scoped networks

### Subnet Classes Review

- The three classes of subnets are listed below in the following format


      ADDRESS CLASS

          DEFAULT SUBNET MASK

          ASSIGNABLE IP CALCULATION

          ASSIGNABLE IP ADDRESSES

  - Class A

      - 255.0.0.0

      - 2<sup>24</sup> - 2

      - 16,777,214

  - Class B

      - 255.255.0.0

      - 2<sup>16</sup> - 2

      - 65,534

  - Class C

      - 255.255.255.0

      - 2<sup>8</sup> - 2

      - 254

- When working with IPV4, the number of assignable IP addresses as hosts subtracts two addresses, because the first address in the range is used as the network ID and the final address in the range is used as the broadcast ID (so neither of them can be used as host addresses)

    - This rule does NOT apply to IPV6, which is allowed to assign the full range of addresses in a subnet as host addresses

### Classless Subnet Example

- Assume we have a network 192.168.1.0/26, which has a default subnet mask of 255.255.255.0 represented by /24 in CIDR notation

    - The /26 means that we are borrowing two bits additional from the host portion of the address instead of using the default subnet mask of /24

    - The number of available subnets is 2 raised to the number of borrowed bits, so 2<sup>2</sup> in this case, which is 4 total subnets

    - Each of those subnets has 2<sup>32 - CIDR</sup> IP addresses, so 2<sup>32 - 26</sup> or 2<sup>6</sup> in this case, which is 64 total addresses

        - However, the first address in the range is always the network ID and the last address in the range is the broadcast ID, neither of which are available to be assigned to hosts, so that means we only have 64 - 2 = 62 total assignable IP addresses in the subnet

### Variable-Length Subnet Mask (VLSM)

- Allows subnets of various sizes to be used and requires a routing protocol that supports it such as the following

    - Routing Information Protocol (RIP)

    - Open Shortest Path First (OSPF)

    - Intermediate System - Intermediate System (IS-IS)

    - Enhanced Interior Gateway Routing Protocol (EIGRP)

    - Border Gateway Protocol (BGP)

- In simplified terms, Variable-Length Subnet Masking is a subnetting of subnets

## Subnetting Practice

### Practice #1

- A new office location has been assigned the range of 10.10.10.0/24. Configure subnets for each department in the new office using CIDR notation and provide the minimum number of IP addresses that will meet their needs. The departments are listed below:

    - 54 - IT

    - 32 - Instructors

    - 5 - Sales

    - 3 - Admin

    - X - Unused

- The CIDR notation solutions for the departments are listed below:

    - IT - /26

    - Instructors - /26

    - Sales - /29

    - Admin - /29

    - Unused - /26

### Practice #2

- How many assignable IP addresses exist in the network 172.16.1.0/27?

    - 30 assignable IP addresses exist in the network 172.16.1.0/27 (because we have 32 IP addresses in the range, but need to subtract 2 for the network ID and the broadcast ID)

### Practice #3

- How many assignable IP addresses exist in the network 192.168.1.0/28?

    - 14 assignable IP addresses exist in the network 192.168.1.0/28 (because we have 16 IP addresses in the range, but need to subtract 2 for the network ID and the broadcast ID)

## Subnetting by Hand

### Non-Standard Subnets

- A /31 subnet is a non-standard subnet supported by Cisco routers (and some non-Cisco routers) for point-to-point connections between two routers when network ID and broadcast ID addresses are not required

- A /32 subnet is just a single IP address, and on a class C network there would be 256 subnets in /32 with one IP address each

### Subnetting Examples

- Determine the network ID, first host address, last host address, and broadcast ID from the following network address 171.129.67.160/25

    - /25 means that there are 2 subnets of 128 IP addresses each

    - The first subnet is from 171.129.67.0 to 171.129.67.127

    - The second subnet is from 171.129.67.128 to 171.129.67.255

    - Our network address falls within the second subnet, so the network ID is 171.129.67.128, the first host address is 171.129.67.129, the last host address is 171.129.67.254, and the broadcast ID is 171.129.67.255

- Determine the network ID, first host address, last host address, and broadcast ID from the following network address 56.187.210.21/28

    - /28 means that there are 16 subnets of 16 IP addresses each

    - The first subnet is from 56.187.210.0 to 56.187.210.15

    - The second subnet is from 56.187.210.16 to 56.187.210.31

    - The third subnet is from 56.187.210.32 to 56.187.210.47

    - The fourth subnet is from 56.187.210.48 to 56.187.210.63

    - The remaining subnets can be calculated in a similar manner by counting up in groups of 16 addresses and are left as an exercise to the reader...

    - Our network address falls within the second subnet, so the network ID is 56.187.210.16, the first host address is 56.187.210.17, the last host address is 56.187.210.30, and the broadcast ID is 56.187.210.31

## IPV6 Addressing

### Overview

- IPV4 has 2<sup>32</sup> available addresses, which is approximately 4.2 billion IP addresses

    - These are almost all in use nowadays, causing a problem known as **address exhaustion**

    - In 1995, the Internet Engineering Task Force (IETF) began developing the IPV6 standard when it was clear that IPV4 would eventually run out of addresses

        - The Request For Comment (RFC) document for IPV6 was originally termed IP Next Generation (IPng)

- IPV6 has 2<sup>128</sup> available addresses, which is approximately 340 undecillion IP addresses

    - IPV5 was skipped as an experimental protocol, but some of its concepts were incorporated into IPV6

### Benefits of IPV6

- There are many benefits of using IPV6 rather than IPV4

    - Larger address space

        - This is because of the 128-bit addresses

    - No broadcasts

        - This improves the efficiency of networks

    - No fragmentation

        - This improves security and reduces overhead processing

        - Also removes the MTU discovery process for each session

    - Backwards compatible with IPV4

        - Can coexist with IPV4 on the same network

    - Simplified Header

        - There are only 8 header fields in IPV6

            - This is in contrast to the 12 header fields of IPV4

        - This improves the efficiency of networks

### What is Dual-Stack Equipment?

- Dual-Stack Equipment is equipment (network devices) that runs both IPV4 and IPV6 protocols simultaneously

    - If a network device supports IPV6, a dual-stack router will prefer that protocol for communication, but can also communicate over IPV4 if necessary for devices that do not support IPV6

### What is Tunneling?

- Tunneling allows an existing IPV4 router to carry IPV6 traffic

    - IPV6 packets will be encapsulated within IPV4 headers and then carried by IPV4 routers over IPV4 networks

        - Point-to-point tunnels will be created between the source and destination, which allows isolated IPV6 clients and servers to communicate with eachother without needing to upgrade all of the routers and switch infrastructure that exists between them

### IPV6 Headers

- There are 8 header fields in IPV6 (as opposed to the 12 headers of IPV4):

    - Version

    - Traffic Class

    - Flow Label

    - Payload Length

    - Next Header

    - Hop Limit

    - Source IP Address

    - Destination Address

### IPV6 Address Formatting

- As IPV6 Addresses are 128 bits in length, it is impractical to display them in binary (128 digits) or in dotted decimal notation (16 octets)

- The Internet Engineering Task Force (IETF) determined that the best option for displaying IPV6 Addresses was hexadecimal notation

    - In hexadecimal, each digit represents 4 bits, which allows us to display a 128 bit IPV6 Address in 32 hexadecimal digits

    - IPV6 Addresses combine 4 hexadecimal digits into a group known as a **segment** (which contains 16 bits), and then repeats the process for all 128 bits of the address, giving us 8 segments in total

- IPV6 Address shorthand rules allow a segment with four zeros to be concatenated into a single zero

    - For example, 2018:0000:0000:0000:0000:0000:4815:54ae can be represented as 2018:0:0:0:0:0:4815:54ae

- IPV6 Address shorthand rules allow multiple segments that only contain zeros to be represented by a double colon (::), but this shorthand can only be used once in an IPV6 address

    - For example, 2018:0000:0000:0000:0000:0000:4815:54ae can be represented as 2018::4815:54ae

### IPV6 Address Types

- There are 3 different IPV6 Address types

    - Unicast Addresses

    - Multicast Addresses

    - Anycast Addresses

- Unlike IPV4, we can assign multiple IPV6 addresses to a single interface on a client, and these IPV6 addresses can be a mixture of any of the 3 different types of IPV6 addresses

#### Unicast Addresses

- Unicast Addreses are used to identify a single interface and can be broken down into two categories

    - Globally-Routed

        - Similar to IPV4's unicast class A, B, and C addresses

        - **Begins with 2000-3999**

    - Link-Local (Local Use)

        - Similar to IPV4's private IP ranges in that it can only be used on a local area network

        - Begins with FE80 (as the first segment)

        - Whenever an IPV6 system starts up, it will create an FE80 Link-Local Address for each IPV6 interface on that system, even if a Globally-Routed address was already obtained for that interface through manual configuration or through a configuration protocol such as DHCP

            - This automatic FE80 Link-Local Address configuration occurs through **Stateless Address Autoconfiguration (SLAAC)**

#### Stateless Address Autoconfiguration (SLAAC)

- Stateless Address Autoconfiguration elimates the need for hosts to obtain addresses or other configuration information from a central server

- Hosts can independently select Link-Local Addresses, test the uniqueness of that Link-Local Address, assign the Link-Local Addresses to themselves, contact the router, and provide direction to the node about how to proceed with the autoconfiguration

    - The host can even configure the global unicast address that it prefers to use (assuming that it is available for use)

#### Extended Unique Identifier (EUI)

- The Extended Unique Identifier process allows a host to assign itself a unique 64-bit IPV6 interface identifier called an EUI-64

    - This EUI-64 is obtained from the 48-bit MAC address of the network interface

        - The 48-bit MAC address is first separated into two 24-bit portions

            - The first 24-bit portion contains the Organizational Unique Identifier (OUI)

            - The second 24-bit portion contains the Network Interface Card (NIC) number

        - Between the two 24-bit portions of the divided 48-bit MAC address, we add a hexadecimal value of FF EE, giving us a 64-bit Extended Unique Identifier

    - After obtaining the EUI-64, the network interface uses autodiscovery to determine the network it is on and adds the 64-bit network portion of the IPV6 address to the front of the EUI-64 to create a unicast globally-routable IPV6 address

- DHCP can be used in IPV6 as an alternative to SLAAC and EUI-64 if preferred, however the DHCPv6 protocol needs to be used for compatibility with IPV6

    - DHCPv6 Protocol allows DHCP to automatically assign addresses from a DHCPv6 server

#### Neighbor Discovery Protocol (NDP)

- Neighbor Discovery Protocol allows hosts to learn the Datalink Layer (OSI Model Layer 2) addresses on a given network for the following purposes:

    - Router Solicitation

        - Used to locate routers on a network to determine default gateway

    - Router Advertisement

        - Routers can advertise themselves using NDP as an alternative to router solicitation by hosts

    - Neighbor Solicitation

        - Used to locate other clients on a given network and determine how to communicate with them directly

    - Neighbor Advertisement

        - Clients can advertise themselves (and the services that they offer) using NDP as an alternative to neighbor solicitation by hosts

    - Redirection

        - Routers can inform hosts that there are better first-hop routers on the network to use instead of themselves, which increases the overall efficiency of the network

### Multicast Addresses

- Multicast Addresses are used to identify a set of interfaces

    - **Begins with FF** (as the first two digits within the first segment)

- Packets send to a multicast address will be distributed to all of the interfaces within that group

### Anycast Addresses

- Anycast Addresses are used to identify a set of interfaces so that a packet can be sent to any member of a set

    - Anycast Addresses are allocated from the unicast address space, so theres no way to determine if an IPV6 address is anycast or unicast just by looking at the IPV6 address

## IPV6 Data Flows

### Overview

- IPV4 had unicast, multicast, and broadcast data flows

- IPV6 keeps unicast and multicast data flows, but eliminates broadcast data flows in favor of anycast data flows

#### Unicast

- Works as it did in IPV4, but uses IPV6 addresses instead of IPV4 addresses

#### Multicast

- Works as it did in IPV4, but uses IPV6 addresses instead of IPV4 addresses

    - Server addresses the packets to the multicast group, which starts with **FF** as the first two digits of the first segment in IPV6, and the switch will distribute additional copies to all of the receipients in the multicast group

#### Anycast

- Data travels from a single source to the device nearest to multiple (but specific) destination devices

    - Anycast is designed to let one host initiate an efficient updating of router tables for a group of other hosts

        - IPV6 is able to determine which gateway the host is closest to and send the packets to that gateway as though it was a unicast communication

        - The gateway sends the packets through anycast to any other hosts in the group until all of the routing tables are updated