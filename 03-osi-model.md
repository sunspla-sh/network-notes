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