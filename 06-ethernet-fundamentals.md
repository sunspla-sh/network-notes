# Ethernet Fundamentals

## Overview

### History of Ethernet

- Historically there were many Datalink Layer (OSI Model Layer 2) protocols vying for dominant market position in local area networking such as the following:

    - Ethernet

    - Token Bus

    - Token Ring

    - FDDI (Fiber Distributed Data Interface)

    - Local Talk

    - Apple Talk

- Ethernet became the market leader and first operated over coaxial cables using 10BASE2 (ThinNet) and 10BASE5 (ThickNet) in the early 1980s

- Eventually Ethernet became known for twisted pair cabling (CAT3) using 10BASE-T

- Initially, it was undecided whether networks should be **deterministic** or **contention-based**:

    - **Deterministic networks** are orderly and require electronic tokens to transmit

        - Examples of deterministic networks include the following

            - Token Ring

            - Token Bus

    - **Contention-based** networks are chaotic and transmit whenever possible (which can cause collisions)

        - Examples of contention-based networks include the following

            - Ethernet

### Preventing Collisions on Ethernet

- **Carrier Sense Multiple Access with Collision Detection (CSMA/CD)** prevents collisions by using carrier-sensing to defer transmission until no other stations are transmitting

    - The steps for CSMA/CD include the following

        1. Listen for signals on the carrier (wire)

        2. If activity is detected - wait and then return to step 1

        3. Else - transmit

            a. If collision is detected - stop transmitting, wait with a random backoff timer, and then return to step 1

            b. Else - transmission complete

- **Collision Domains** are each area of a network that share a single segment

    - Best practice is to keep network segments small to decrease collisions

- **Ethernet Switches** increase the scalability of a network by creating multiple collision domains


### Reviewing Ethernet Standards for Copper Media

- For the review, standards will use the following layout

        CATEGORY

            STANDARD

                BANDWIDTH

                DISTANCE

    - CAT 3

        - 10BASE-T

            - 10 Mbps

            - 100 meters

    - CAT 5

        - 100BASE-TX

            - 100 Mbps

            - 100 meters

    - CAT 5e

        - 1000BASE-T

            - 1000 Mbps

            - 100 meters

    - CAT 6 

        - 1000BASE-T

            - 1000 Mbps

            - 100 meters

        - 10GBASE-T

            - 10 Gbps

            - 55 meters

    - CAT 6a

        - 10GBASE-T

            - 10 Gbps

            - 100 meters

    - CAT 7

        - 10GBASE-T

            - 10 Gbps

            - 100 meters

    - CAT 8

        - 40GBASE-T

            - 40 Gbps

            - 30 meters

- **Bandwidth** measures how many bits the network can transmit per second

### Reviewing Ethernet Standards for Fiber Media

- For the review, standards will use the following layout

        CATEGORY

            STANDARD
                
                MODE

                BANDWIDTH

                DISTANCE

    - 100BASE-FX

        - MMF (Multi-mode Fiber)

        - 100 Mbps

        - 2 kilometers

    - 100BASE-SX

        - MMF

        - 100 Mbps

        - 300 meters

    - 1000BASE-SX

        - MMF

        - 1000 Mbps

        - 220-550 meters

    - 1000BASE-LX

        - SMF (Single Mode Fiber) or MMF (Multi-mode Fiber)

        - 1000 Mbps

        - 5 kilometers (SMF) or 550 meters (MMF)

    - 10GBASE-SR

        - MMF

        - 10 Gbps

        - 400 meters

    - 10GBASE-LR

        - SMF

        - 10 Gbps

        - 10 kilometers

## Network Infrastructure Devices

### Identifying Network Infrastructure Devices

- Hubs

    - Hubs, also known as *multiport repeaters*, are Physical Layer (OSI Model Layer 1) devices that connect multiple network devices and workstations

    - On charts, hubs can be identified by a **square icon with two arrows pointing in opposite directions**

    - Three different types of Hubs:

        - Passive

            - Repeats signal with no amplification

            - Because there is no amplification, a 75 meter cable connected to a 50 meter cable by a passive hub would be the equivalent of a 125 meter cable and therefore our network would not work well as it is over the 100 meter limit

        - Active

            - Repeats signal with amplification

            - Because there is amplification, a 75 meter cable connected to a 50 meter cable by an active hub (for a total of 125 meters) will work fine as the active hub restarts the 100 meter limit

        - Smart

            - Similar to an active hub because it repeats signal with amplification, but also has enhanced features like SNMP (Simple Network Management Protocol) which allows it to be remotely configured

    - Hubs do NOT break up collision domains, instead they connect them, which becomes a problem when working with larger networks

