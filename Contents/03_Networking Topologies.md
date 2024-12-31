# Networking Topologies
![image](https://github.com/user-attachments/assets/b7d81315-bee8-453b-869c-2d5a377113c6)


## What's Networking Topologies ?

A network topology is a typical arrangement and physical or logical connection of devices in a network. Computers are hosts, such as clients and servers, that actively use the network. They also include network components such as switches, bridges, and routers, which we will discuss in more detail in later sections, which have a distribution function and ensure that all network hosts can establish a logical connection with each other. The network topology determines the components to be used and the access methods to the transmission media.
---
Physical topology and logical topology are two important concepts in computer networks that refer to how devices are connected and how data is transmitted within a network:
### Physical Topology
Physical topology refers to the physical arrangement and connection of devices in a network, including:
- Cabling plan: The routes that cables take to connect devices to each other.
- Node positions: The exact locations of devices (such as computers, servers, routers) in the network.
- Connections: How devices are connected to the cables and network equipment.
Simply put, physical topology is the visible map of the actual connections of devices. Examples of physical topology include:
- Star topology: Devices are connected to a central switch or hub.
- Ring topology: Each device is connected to the next, forming a ring.
- Bus topology: All devices are connected through a shared cable.
### Logical Topology
Logical topology refers to how data is transmitted between devices in a network, which may differ from the physical topology. It includes:
- How signals move on the transmission medium: For example, the paths data takes to be sent and received.
- Data transfer mechanisms: The pattern and sequence by which data is sent from one device to another.

### **For example:**
- In Ethernet networks, the physical topology might be a star, but the logical topology may operate like a bus because data is logically broadcast to all devices.
- In a wireless network, there might be no physical topology, but the logical topology defines how devices communicate and exchange data.

### Key Difference
- Physical topology: The actual structure and hardware arrangement of the network.
- Logical topology: The functional operation and data transmission within the network.
---
We can divide the entire network topology area into three areas:
1. Connections :
![image](https://github.com/user-attachments/assets/bd047e21-d28f-4208-9bf9-4946e330d9f1)
2. Nodes - Network Interface Controller (NICs) :
![image](https://github.com/user-attachments/assets/5e79aabf-d44d-471c-be8a-aa89a190697f)
Network nodes are the transmission medium's connection points to transmitters and receivers of electrical, optical, or radio signals in the medium. A node may be connected to a computer, but certain types may have only one microcontroller on a node or may have no programmable device at all.
3. Classifications

We can imagine a topology as a virtual form or structure of a network. This form does not necessarily correspond to the actual physical arrangement of the devices in the network. Therefore these topologies can be either physical or logical. For example, the computers on a LAN may be arranged in a circle in a bedroom, but it is very unlikely to have an actual ring topology.
---
Network topologies are divided into the following eight basic types:

![image](https://github.com/user-attachments/assets/b7dea406-694a-4539-8fd2-88020138a10c)

More complex networks can be built as hybrids of two or more of the basic topologies mentioned above.
---
## Point-to-Point
The simplest network topology with a dedicated connection between two hosts is the point-to-point topology. In this topology, a direct and straightforward physical link exists only between two hosts. These two devices can use these connections for mutual communication.

Point-to-point topologies are the basic model of traditional telephony and must not be confused with P2P (Peer-to-Peer architecture).

![image](https://github.com/user-attachments/assets/d1ac750c-cf54-4bb1-9b1c-109aac3a7216)

## Bus
All hosts are connected via a transmission medium in the bus topology. Every host has access to the transmission medium and the signals that are transmitted over it. There is no central network component that controls the processes on it. The transmission medium for this can be, for example, a coaxial cable.

Since the medium is shared with all the others, only one host can send, and all the others can only receive and evaluate the data and see whether it is intended for itself.

![image](https://github.com/user-attachments/assets/ce0efd49-3620-4aea-bdb5-64c19aa7bc2a)

## Star
The star topology is a network component that maintains a connection to all hosts. Each host is connected to the central network component via a separate link. This is usually a router, a hub, or a switch. These handle the forwarding function for the data packets. To do this, the data packets are received and forwarded to the destination. The data traffic on the central network component can be very high since all data and connections go through it.

![image](https://github.com/user-attachments/assets/fcc75627-21e7-4420-8a4c-d15bc137440e)

## Ring

The physical ring topology is such that each host or node is connected to the ring with two cables:

- One for the incoming signals and
- the another for the outgoing ones.

This means that one cable arrives at each host and one cable leaves. The ring topology typically does not require an active network component. The control and access to the transmission medium are regulated by a protocol to which all stations adhere.

A logical ring topology is based on a physical star topology, where a distributor at the node simulates the ring by forwarding from one port to the next.

The information is transmitted in a predetermined transmission direction. Typically, the transmission medium is accessed sequentially from station to station using a retrieval system from the central station or a token. A token is a bit pattern that continually passes through a ring network in one direction, which works according to the claim token process.

![image](https://github.com/user-attachments/assets/9ec76d15-4057-4d76-b55c-8fd6dc35606f)
