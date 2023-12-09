# Media and Cabling

## Overview

### What is Media?

- Media is the material used to transmit data over a network

- In terms of the Network+ exam, networking media is either **copper, fiber optic, and wireless.**

## Copper Media

### Overview

- There are three main types of copper media

    - Coaxial cables

    - Twisted pair cables

    - Serial cables

### Coaxial Cables

- Coaxial cables (also known as co-ax) are the oldest type of copper media

- Coaxial cables have the following structure, from innermost to outermost layers

    - Copper core

    - Insulator

    - Metallic shield

    - Braided metal shielding

    - Plastic jacket

- There are two main places coaxial cables are used in modern networks

    - RG-6

        - This very thick version of coaxial cabling is used by cable companies to connect their service to your home

    - RG-59

        - This coaxial cabling is used inside your home to carry composite video between two nearby devices or to connect an outlet to a cable modem

- There are two commonly used types of connectors for coaxial cabling

    - F-type

        - Most coaxial cables these days have F-type connectors

    - BNC

        - Short for Bayonet Neill Concelman connector or British Naval Connector

        - Common in older networks starting in the 1970s or 1980s, but much less common today in modern networks


#### Twinaxial Cable

- There is a newer form of cable known as a **twinaxial cable**, which is similar to coaxial cabling, but uses two inner conductors to carry the data instead of just one

- Twinaxial cabling is used for very short range, high speed connection between devices and uses less energy than traditional coaxial cabling

    - A use case example is that twinaxial cabling (specifically SFP+ direct attached copper cable) can replace fiber optic cabling as a cheaper option between two switches that are less than 7 meters apart and will provide speeds up to 10 gigabits per second

### Serial Cables

- Serial cables have a series of straight copper wires inside a single cable or plastic jacket

- There are two commonly used types of connectors for serial cabling

    - DB-9

        - DB-9 connectors have 9 pins

    - DB-25

        - DB-25 connectors have 25 pins

- Serial cables are also known as RS-232 cables, because that is the signaling method used when transmitting data over those cables

- Serial cables are old and not commonly used in modern networks, but they may be found in older networks using external ISDN modems, T1 modems, or E1 modems

### Twisted Pair Cabling

- Twisted pair cabling consists of a plastic sheath surrounding 8 individual wires twisted into 4 pairs

    - The more twists per linear unit of cable, the better the protection from electromagnetic interference (and conversely, the less twists, the less protection from interference)

- Twisted pair cabling is the most popular local area network cabling technology used in networks today

- There are two common types of twisted pair cabling

    - Unshielded Twisted Pair (UTP)

        - UTP is easier to install and less expensive because of the lack of extra metal shielding, so the cable is more flexible

    - Shielded Twisted Pair (STP)

        - STP is more expensive and harder to install because of the extra metal shielding, which makes the cable less flexible

    - STP and UTP operate about the same (with the exception of less electromagnetic interference in STP) and have similar distance limitations

- There are two commonly used types of connectors for twisted pair cabling

    - RJ45

        - Plastic, 8 pin connector used frequently in ethernet-based networks with CAT5, CAT6, CAT7, and CAT8 cables

        - Using 10BASE-T (10Mbps) and 100BASE-TX (100 Mbps) standards only 4 of the 8 pins in an RJ45 connector are in use and the other pins are reserved for future use (or alternatively can be used for power-over-ethernet)

        - Using 1000BASE-T (1 Gbps) standard and higher, all 8 pins are used for data transfer

    - RJ11

        - Plastic, 6 pin connector used commonly in phone systems to connect a phone to a landline jack

        - Only 2 pins are actually used, one is reserved for the ring and one is reserved for the signal

        - In modern networking, you may come across an RJ11 if using a DSL modem for internet connectivity or if providing VoIP services through an analog telephone adapter, but other than that they are not very common

    - RJ is short for **Registered Jack**, which is a wiring standard for telecommunication network interfaces that are used to carry voice or data (with RJ11 being for traditional phone networks and RJ45 being for data networks)


