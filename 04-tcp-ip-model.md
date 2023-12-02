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