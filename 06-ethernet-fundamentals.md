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

    

