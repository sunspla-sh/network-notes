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

### Straight-through Cable Color Order

- On both ends of the cable

    1. Orange-white
    2. Orange
    3. Green-white
    4. Blue
    5. Blue-white
    6. Green
    7. Brown-white
    8. Brown

### Crossover Cable Color Order

- On one end of the cable

    1. Orange-white
    2. Orange
    3. Green-white
    4. Blue
    5. Blue-white
    6. Green
    7. Brown-white
    8. Brown

- On the other end of the cable

    1. Green-white
    2. Green
    3. Orange-white
    4. Blue
    5. Blue-white
    6. Orange
    7. Brown-white
    8. Brown

## Fiber Media

### Overview

### Fiber Optic Cables

- Fiber Optic Cables use light from a light-emitting diode (LED) or laser to transmit information through a thin glass fiber

    - There is little to no interference in Fiber Optic cables because we are using glass and light to transmit the data rather than metal wires and voltages

    - The range of Fiber Optic cables in on the order of hundreds of meters to hundreds of miles (as compared to less than one hundred meters for copper wires)

    - The data capacity of Fiber media is on the order of terabits per second (which is an improvement compared to the megabits per second or gigabits per second of copper media)

        - Speeds of up to one petabit per second have been reached with fiber in controlled experiments

        - At these high speeds with fiber media, its usually the other networking equipment that becomes the bottleneck such as switches, routers, and end-user devices

- Drawbacks of Fiber Optic Cables include the following:

    - Expensive

        - On the order of 5x to 10x more expensive than copper cables

    - More difficult to work with

        - Harder and more expensive to build and repair than copper cables

### Categories of Cables

- There are two main types of fiber optic cables

    - Single mode

    - Multimode

#### Single Mode Fiber (SMF)

- Single Mode Fiber is used for longer distances and has smaller core size which allows for only a single mode of travel for the light signal

    - Core size of 8.3-10µm (micrometers)

    - Allows a more precise signal transmission over a longer distance because light is focused down the narrow core and is not dispersed throughout a larger cross-section

#### Multimode Fiber (MMF)

- Multimode Fiber is used for shorter distances and has larger core size which allows for multiple modes of travel for the light signal

    - Core size of 50-100µm (micrometers)

    - Used for shorter distances of 2 kilometers or less

    - Multimode fibers can typically be used anywhere you would use a copper patch (straight-through) cable instead, such as connecting routers to switches, switches to switches, switches to servers, etc.

### Comparing SMF and MMF

- Multimode Fiber (MMF)

    - Larger core size

    - Covers shorter distances

    - Less expensive

    - Typically has an aqua-blue or orange colored sheath

- Single Mode Fiber (SMF)

    - Smaller core size

    - Covers longer distances

    - More expensive

    - Typically has a yellow colored sheath

### Fiber Optic Connectors

- There are 4 different connector types for fiber optic cables:

    - SC (Subscriber Connector)

    - ST (Straight Tip)

    - LC (Lucent Connector)

    - MTRJ (Mechanical Transfer Registered Jack)

        - Smaller form factor than the other three (about half the size) allowing for 24 ports instead of 12 ports in switches

- There are two different types of connector faces

    - APC (Angled Physical Contact)

        - Fiber endface is polished at an 8 degree angle

        - Better overall signal with less overall noise

        - SC connectors typically use APC

        - Identified by a green colored connector

    - UPC (Ultra Physical Contact)

        - No fiber endface angling, but polished with a curvature for better core alignment when plugged into a jack

        - Slightly more noise and slightly worse signal

        - MTRJ connectors typically use UPC

        - Identified by a blue colored connector


### Wavelength Division Multiplexing (WDM)

- Wavelength Division Multiplexing combines multiple signals into one signal and sends it over a single fiber optic strand using different wavelengths of the laser light source

    - Allows for bidirectional communication over a single strand

    - Increases bandwidth and capacity

- Transmitting end uses a multiplexer to combine several light signals together before sending across the fiber, which is then received by a demultiplexer on the receiving end and split into its component signals again

- Most WDM is run over single mode fibers, but there are a few types of WDM that can run over multimode fibers as well

- There are two main types of Wavelength Division Multiplexing (WDM):

    - Coarse WDM

    - Dense WDM

#### Coarse WDM (CWDM)

- Coarse WDM is used mainly in shorter distance applications of up to 70 kilometers, but you can only use 8 of the 18 total channels if above 40 kilometers and less than 70 kilometers

    - Wavelength Channels

        - Up to 18 channels (max 40 kilometers)

        - Up to 8 channels (between 40 and 70 kilometers) (because the light spreads out and creates more noise over longer distances)

    - Channel Distance

        - 20nm

    - Speed

        - Up to 10 Gbps (Ethernet)

        - Up to 16 Gbps (Fiber)

- CWDM is sometimes used to connect routers and switches using GBIC or SFF transceivers (which will be explained in the next section of notes 😁) with longer distances than you could using copper cable

#### Dense WDM (DWDM)

- Dense WDM is used to transport data over much longer distances as the connections can be amplified every 80-100km as they're going across the cable

    - Wavelength Channels

        - Up to 80 channels

    - Channel Distance

        - 0.8nm

    - Speed

        - Up to 8 Tbps (100 Gbps per channel)

- DWDM is extremely expensive, so it only makes sense for large service providers who are running SONET (Synchronous Optical Networking) systems, and you likely won't find it in small office, home office, or corporate office environments

## Transceivers (Media Converters)

### Overview