- Bridges

    - Bridges are Datalink Layer (OSI Model Layer 2) devices that analyze source MAC addresses and make intelligent forwarding decisions based on the destination MAC in a given frame

    - Bridges break up collision domains into smaller collision domains

    - On charts, bridges can be identified by a **square icon with a semi-circle cutout**

- Switches

    - Switches, also known as multiport bridges, are Datalink Layer (OSI Model Layer 2) devices that connect multiple network segments together (by acting as both a hub and a bridge)

    - Each port on a switch represents an individual collision domain, but each device connected to the switch by those ports is a part of the same broadcast domain

    - Switches only know about Layer 2 and MAC Addresses, so they won't be used for connecting to external networks using protocols like IPV4 or IPV6

    - On charts, switches can be identified by a **square icon with four arrows, two pointing in on direction and another two pointing in the opposite direction**

- Routers

    - Routers are Network Layer (OSI Model Layer 3) devices that connect multiple networks and make forwarding decisions based on logical network information

    - Routers separate our broadcast domains and improve the efficiency of our networks by doing so

    - On charts, routers can be identified by a **circle icon with four arrows, two pointing inwards and another two pointing outwards**

- Layer 3 Switches

    - Layer 3 Switches are Network Layer (OSI Model Layer 3) devices that make layer 3 routing decisions and then interconnect entire networks, not just network segments like traditional layer 2 switches

    - Each port on a Layer 3 Switch acts as its own broadcast domain and its own collision domain

    - Layer 3 Switches are not as efficient at routing as a traditional Router, so it's best not to use them in larger networks

    - On charts, Layer 3 Switches can be identified by a **square icon with many arrows all pointing outwards from the center**

## Hands-on With Devices

### Home Devices

- Combination Device

    - Most homes will have a single combination device that acts as a media converter, switch, router, and frequently also as a wireless access point


### Corporate Office Devices

- Most corporate offices and some homes use separate devices instead of a combination device

  - Media Converters

      - Media Converters will convert two dissimilar signals of any format, e.g. fiber to cable, cable to ethernet, fiber to ethernet, HDMI to ethernet, etc

          - Fun fact: HDMI only has a ~20 foot (~7 meter) range, so it's best to convert from HDMI to ethernet at the source for longer distances and then back to HDMI at the receiving destination

  - Switches

      - Switches can be small or large, with as few as 3 ports or as many as 52 ports

  - Wireless Access Points (WAP)

      - Traditional wireless access points are simple media converters that go from copper media to wireless, typically having an RJ45 connection on the side, although there are other types of wireless access points that convert between other types of media and wireless

## Additional Ethernet Switch Features

### Overview

- Additional Ethernet Switch features include the following:

    - Virtual LANs (VLANs)

    - Trunking

    - Spanning Tree Protocol (STP)

    - Link Aggregation

    - Power over Ethernet (PoE)

    - Port Monitoring

    - User Authentication

- The additional features of Ethernet Switches improve capabilities in the following areas:

    - Network performance

    - Redudancy

    - Security

    - Management

    - Flexibility

    - Scalability

### Link Aggregation Control Protocol (LACP) (IEEE 802.3ad)

- Link Aggregation Control Protocol (LACP) combines multiple physical connections into a single logical connection to minimize congestion

    - For example, on a 24 port 100 Mbps switch, we can hit bandwidth limits if more than one connected device is trying to operate at a full 100 Mbps, but there is only one outgoing 100 Mbps connection to another switch
    
        - We can work around this outgoing limitation by combining multiple ports of the switch into a single, larger logical connection to provide more bandwidth (e.g. turning ports 1-4 of the switch into a single logical connection with a bandwidth of 400 Mbps, thus allowing up to 4 switch-connected devices to communicate at their full, individual 100 Mbps each at once)

        - Theoretically we could still hit limits with this larger logical connection, but it is unlikely that many devices on the switch will be operating with their full 100 Mbps simultaneously

### Power over Ethernet

#### Power over Ethernet (PoE 802.3af)

- Power over Ethernet (PoE) supplies electrical power over ethernet and requires CAT5 or higher copper cable with RJ45 connector

  - Provides up to 15.4 watts

#### Power over Ethernet+ (PoE 802.3at)

- Power over Ethernet+ (PoE+) supplies electrical power over ethernet and requires CAT5 or higher copper cable with RJ45 connector

  - Provides up to 25.5 watts

#### Power Sourcing Equipment (PSE)

