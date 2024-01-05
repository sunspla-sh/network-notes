# Routing

## Routing Fundamentals

### Overview

- Routers are Network Layer (OSI Model Layer 3) devices forward traffic between subnets, between an internal and external network, or between two external networks

    - Each subnet or external network is its own broadcast domain

- Multilayer Switches are Datalink Layer (OSI Model Layer 2) switches that also perform routing functions on the Network Layer (OSI Model Layer 3)

### Routing Example

    BROADCAST DOMAIN ONE

      Router

          IP: 192.1.1.1/30

      Switch

          IP: 10.0.1.1

          MAC: AA:AA:AA:AA:AA:AA

      PC1 (Client)

          IP: 10.0.1.2

          MAC: AA:BB:CC:AA:BB:CC

    ----------------------------

    BROADCAST DOMAIN TWO

      Router

          IP: 192.1.1.2/30

      Switch

          IP: 10.0.2.1

          MAC: BB:BB:BB:BB:BB:BB

      PC2 (Client)

          IP: 10.0.2.2

          MAC: DD:EE:FF:DD:EE:FF



- The main steps involved in routing a message are listed below

    - PC1 attempts to send a message to PC2 by starting with an ARP request to the switch

    - PC1's message arrives at the switch and the switch does not recognize PC2's MAC address, so forwards the message out its default gateway

    - The router that has been configured as the default gateway will respond to PC1's ARP request on behalf of the destination device

    - The router from PC1's network will package up the dataframe from PC1 as an IP packet, add an IP header to the packet, and then send it to the other router from PC2's network

    - The router from PC2's network will strip off the IP header, unpackage the IP packet, and convert the message back into a dataframe by adding a MAC address for PC2

    - The router from PC2's network sends the dataframe to the switch on PC2's network

    - The switch from PC2's network sends the dataframe to PC2 using PC2's MAC address

    - The entire process occurs again in the reverse order if PC2 wants to send a response to PC1

## Routing Tables

### Overview

- Every route between two routers has a cost

### Sources of Routing Information

- There are three different sources of routing information:

    - Directly Connected Routes

        - Learned from a physical connection between two routers

    - Static Routes

        - Manually configured by an administrator

        - Default Static Route

            - 0.0.0.0/0

            - "If you don't know where to go, go here."

    - Dynamic Routes

        - Learned by exchanging information between routers

#### Directly Connected Routes

- From our previous routing example, the router in PC1's network might have a routing table that looks like the following:

|      Type    |    Network   |   Interface  |
| ------------ | ------------ | ------------ |
| Connected    | 10.0.1.0/24  | Fa 0/0       |
| Connected    | 192.1.1.0/24 | S 1/1        |

- The two devices listed in the routing table are the directly connected switch from PC1's network, represented by network 10.0.1.0/24 and interface Fa 0/0, and the directly connected router from PC2's network, represented by network 192.1.1.0/24 and interface S 1/1

    - Notice that the router in PC1's network does not know how to get to the 10.0.2.0 network that has been created by the switch from PC2's network

#### Static Routes

- Building on the previous example of directly connected routes, we can do static routing and manually configure the router from PC1's network with a default gateway, which will be the router from PC2's network

    - In that case, the routing table for router would be updated as follows:

|      Type    |    Network   |   Interface  |
| ------------ | ------------ | ------------ |
| Connected    | 10.0.1.0/24  | Fa 0/0       |
| Connected    | 192.1.1.0/24 | S 1/1        |
| Static       | 0.0.0.0/0    | S 1/1        |

- This additional row in the routing table means that anytime the router does not know a given IP address, it should send the message out port Serial 1/1, which is going to send it over to the router on PC2's network

#### Dynamic Routes

- In dynamic routing, there can be more than one path from a given source to a given destination

    - A dynamic routing protocol will negotiate the best path based on different factors:

        - Number of hops

        - Link bandwidth available

        - Other criteria depending on the specific dynamic routing protocol