### Bandwidth

- Bandwidth is the theoretical measure of how much data could be transferred from a source to a destination

### Throughput

- Throughput is the actual measure of how much data is transferred from a source to a destination

### Categories of Cabling

- There are many categories of cabling, but the ones listed on the Network+ exam include the following:

  - CAT 3

      - 10BASE-T 

          - 10 Mbps

          - 100 meters

      - Popular in the 1980s and 1990s

  - CAT 5

      - 100BASE-TX

          - 100 Mbps

          - 100 meters
      
      - The *TX* in the standard name denotes *twisted pair, fast ethernet*

  - CAT 5e

      - 1000BASE-T

          - 1000 Mbps (1 Gbps)

          - 100 meters

  - CAT 6

      - 1000BASE-T

          - 1000 Mbps (1 Gbps)

          - 100 meters

      - 10GBASE-T

          - 10 Gbps

          - 55 meters

      - CAT 6 cabling can operate on two standards, 1000BASE-T and 10GBASE-T, but with reduced range at the higher transmission speed standard of 10GBASE-T

  - CAT 6a

      - 10GBASE-T

          - 10 Gbps

          - 100 meters

  - CAT 7
      
      - 10GBASE-T

          - 10 Gbps

          - 100 meters

      - CAT7 was released over 7 years before CAT6a and can use a traditional RJ45 connector or a TERA connector

  - CAT 8

      - 40GBASE-T

          - 40 Gbps

          - 30 meters

- When reading ethernet standards such as 10BASE-T, the leading number *10* refers to the transmission speed in Mpbs (megabits per second), *BASE* denotes that baseband transmission is used, and *T* designates that twisted pair cabling is used

### Straight-Through Cable (Patch Cable)

- Straight-through cables, also known as patch cables, contain the exact same pinout on both ends of the cable

### Crossover Cable

- Crossover cables swap the send and receive pins on the other end of the cable when the connector and its pinout are created

### Standard Pinouts

- There are two standard pinouts

    - 568A

    - 568B

        - The preferred standard for wiring jacks inside buildings, so most straight-through cables (patch cables) use this pinout

### Data Terminal Equipment (DTE)

- Data Terminal Equipment is any device that acts as an endpoint for a connected piece of data communication equipment (DCE)

    - DTE Examples

        - Laptops

        - Desktops

        - Servers

        - Routers

### Data Communications Equipment (DCE)

- Data Communications Equipment is any device that that provides or facilitates network connectivity without acting as a direct endpoint

    - DTE Examples

        - Switches

        - Modems

        - Hubs
        
        - Bridges

### Connecting DTEs and DTCs

- Straight-through (patch) cables can be used for the following connections

    - DTE to DTC
    - DTC to DTE

      - Straight-through (patch) cables use the same pinout on both ends (usually the 568B standard)

- Crossover cables can be used for the following connections

    - DTE to DTE
    - DTC to DTC

    - Crossover cables use opposite pinouts of 568A on one end and 568B on the other end

#### Medium-Dependent Interface Crossover (MDIX)

- Medium-dependent Interface Crossover (MDIX) is an automated electronic simmulation of a crossover cable connector when a straight-through (patch) cable is used

    - Typically a switch-to-switch connection requires a crossover cable, but modern switchs have MDIX (medium-dependent interface crossover) which allows them to use straight-through (patch) cables instead of crossover cables

### Plenum Cables

- The word *plenum* usually refers to the space within a raised floor or suspended ceiling

- Plenum cables are UTP or STP cables with a special coating that provides a fire-retardand chemical layer to the outer insulating jacket

    - Typically plenum cables are required by law when laying cable in non-visible or not easily accesible areas such in ceilings, walls, raised floors, or near air ducts

    - Non-plenum rated cables are known as PVC cables

## Building A Cable