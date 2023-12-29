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

