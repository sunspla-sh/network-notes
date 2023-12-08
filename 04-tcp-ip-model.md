# TCP/IP Model

## Overview

### What is the TCP/IP Model

- The TCP/IP Model is a reference model for computer networking and troubleshooting with 4 layers rather than the 7 layers of the OSI model

- Also known as the TCP/IP Stack or the DoD Model

- The TCP/IP Model is a predecessor of and alternative to the OSI Model, and also serves as the basis for most modern computer networks

- The 4 layers of the TCP/IP Model are listed below from top to bottom (highest to lowest layer):

    - Application Layer (Layer 4)
        - Equivalent to the Application, Presentation, and Session layers of the OSI model
    - Transport Layer (Layer 3)
        - Equivalent to the Transport layer of the OSI model
    - Internet Layer (Layer 2)
        - Equivalent to the Network layer of the OSI model
    - Network Interface Layer (Layer 1)
        - Equivalent to the Datalink and Physical layers of the OSI model

## Network Interface Layer (Layer 1)

### What is the Network Interface Layer?

- The Network Interface Layer describes how to transmit bits across a network and determines how the network medium is going to be used

## Internet Layer (Layer 2)

### What is the Internet Layer?

- The Internet Layer is where data is taken and packaged into IP datagrams

- Some protocol examples at this layer include the following:

    - IP
    - ICMP
    - ARP
    - Reverse ARP

## Transport Layer (Layer 3)

### What is the Transport Layer?

- The Transport Layer of the TCP/IP model is identical to the transport layer of the OSI model

- The Transport Layer defines the level of service and the status of the connection being used by TCP, UDP, RTP, or other layer 3 protocols

## Application Layer (Layer 4)

### What is the Application Layer?

- The Application Layer dictates how programs are going to interface with the transport layer by conducting session management

- Additionally, the Application Layer is where the user interacts with the network using some sort of program

- Some protocol examples at this layer include the following:

    - HTTP
    - Telnet
    - FTP
    - SSH
    - SNMP
    - DNS
    - SMTP
    - SSL/TLS

## Data Transfer over Networks

### What is a Port?

- Ports are logical openings on a system representing a service or application that is listening and waiting for traffic

    - Ports are numbered from 0 to 65,535
    - Well-known/Reserved ports are from 0 to 1023 and some examples are listed here:
        - FTP on port 21
        - HTTP on port 80
        - SMTP on port 25
    - Ephemeral ports are from 1024 to 65,535

- Data Transfer occurs using ports and IP addresses
    1. Client has a source IP address and a source port (random high port number opened specifically for the connection)
    2. Client sends data to a destination IP Address and destination port, which is port 80 in the case of web servers
    3. Web Server has a source IP address and source port (80) 
    4. Web Server sends data to a destination IP Address and destination port, which are the Client source IP Address and Port (the same random high port number that the client initially used) (the port is closed by the client after receiving the response from the web server)

## Ports and Protocols

### What are the 28 Ports and Protocols on the Network+ Exam?

- File Transfer Protocol (FTP)
    - Ports 20, 21
        - Provides insecure file transfers

- Secure Shell (SSH)
    - Port 22
        - Provides secure remote control of another machine using a text-based environment

- Secure File Transfer Protocol (SFTP)
    - Port 22
        - Provides secure file transfers

- Telnet
    - Port 23
        - Provides insecure remote control of another machine using a text-based environment

- Simple Mail Transfer Protocol (SMTP)
    - Port 25
        - Provides the ability to send emails over the network

- Domain Name Service (DNS)
    - Port 53
        - Converts domain names to IP addresses, and IP addresses to domain names

- Dynamic Host Configuration Protocol (DHCP)
    - Ports 67, 68
        - Automatically provides network parameters to clients, such as assigned IP address, subnet mask, default gateway, and DNS server

- Trivial File Transfer Protocol (TFTP)
    - Port 69
        - Allows bi-directional lightweight file transfer for sending configuration files or network booting of an operating system (no authentication or directory visibility)

- HyperText Transfer Protocol
    - Port 80
        - Insecure web browsing

- Post Office Protocol Version Three (POP3)
    - Port 110
        - Used to receive incoming emails

- Network Time Protocol (NTP)
    - Port 123
        - Used to keep accurate time for clients on a network

- Network Basic Input/Output System (NetBIOS)
    - Port 139
        - Used for file or printer sharing in a Windows network

- Internet Mail Application Protocol (IMAP)
    - Port 143
        - Method of retrieving incoming emails which improves upon the older POP3 method

- Simple Network Management Protocol (SNMP)
    - Ports 161, 162
        - Used to collect data about network devices and monitor their status

- Lightweight Directory Access Protocol (LDAP)
    - Port 389
        - Used to provide directory information services to a network (in an open-source manner, as opposed to Windows Active Directory, which is a proprietary version of LDAP), e.g. searching for internal company email addresses and users in an email client address book on a business computer

- HyperText Transfer Protocol Secure (HTTPS)
    - Port 443
        - Secure web browsing (using either TLS (newer) or SSL (older))

- Server Message Block (SMB)
    - Port 445
        - Used for Windows file and printer sharing services (often operates with NetBIOS, which does authentication over port 139 while SMB handles the actual passing of the files)

