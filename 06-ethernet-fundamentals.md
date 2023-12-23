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

### Link Aggregation (IEEE 802.3ad)

- Link Aggregation combines multiple physical connections into a single logical connection to minimize congestion

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