- A Media Converter, also known as a Transceiver, converts media from one format to another (e.g. copper to fiber or fiber to copper)

- Media Converters/Transceivers are Physical Layer (OSI Model Layer 1) devices because all they do is convert media and repeat the signal

### Communication Types

- Bidirectional (Half-Duplux) Communication

    - In Bidirectional communication, also known as Half-Duplex communication, devices must take turns to communicate

        - Only one side of the communication uses all the bandwidth at a given time

- Duplex (Full-Duplex) Communication

    - In Duplex communication, also known as Full-Duplex communication, devices are able to communicate at the same time

### Transceiver Types

- Gigabit Interface Converter (GBIC) Module

    - In routers and switches, Gigabit Interface Converter (GBIC) modules are standard, hot-pluggable gigabit ethernet transceivers that can 
    take copper or fiber as a connector

- Small Form-factor Pluggable (SFP) Module

    - In routers and switches, Small Form-factor Pluggable modules are hot-pluggable modules (meaning that they can be swapped without turning on/off the router/switch) with optical converters that are approximately half the size of GBIC modules (and sometimes called mini-GBICs because of that)

        - Speeds up to 4.2 Gbps

- Small Form-factor Pluggable Plus (SFP+) Module

    - A faster version of the SFP module

        - Speeds up to 16 Gbps

- Quad Small Form-factor Pluggable (QSFP) Module

    - A faster version of the SFP module

        - Speeds up to 40 Gbps

- Quad Small Form-factor Pluggable Plus (QSFP+) Module

    - A faster version of the SFP module

        - Speeds up to 41.2 Gbps

- Quad Small Form-factor Pluggable 28 (QSFP28) Module

    - A faster version of the SFP module

        - Speeds up to 100 Gbps

- Quad Small Form-factor Pluggable 56 (QSFP56) Module

    - A faster version of the SFP module

        - Speeds up to 200 Gbps

## Cable Distribution

### Overview

- Cable Distribution Systems are organized systems that connect a network's backbone in the main distribution frame (MDF) to the intermediate distribution frame (IDF) and finally to the end user's wall jacks

    - Cable Distribution Systems should be hierarchical in nature so that each cable run is logically placed safely, securely, and functionally inside a building

### Components of Cable Distribution Systems

- Entrance Facilities

    - Location where WAN (wide area network) connection enters a given building

    - This is a **Demarcation Point**, which is where an internet service provider's connection ends and our network begins

- Backbone Switch

    - Device that connects to everything on the network

        - Can be the only switch in a small organization

        - Can be a switch that connects to other "edge" switches in a large organization of hundreds to thousands of end users

            - Edge switchs connect to the backbone switch using a trunk line

- Main Distribution Frame (MDF)

    - A telecommunications closet which serves as the main starting point for all interior cabling

    - Typically in a commercial setting, this is where the **Entrance Facilities** and **Backbone Switch** is located

- Intermediate Distribution Frame (IDF)

    - Smaller distribution frames that branch off of the main distribution frame (for example, there might be one IDF per floor in a large office building)

    - Contains an edge switch, a patch panel, and other associated equipment to support the floor and offices nearest to it

- Cable Trays

    - Rigid structural system to securely support cables and raceways throughout a building

    - Typically located in a drop ceiling or under a raised floor

- Punchdown Blocks

    - There are 4 main types of punchdown blocks used in networking

        - 66 Block (M Block)

            - Used in older analog telephone systems and older CAT3 networks (and originally developed in the 1962)

            - Supports a 25-pair cable that would run to an MDF or IDF

        - 110 Block

            - Supports high speed data networks for CAT5 and above

            - Used for both voice and data

            - Includes the use of insulation displacement contract connectors

        - Krone Block

            - Proprietary European alternative to 110 block

            - Originally developed in the 1970s by The Krone Group (a German communication company)

        - BIX Block

            - Proprietary punchdown block available in various sizes

            - Originally developed in the 1970s by Nortel Networks (a Canadian communication company)

- Punchdown Tool

    - Used to insert cables into the blades of punchdown blocks

    - Sometimes also has a small blade to chop off excess wire after it is inserted into the blades of the punchdown block

- Patch Panel (for copper media)

    - Keeps a data center or server room organized by making it easy to move, add, or change cable distribution infrastucture

    - Best practice is to always connect wall cables into a 110 Block or the back of a patch panel, then use a patch cable to connect the patch panel to any switches

        - Connecting to a 110 Block or Patch Panel prevents wearing out the switch ports from consistent plugging and unplugging, which is beneficial because Patch Panels and 110 Blocks are much cheaper to replace compared to switches

        - Patch Panel to Switch connections with patch cables will rarely need to be plugged or unplugged

- Fiber Distribution Panels

    - Converts fiber connections from one type to another

    - Unlike Patch Panels for copper media, there are no punchdowns, only fiber connectors on either side of the panel

### Wiring a Network

- Keystone modules for networking use mini 110 Blocks on one side and a standard RJ45 connectors on the other

    - Wall cables run from a punchdown block on the back of a patch panel to the keystone module, where the other end of the cable is punched down into the backside of the keystone module

    - After wiring the patch panel to the keystone module, the keystone module is inserted into a wall plate and clicks into place, with the front-facing side of the wall plate now exposing the standard RJ45 connector to the room in which it is installed

### Testing a Network

- Fox-and-Hound Probes, also known as Toner probes, send a signal down a wire and then are able to listen for that signal at various points along the wire and emit a noise for finding breaks and other troubleshooting

        