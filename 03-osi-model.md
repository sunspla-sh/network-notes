# OSI Model

## Overview

### What is the OSI Model?

- Open Systems Interconnection (OSI) model is a standard (ISO 7498) for connecting systems in a network

- There are 7 layers in the OSI model and we can use the OSI model as a reference model while troubleshooting to categorize our problems into different layers to help develop a solution

- The 7 layers of the OSI model are listed below from top to bottom (highest to lowest layer):
    
    - Application (Layer 7)
    - Presentation (Layer 6)
    - Session (Layer 5)
    - Transport (Layer 4)
    - Network (Layer 3)
    - Datalink (Layer 2)
    - Physical (Layer 1)

- The OSI model doesn't cleanly map to the way our modern networks operate nowadays because our networks typically follow the TCP/IP model and protocols, while the OSI model attempts to describe how ALL networks operate

    - Some parts of our TCP/IP model map to and/or operate at multiple levels of the OSI model

- When we communicate data across a network, we can give it more descriptive names as it flows through the various layers of the OSI model

- The different, more specific names for data as it flows top-to-bottom (highest to lowest layer) through the OSI model are as follows:
    
    - Data (Application)
    - Data (Presentation)
    - Data (Session)
    - Segments (Transport)
    - Packets (Network)
    - Frames (Datalink)
    - Bits (Physical)


## Physical Layer (OSI Model Layer 1)

### What is the Physical Layer?

- The physical layer of the OSI model is the layer where transmission of bits (logical zeroes and ones) across the network occurs and it includes the physical and electrical network characteristics

    - These physical and electrical network characteristics are things such as copper cabling, fiber optic cabling, and the various electrical voltages (in the case of copper cabling) or photons (in the case of fiber optic cabling) that travel across them and represent bits (logical zeroes and ones)

    - If wifi (wireless networking) is used, then radio frequencies act as the physical layer instead of copper or fiber optic cabling

- Transition modulation is the changing of either voltages (in the case of copper cabling), photons (in the case of fiber optic cabling), or radio frequencies (in the case of wifi wireless networking) that represent bits (logical zeroes and ones)

- If we're using copper wire in the form of CAT5 or CAT6 cables, there are two standards in which the physical network is wired

    - TIA/EIA-568A
    - TIA/EIA-568B

- Some times we use crossover cables with different connectors on each end that flip between the two standards

- Othertimes we use straight-through and/or patch cables that use the TIA/EIA-568B standard on both sides

- Layer 1 devices view networks from a physical topology perspective

    - Bus
    - Ring
    - Star
    - Spoke-and-hub
    - Mesh
    - Hybrid (usually combo of mesh and spoke-and-hub)

### How is Communication synchronized on the Physical Layer?

- Communication can be either synchronous or asynchronous

- Asynchronous communication uses start and stop bits to indicate when the transmissions occur from the sender to the receiver

    - An example of asynchronous communication is sending a text message or leaving a voice message for your friend to listen to later

- Synchronous communication uses a reference clock (common time source) to coordinate the transmissions by both sender and receiver

    - An example of synchronous communication is a phone call with your friend, where both parties are required to be active on their devices at the same time

### How is Bandwidth utilized on the Physical Layer?

- The two main ways of utilizing bandwidth on the physical layer are broadband and baseband

- Broadband divides bandwidth into separate channels

    - An example of broadband is cable television, which is a single cable that often carries two hundred or more different channels that the user filters through to choose a single channel to watch

- Baseband uses all available frequencies on a medium (often a cable, but not always) to transmit data

    - An example of baseband is a landline phone, which uses all of the bandwidth allocated to that phoneline to make a phone call and there is no extra bandwidth available for additional calls on that same line

    - Baseband uses a reference clock to coordinate the transmisison of data from both sender and receiver at a certain time, so this is an example of synchronous communication

    - Another example of baseband is a wired home ethernet network, which uses all available bandwidth on the cable to maximize transmission speed compared to a broadband network

- Efficient usage of baseband requires several different strategies

    - Time-Division Multiplexing (TDM) has each session take a turn, using timeslots, to share the medium between all users, although this often leads to wasted timeslots

    - Statistical Time-Division Multiplexing (StatTDM) dynamically allocates timeslots on an as-needed basis, reducing the amount of wasted timeslots

    - Frequency-Division Multiplexing (FDM) divides the medium into channels based on frequencies and each session is transmitted over a different channel, and thus transforms baseband into broadband, with each channel having a fraction of the total bandwidth of the medium

### Examples of Physical Layer Devices

- Different types of media devices make up the Physical Layer

- Cables

    - Fiber Optic
    - Ethernet
    - Coaxial

- Radio Frequencies

    - Bluetooth
    - Wi-Fi
    - NFC

- Infrastructure Devices (that operate at the bit layer, without logic, and simply repeat their inputs as outputs)

    - Hubs
    - Access Points
    - Media Converters

## Datalink Layer (OSI Model Layer 2)

### What is the Datalink Layer?

- The Datalink Layer packages data (bits from the physical layer) into frames and transmits those frames on the network.

    - Additionally, the Datalink Layer also performs some error detection and correction, identifies unique network devices using MAC addresses, and provides some flow control

### What is a MAC Address?

- MAC address is short for Media Access Control address

    - Media Access Control addressing is a system of physical addressing of devices which allows them to operate on a logical topology

    - MAC addresses are unique 48-bit addresses that are assigned to Network Interface Cards (NIC) when produced by manufacturers

    - MAC addresses are always represented by 12 hexidecimal numbers (48 bits), with the first 6 numbers (24 bits) representing the manufacturer of the device and the last 6 numbers (24 bits) representing the unique number of the device

    - For example, in a MAC address of D2:51:F1:3A:34:65, the D2:51:F1 portion of the MAC address represents the vender code (the manufacturer of the device) and 3A:34:65 represents the unique number of the device produced by that manufacturer

### What is Logical Link Control?

- Logical Link Control (LLC) provides connection services and allows acknowledgement of reciept of messages

    - It is the most basic form of flow control by limiting the amount of data a sender can send at once to prevent the receiver from being overwhelmed

    - It allows a device to make a request for either less information at a time or for a replay of that information

    - It provides basic error control functions by allowing the receiver to inform the sender that a dataframe wasn't received or if it was received corrupted, which it can verify through the use of a checksum (adding up all the bits and then verifying the parity of the result)

### How is Communication synchronized on the Datalink Layer?

...