- Power Sourcing Equipment is the equipment (in this case, Ethernet Switches) providing the power to devices

#### Powered Device (PD)

- Powered Devices are the Ethernet-connected devices that are receiving power, often VoIP phones or Wireless Access Points

### Port Monitoring / Port Mirroring

- Port Monitoring, also known as Port Mirroring, makes a copy of all traffic destined for a port and sends it to another port

    - On a hub, collecting traffic data is simple because the hub will rebroadcast to all ports

    - On switches, port monitoring/port mirroring can be configured so that, for example, ports 1-23 of a 24 port switch handle network traffic and port 24 is a network analyst machine that receives copies of all traffic on ports 1-23

        - This setting must be configured because switches, unlike hubs, do not normally rebroadcast on all ports in order to improve overall network efficiency

- Port monitoring/port mirroring is used to improve network security

### User Authentication (802.1x)

- User Authentication requires users to authenticate themselves before being able to gain access to the network

- User Authentication Flow:

    - Switch-level authentication requires that the supplicant (switch-connected device such as a desktop or laptop that wants to access the network) asks for permission to join the network

    - Switch sends the request onward to the authentication server

    - Authentication server checks supplicant's credentials and creates a key for the supplicant if it is authorized

    - The created key is used to encrypt traffic between the switch and the supplicant

### Management Access and Authentication

- Switches can be managed and configured in three ways:

    - Secure Shell (SSH)

        - SSH allows for remote configuration of switches

    - Console Port

        - Console Ports allow for local configuration of switches

        - Typically uses a RS232 Serial Cable, also known as a rollover cable, with one end as an RJ45 connector and another end as a DB9 connector

    - Out-of-Band (OOB) Management

        - Keeps all network configuration devices on a separate network

### First-Hop Redundancy

- First-hop Redundancy often uses **Hot Standby Router Protocol** (HSRP) to create virtual IP and MAC addresses to provide active and standby routers

    - HSRP groups consist of an *Active Router* (physical device), a *Standby Router* (physical device), and a *Virtual Router* (logical device)

        - Properly configured computers on the network will only see and send traffic to the Virtual Router

        - The Virtual Router will know which of the two physical routers is Active or Standby, and then send traffic to the appropriate router

    - HSRP is the most popular First-hop Redundancy protocol and used in most networks today, but other First-hop Redundancy protocols include the following:

        - Gateway Load Balancing Protocol (GLBP)

        - Virtual Router Redundancy Protocol (VRRP)

        - Common Address Redundancy

### MAC Filtering

- MAC Filtering permits or denies traffic based on a device's MAC address

    - This filtering occurs at the Datalink Layer (OSI Model Layer 2)

### Traffic Filtering

- Traffic Filtering permits or denies traffic based on IP addresses or application ports

    - If we are filtering by IP addresses, this filtering occurs at the Network Layer (OSI Model Layer 3)

    - If we are filtering by Ports, this filtering occurs at the Transport Layer (OSI Model Layer 4)

### Quality-of-Service (QoS)

- Quality-of-Service allows prioritizing traffic based on device or protocol

    - For example, we might want to prioritize a VoIP phone device or prioritize all UDP traffic in general, because that VoIP phone uses UDP to send datagrams of the user's voice and we don't want their voice cutting in and out during a call, but other TCP traffic on the network can be given a lower priority because TCP handles dropped packets and re-transmissions

## Spanning Tree Protocol (802.1d)

### Overview

- Spanning Tree Protocol (802.1d) permits redundant links between switches and prevents the looping of network traffic

### Shortest Path Bridging (SPB)

- Shortest Path Bridging (SPB) is used instead of Spanning Tree Protocol (STP) for larger network environments

### Broadcast Storms

- Broadcast Storms occur when multiple copies of frames are forwarded back and forth, which then consumes the network

    - Spanning Tree Protocol solving the Broadcast Storm problem using root and non-root bridges

### Bridge ID

- The combination of a priority value and a MAC address (of a switch)

- Priority value is based on the category of cabling being used

### Root Bridge

- The Root Bridge is the bridge (technically a switch, which is also known as a multiport bridge) with the lowest bridge ID (BID)
    
    - It is elected to act as a reference point for the entire spanning tree

    - Typically if priority values are equal, then the decision on root bridge is made by whichever switch has the lowest MAC address

### Non-Root Bridge

- Non-Root Bridges are all switches in an STP topology other than the Root Bridge

### Root Port

- Every non-root bridge has a single root port which is closest to the root bridge in terms of cost

    - Cost is determined by cable type, with faster cables having a lower cost and slower cables having a higher cost

