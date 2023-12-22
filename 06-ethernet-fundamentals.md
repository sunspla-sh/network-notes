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

