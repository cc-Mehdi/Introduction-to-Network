# MAC Addresses

![image](https://github.com/user-attachments/assets/32196890-25f6-4436-b21f-eadcd81cd7b7)

Each host in a network has its own **48**-bit (**6 octets**) **Media Access Control** (**MAC**) address, represented in hexadecimal format. **MAC** is the **physical address** for our network interfaces. There are several different standards for the MAC address:

- Ethernet (IEEE 802.3)
- Bluetooth (IEEE 802.15)
- WLAN (IEEE 802.11)

This is because the **MAC** address addresses the physical connection (network card, Bluetooth, or WLAN adapter) of a host. Each network card has its individual MAC address, which is configured once on the manufacturer's hardware side but can always be changed, at least temporarily.

Let's have a look at an example of such a MAC address:

MAC address:

- **DE:AD:BE:EF:13:37**
- **DE-AD-BE-EF-13-37**
- **DEAD.BEEF.1337**

![image](https://github.com/user-attachments/assets/528a32b8-1288-46a5-bc7d-a15860fe8cdd)

When an IP packet is delivered, it must be addressed on **layer 2** to the destination host's physical address or to the router / NAT, which is responsible for routing. Each packet has a **sender address** and a **destination address**.

The MAC address consists of a total of **6 bytes**. The first half (**3 bytes / 24 bit**) is the so-called **Organization Unique Identifier** (**OUI**) defined by the **Institute of Electrical and Electronics Engineers** (**IEEE**) for the respective manufacturers.

![image](https://github.com/user-attachments/assets/7977ec4d-ff60-4e31-b03c-1ee1da97e1b3)

The last half of the MAC address is called the **Individual Address Part** or **Network Interface Controller** (**NIC**), which the manufacturers assign. The manufacturer sets this bit sequence only once and thus ensures that the complete address is unique.

![image](https://github.com/user-attachments/assets/99d63759-5c15-4b58-8f23-f7129d6a8c85)

If a host with the IP target address is located in the same subnet, the delivery is made directly to the target computer's physical address. However, if this host belongs to a different subnet, the Ethernet frame is addressed to the **MAC address** of the responsible router (**default gateway**). If the Ethernet frame's destination address matches its own **layer 2 address**, the router will forward the frame to the higher layers. **Address Resolution Protocol** (**ARP**) is used in IPv4 to determine the MAC addresses associated with the IP addresses.

As with IPv4 addresses, there are also certain reserved areas for the MAC address. These include, for example, the local range for the MAC.

![image](https://github.com/user-attachments/assets/a03ea1af-7bb4-415f-831c-39bcd9605b53)

Furthermore, the last two bits in the first octet can play another essential role. The last bit can have two states, 0 and 1, as we already know. The last bit identifies the MAC address as **Unicast** (**0**) or **Multicast** (**1**). With **unicast**, it means that the packet sent will reach only one specific host.

### MAC Unicast

![image](https://github.com/user-attachments/assets/cff5b6e2-fbd3-42b1-9f0b-e52a8e1e2d52)

With **multicast**, the packet is sent only once to all hosts on the local network, which then decides whether or not to accept the packet based on their configuration. The **multicast** address is a unique address, just like the **broadcast** address, which has fixed octet values. **Broadcast** in a network represents a broadcasted call, where data packets are transmitted simultaneously from one point to all members of a network. It is mainly used if the address of the receiver of the packet is not yet known. An example is the **ARP** (**for MAC addresses**) and **DHCP** (**for IPv4 addresses**) protocols.

The defined values of each octet are marked **green**.

### MAC Multicast

![image](https://github.com/user-attachments/assets/c0525292-e6e0-4385-803b-ce551aa78189)

### MAC Broadcast

![image](https://github.com/user-attachments/assets/92b918d3-3268-4701-af08-4ad9ec97e077)

The second last bit in the first octet identifies whether it is a **global OUI**, defined by the IEEE, or a **locally administrated** MAC address.

### Global OUI

![image](https://github.com/user-attachments/assets/559c07ef-1e8c-421f-a281-e1a6256407dd)

### Locally Administrated

![image](https://github.com/user-attachments/assets/d14cb089-d689-47df-9b87-868f21dddce1)

## Address Resolution Protocol

MAC addresses can be changed/manipulated or spoofed, and as such, they should not be relied upon as a sole means of security or identification. Network administrators should implement additional security measures, such as network segmentation and strong authentication protocols, to protect against potential attacks.

There exist several attack vectors that can potentially be exploited through the use of MAC addresses:

- **MAC spoofing:** This involves altering the MAC address of a device to match that of another device, typically to gain unauthorized access to a network.
- **MAC flooding:** This involves sending many packets with different MAC addresses to a network switch, causing it to reach its MAC address table capacity and effectively preventing it from functioning correctly.
- **MAC address filtering**: Some networks may be configured only to allow access to devices with specific MAC addresses that we could potentially exploit by attempting to gain access to the network using a spoofed MAC address.

## Address Resolution Protocol

[Address Resolution Protocol](https://en.wikipedia.org/wiki/Address_Resolution_Protocol) (**ARP**) is a network protocol. It is an important part of the network communication used to resolve a network layer (layer 3) IP address to a link layer (layer 2) MAC address. It maps a host's IP address to its corresponding MAC address to facilitate communication between devices on a [Local Area Network](https://en.wikipedia.org/wiki/Local_area_network) (**LAN**). When a device on a LAN wants to communicate with another device, it sends a broadcast message containing the destination IP address and its own MAC address. The device with the matching IP address responds with its own MAC address, and the two devices can then communicate directly using their MAC addresses. This process is known as ARP resolution.

ARP is an important part of the network communication process because it allows devices to send and receive data using MAC addresses rather than IP addresses, which can be more efficient. Two types of request messages can be used:

### ARP Request

When a device wants to communicate with another device on a LAN, it sends an ARP request to resolve the destination device's IP address to its MAC address. The request is broadcast to all devices on the LAN and contains the IP address of the destination device. The device with the matching IP address responds with its MAC address.

### ARP Reply

When a device receives an ARP request, it sends an ARP reply to the requesting device with its MAC address. The reply message contains the IP and MAC addresses of both the requesting and the responding devices.

### Tshark Capture of ARP Requests

![image](https://github.com/user-attachments/assets/0da980e3-2ba3-40bb-bd02-c9330aa6b0dc)

The "**who has**" message in the first and third lines indicates that a device is requesting the MAC address for the specified IP address, while the second and fourth lines show the ARP reply with the MAC address of the destination device.

However, it is also vulnerable to attacks, such as [ARP Spoofing](https://en.wikipedia.org/wiki/ARP_spoofing), which can be used to intercept or manipulate traffic on the network. However, to protect against such attacks, it is important to implement security measures such as firewalls and intrusion detection systems.

**ARP spoofing**, also known as **ARP cache poisoning** or **ARP poison routing**, is an attack that can be done using tools like [Ettercap](https://github.com/Ettercap/ettercap) or [Cain](https://github.com/xchwarze/Cain) & Abel in which we send falsified ARP messages over a LAN. The goal is to associate our MAC address with the IP address of a legitimate device on the company's network, effectively allowing us to intercept traffic intended for the legitimate device. For example, this could look like the following:

![image](https://github.com/user-attachments/assets/242b6178-5ecd-405b-9994-b55bcad7a5ae)