### Designated Port

- Every network segment has a designated port, which is the closest to the root bridge in terms of cost

    - All of the ports on the root bridge are considered to be designated ports, because they are all on the root bridge and therefore equally close to the root bridge in terms of cost

### Non-Designated Port

- Non-designated ports block traffic to create loop-free topology

    - Non-designated ports still receive the information as *Bridge Protocol Data Units (BPDUs)*, but do not forward the information

    - Non-designated ports can become designated ports if a network segment goes down by transitioning through four states:

        - Blocking

            - BPDUs are received but not forwarded

        - Listening

            - Populates the MAC address table, but does not forward frames

        - Learning

            - Processes BPDUs and determines its own role in the spanning tree

        - Forwarding

            - Forwards frames for operations (becoming either a root port or designated port in the process)

### Link Cost

- Link Cost is associated with the speed of the link - the lower the link's speed, the higher the cost

    - Cost Examples

        - Ethernet

            - 10 Mbps

            - 100 STP Port Cost

        - Fast Ethernet

            - 100 Mbps

            - 19 STP Port Cost

        - Gigabit Ethernet

            - 1 Gbps (1000 Mbps)

            - 4 STP Port Cost

        - 10-Gigabit Ethernet

            - 10 Gbps (10000 Mbps)

            - 2 STP Port Cost

    - Recently costs for cable types have been updated to reflect faster and faster cable types, so do not expect STP Port Costs to remain static, however they will always remain in a highest to lowest order for slowest to fastest cables

## Virtual Local Area Networks (VLANs)

### Overview

- Virtual Local Area Networks allow different logical networks to share the same physical hardware and provide additional security and efficiency

    - Different ports can be used for different broadcast domains

### VLAN Trunking (802.1q)

- Multiple VLANs are transmitted over the same physical cable (but in a network diagram, the VLANs are represented by separate logical cables)

#### Trunk

- A **trunk** is the single physical cable carrying multiple VLANs

#### 4-Byte Identifiers

- 4-Byte Identifers are electronic tags that allow us to identify different VLANs going over a single trunk

    - There are two piecies of 4-Byte identifiers:

        - Tag Protocol Identifier (TPI)

        - Tag Control Identifier (TCI)

    - An untagged VLAN is considered to be the **native VLAN** and is also known as **VLAN zero**

## Specialized Network Devices

### Overview

- Outside of the standard routers, switches, hubs, bridges, servers, and workstations, there are many specialized network devices (used for less common tasks) such as VPN concentrators, firewalls, proxy servers, content engines, and content switches

### VPN Concentrators

- A *Virtual Private Network* creates virtual tunnels over an untrusted network like the internet

- **VPN Concentrators** are devices that terminate VPN tunnels and allow for multiple VPN connections in one location

    - VPN Concentrators can be separate physical devices or logical devices that are built into other devices like UTMs (Unified Threat Management systems) or Firewalls

    - Most modern Firewalls will have this functionality, but when using this functionality it is considered to be a logical VPN Concentrator and not a Firewall

- **VPN Headends** are a specific type of VPN concentrator used to terminate IPSec VPN tunnels within a router or other device

### Firewalls

- Firewalls are network security appliances placed at the boundary of a network

    - Firewalls can be either software or hardware

    - Firewalls can be either stateful or stateless

- Firewalls allow traffic to go from inside the network to outside the network (e.g. from your office network to the internet) and can also block traffic attempting to come from outside the network to inside the network (e.g. from the internet to your office network)

- On network charts/network diagrams, Firewalls can be identified by three different icons:

    - Pix Firewalls are identified by a **circle icon with a forward-step icon (play symbol with vertical bar after it)**

        - These icons are commonly used by Cisco because Pix is their brand of Firewall

    - Generic Firewalls are identified by a **brick wall icon**

    - Routers with Firewalls are combination devices that are identified by a **standard circular router icon with a brick circular base**

#### Next-Generation Firewalls (NGFWs)

- Next-Generation Firewalls are firewalls that are able to conduct deep packet inspection at Layer 7 and can look through traffic to detect and prevent attacks

- Traditional firewalls will block based on IP Addresses and possibly port and protocol, but Next-Generation Firewalls can look deeping into the traffic to block attacks by continually connecting to cloud resources to get the latest threat information

### Intrusion Detection Systems (IDSs) and Intrusion Prevention Systems (IPSs)

- Intrusion Detection Systems (IDSs) can see and log attack signatures and anomaliesn