- System Logging Protocol (Syslog)
    - Port 514
        - Used to send logging data back to a centralized server

- Simple Mail Transfer Protocol Transport Layer Security (SMTP TLS)
    - Port 587
        - Secure and encrypted way to send emails (and not technically its own protocol, rather it is regular SMTP wrapped in TLS)

- Lightweight Directory Access Protocol - Secure (LDAPS)
    - Port 636
        - Provides secure directory services

- Internet Message Access Protocol over SSL (IMAP over SSL)
    - Port 993
        - Secure and encrypted way to receive emails

- Post Office Protocol Version Three over SSL (POP3 over SSL)
    - Port 995
        - Secure and encrypted way to receive emails

- Microsoft SQL Server (MSSQL)
    - Port 1433
        - Used for communication from a client to a Microsoft SQL server database engine

- Oracle Net Services (formerly known as SQLnet protocol)
    - Port 1521
        - Used for communication from a client to an Oracle database

- MySQL Protocol
    - Port 3306
        - Used for communication from a client to a MySQL server database engine

- Remote Desktop Protocol (RDP)
    - Port 3389
        - Provides graphical remote control of another client or server

- Session Initiation Protocol (SIP)
    - Ports 5060, 5061
        - Used to initiate VoIP and video calls

## Finding Open Ports

### nmap

- ```nmap``` is a network mapping tool used scan computers on a network to determine which ports are open (and which services are using those ports)

- Useful ```nmap``` commands are listed here:
    - ```sudo nmap -v -sSU -O 127.0.0.1 -p-```
        - Scans all ports on localhost for TCP and UDP, plus lists the operating system of the scanned computer
    - ```sudo nmap -v -T4 -A 127.0.0.1```
        - Intensive TCP scan that generates more data about open ports and the services running on them


### netstat

- ```netstat``` is a network statistics tool used to list active connections to and from a computer (including the ports and program names/pids that created those connections)

- Useful ```netstat``` commands are listed here:
    - ```sudo netstat -4plunt```

## IP Protocol Types

### TCP Review

- Transmission Control Protocol (TCP) operates at layer 4 of the OSI model and operates by conducting a three way handshake between client and server to establish a connection

    - Client and Server constantly negotiate how much data can be received through a method known as **windowing**

    - Client must acknowledge to server that all segments were received through an ACK flag in a TCP header, but ACK does not have to occur for every segment immediately and one ACK may acknowledge multiple segments

    - Server **window** defines how much data it can send before it *must* receive an ACK

    - TCP is considered to be a *connection-oriented* protocol because of the ACK requirements

### UDP Review

- User Datagram Protocol (UDP) operates at layer 4 of the OSI model and operates without acknowledgements between the client and server and without verification of the ordering of the datagrams that the server sends to the client

  - UDP is preferable in specific use cases such as streaming audio and video because the lack of acknowledgements and smaller header allows higher throughput

  - UDP is considered to be a *connectionless* protocol because there is no acknowledgement that the client recieved datagrams from the server

### What is Internet Control Message Protocol (ICMP)?

- Internet Control Message Protocol (ICMP) is a Network Layer (Layer 3) protocol that is used to communicate information about network connectivity issues back to the sender

  - ICMP is listed as protocol #1 in the TCP/IP model

  - ICMP reports on the following issues

      - Dropped packets (when packets are arriving too fast to be processed)

      - Connectivity issues (when a destination host cannot be reached)

      - Redirection (which tells a sending host to use another router)

  - An example of a program that uses ICMP is ```ping```, which is often used as a network troubleshooting tool to determine connectiviity

  - ICMP is also used by attackers to conduct ping scans and network mapping

### What is Generic Routing Encapsulation (GRE) Protocol?

- Generic Routing Encapsulation procotol is a simple and effective way to create a tunnel (known as a GRE tunnel) over a public network

    - When a GRE tunnel is established at the router level, you need to take into account maximum transmission unit (MTU) size

        - Typically you might use an MTU of ~1400 bytes so that even with extra encapsulation, the total size does not go over ~1500 bytes, which is often the pre-configured MTU limit for many network devices

    - GRE tunnels do **not provide any encryption**

### What is Internet Protocol Security (IPSec)?

- IPSec is a set of secure communication protocols and is used to protect one or more data flows between two peers

- IPSec authenticates and encrypts IP packets, which means that it operates at the Network Layer (Layer 3) of the OSI Model and at the Internet Layer (Layer 2) of the TCP/IP Model

- IPSec provides the following properties:

    - Data Confidentiality

    - Data Integrity

    - Origin Authentication

    - Anti-replay

- Like GRE, IPSec allows the creation of tunnels over public networks, but unlike GRE, IPSec **allows for encryption** of those tunnels, so it is often used to form virtual private networks (VPNs)

- IPSec uses the following two underlying protocols:

    - Authentication Headers (AH)

        - Authentication Header protocol provides integrity and authentication for packets

        - AH works by hashing the normal IP header and the data payload, and then uses that hash to create the new AH header which is appended to the packet and used by the receiving router for verification of data integrity

    - Encapsulating Security Payloads (ESP)

        - Encapsulating Security Payload protocol provides encryption and integrity for packets