- Intrusion Prevention Systems (IPSs) can see and log attack signatures and anomalies like an IDS, but additionally they can respond to attacks through signatures and anomalies

    - IPSs will shut off ports and protocols in an attempt to stop an attack

- IDSs and IPSs can be either host-based or network-based devices

- On network charts/network diagrams, IDSs and IPSs are represented by **square icons with left and right facing arrows going through a circle**

### Proxy Servers

- Proxy Servers make requests to an external network on behalf of a client

    - Proxy Servers can perform content filtering and logging

    - Proxy Servers can also cache content to save bandwidth and time

### Content Engines (Caching Engines)

- Content engines, also known as Caching Engines, are dedicated applications that perform the caching function of a proxy server

    - Content Engines are more efficient that a proxy server when it comes to caching

    - Content Engines are helpful for branch offices with slow internet connections, because data can be sync'd periodically from the main office, and then requested from content engine on the fast internal network of the branch office rather than needing to go over a low bandwidth internet connection back to the head office

- On network charts/network diagrams, Content Engines are identified by **square icons with a database cylinder and three arrows pointing to the cylinder on one side and one arrow point to the cylinder on the other side**

### Content Switches (Load Balancers)

- Content Switches, also known as Load Balancers, distribute incoming requests across various servers in a server farm

    - Distributing requests across various servers prevents any one server from becoming overloaded

    - Additionally, large tasks can be broken up into smaller tasks and split across servers to speed up the task, after which the content switch/load balancer can recombine the results of the distributed task and send back a response

## Other Devices

### Overview

- Other devices encountered on a network (that are not specialized networking devices required for the network to properly function) include the following:

    - VoIP Phones

    - Printers

    - Access Control Devices

    - Cameras

    - HVACs

    - Internet of Things

    - Industrial Control Systems (ICS)

    - Supervisory Control and Data Acquisition (SCADA)

### VoIP Phones (Voice-over-IP Phones)

- VoIP Phones are hardware devices that connect to an IP network in order to make a connection to a call manager within that same network

#### Unified Communications (or Call) Manager

- Unified Communications Managers are used to perform call processing for hardware and software-based IP phones so that VoIP phones can connect to external or public telephone networks

### Printers

- Printers are hardware devices that convert digital documents into physical, paper documents

- Printers can be directly connected to a computer by USB or connected to a network and shared by multiple users

    - Network printers can be wired or wireless

        - Configuration of Network Printers can be done manually with a static IP Address or by using DHCP (Dynamic Host Configuration Protocol)

### Access Control Devices

- Physical Access Control Devices include devices like security gates, turnstiles, door locks, and others

- These Access Control Devices are often, but not always, connected to a network, which is often its own separate network from the corporate network for additional security

    - If Access Control Devices are connected to a corporate network, they should be placed into their own separate VLAN for additional security controls and safety

### Cameras

- Security Cameras should be connected to a separate security network, often the same network that the Access Control Devices are using

    - Like Access Control Devices, if Security Cameras are connected to the corporate network, then it should be through a separate VLAN for additional security

### Heating, Ventilation, and Air Conditioning (HVAC)

- HVAC systems and sensors can control the heating, ventilation, humidity, and air conditioning of a physical location

    - Like Access Control Devices and Security Cameras, HVAC should be placed on a separate security network or on a VLAN if on the corporate network

    - HVAC systems are especially useful for monitoring the conditions of places that people do not work in daily, such as server rooms and telecommunication closets

### Internet of Things (IoT)

- Internet of Things (IoT) is a catch-all term for any non-standard networked devices such as smart TVs, smart watches, smart refrigerators, smart speakers, smart thermostats, smart doorbells, etc.

    - Like Access Control Devices, Security Cameras and HVAC, Internet of Things devices should be placed on a separate security network or on a VLAN if on the corporate network because they do not typically have strong built-in security by default

### Industrial Control Systems (ICS)

- Industrial Control Systems describes the different types of control systems and associated instrumentation that is used to operate and automate industrial processes

    - The ICS devices are different depending on the type of industry, but typically ICS systems include electronic sensors in equipment that are built specifically to have an effect on the physical world

    - ICS devices should be placed on a separate security network or on a VLAN if on the corporate network because they do not typically have strong built-in security by default

### Supervisory Control and Data Acquisition (SCADA)

- Supervisory Control and Data Acquisition (SCADA) systems acquire and transmit data from different systems to a central panel for monitoring and control

    - SCADA devices should be placed on a separate security network or on a VLAN if on the corporate network because they do not typically have strong built-in security by default