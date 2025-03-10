# Vendor Specific Information

[Cisco IOS](https://www.cisco.com/c/en/us/products/ios-nx-os-software/ios-technologies/index.html) is the operating system of Cisco network devices such as routers and switches. It provides features and services required to manage and operate network devices. This operating system comes in different versions and releases that vary in features, support, and performance. It offers several features required for the operation of modern networks, such as, but not limited to:

- Support for IPv6
- Quality of Service (QoS)
- Security features such as encryption and authentication
- Virtualization features such as Virtual Private LAN Service (VPLS)
- Virtual Routing and Forwarding (VRF)

Cisco IOS can be managed in several ways, depending on the network device and hardware used. The most commonly used method is the command line interface (**CLI**), which can also be managed in the graphical user interface (**GUI**). In addition, it supports various network protocols and services required for network operations. These include:

![image](https://github.com/user-attachments/assets/52d29e67-c56e-4c80-9905-7d37d952667d)

In Cisco IOS, different types of passwords are used for various purposes, for example:

![image](https://github.com/user-attachments/assets/86581391-0c68-4aa6-990a-2778bd511ac0)

We highly recommend going through the provided external resources to understand the encryption mechanics of Cisco IOS and how those are used.

The Cisco IOS devices can be configured for SSH or Telnet. So it can be accessed remotely. We can determine from the response we receive that it is indeed a Cisco IOS, as it responds with the **User Access Verification** message.

![image](https://github.com/user-attachments/assets/3e7049b3-944a-414e-8ef2-6069fbfdf69b)

## VLANs

![image](https://github.com/user-attachments/assets/29415ace-638f-4103-afaf-cdb5aa7ea698)

Imagine this scenario: A startup called XQ hired a network administrator to create a network for their single-office company, and due to budget limitations, they can only afford one switch and router. The sysadmin of XQ stated that in addition to hosting the web and database servers in the network, staff from different departments will be using it. As a seasoned network security specialist, the network administrator immediately thought about the security attacks that an insider can perform, especially ones abusing broadcast traffic, such as **broadcast storms**. Therefore, to tackle this problem, the network administrator decided to logically segment the network with **Virtual Local Area Networks** (**VLANS**), conceptually breaking down one switch into smaller mini-switches.

A **VLAN** is a logical grouping of network endpoints connected to defined ports on a switch, allowing the segmentation of networks by creating logical broadcast domains that can span multiple physical LAN segments. With **VLANs**, network administrators can segment networks based on factors such as team, function, department, or application, without worrying about the physical location of endpoints and users. A broadcast packet sent over one **VLAN** does not reach any other endpoint that is a member of another **VLAN**. Because each **VLAN** is regarded as a broadcast domain, it needs to have its own subnet; for example, the network administrator contracted by XQ can segment the network by departments:

![image](https://github.com/user-attachments/assets/facfc3ee-ebd0-462c-a7ac-8e04944addfd)

A myriad of benefits is attained when using **VLANs**, including:

- **Better Organization**: Network administrators can group endpoints based on any common attribute they share.
- **Increased Security**: Network segmentation disallows unauthorized members from sniffing network packets in other **VLANs**.
- **Simplified Administration**: Network administrators do not have to worry about the physical locations of an endpoint.
- **Increased Performance**: With reduced broadcast traffic for all endpoints, more bandwidth is made available for use by the network.

Cisco switches provide the **VLAN** IDs/numbers 1-4094 (**0** and **4095** are reserved IDs and cannot be used); IDs 1-1005 (**VLAN 1** is known as the **default VLAN** and cannot/should not be altered nor deleted) are known as **normal-range VLANs**, with IDs 1002-1005 being reserved for **Token Ring** and **Fiber Distributed Data Interface** (**FDDI**) **VLANs**, while IDs 1006-4094 are known as **extended-range VLANs**. By default, any customization applied for normal-range VLANs is saved in the VLAN database (the vlan.dat file), in contrast to extended-range VLANs, which do not have their customizations saved. VLANs 2-1001 stored in vlan.dat can have parameters including name, type, state, and maximum transmission unit (MTU).


## VLAN Memberships

Network administrators can assign the ports of a switch to **VLANs** either statically or dynamically. Static **VLAN** assignment, which is the simplest and most common method, involves assigning each port to a **VLAN** manually using the switch's network operating system; this must be done for all switches separately (it is essential to keep in mind that endpoints connecting to these ports are unaware of the existence of **VLANs**). In contrast, dynamic VLAN assignment automatically determines an endpoint's **VLAN** membership based on MAC addresses or protocols. The system administrator can register the MAC addresses in a centralized VLAN management service/database, such as the **VLAN** Membership Policy Server (VMPS) service, and then the switch queries the database of VMPS to determine the VLAN of the endpoint with that specific MAC address. Regardless of their flexibility and mobility, dynamic VLANs increase administrative overhead.

Security-wise, static VLANs are the more secure option because a port will forever be tied to a specific VLAN ID, unless changed manually afterward. For dynamic VLANs, an attacker could potentially utilize tools such as [macchanger](https://github.com/alobbs/macchanger) to spoof the MAC address of legitimate endpoints and attain membership of their VLANs, therefore sniffing all network traffic sent through them.

## Access and Trunk Ports

Any port on a VLAN-enabled switch must be either an access port or a trunk port. Access ports belong to and can carry the traffic of only one VLAN (or in some cases two, with the second being for voice traffic); any traffic arriving on an access port is assumed to belong to the VLAN the port was assigned. On the other hand, trunk ports can carry multiple VLANs at the same time; trunk links connect two trunk ports on two switches (or a switch and router) to allow information from multiple VLANs to be carried out across switches.

## VLAN Identification

Standard 802.3 Ethernet frames do not contain VLAN information; therefore, switches and other VLAN-enabled devices need a mechanism to keep track of all the VLAN information associated with a packet while traversing VLAN-enabled devices. Two main trunking methods are utilized to achieve this, ISL and IEEE 802.1Q.

### Inter-Switch Link (ISL)

Inter-Switch Link (ISL) is a Cisco-proprietary protocol used for trunking between VLAN-enabled devices. Although ISL is one of the first trunking methods (predating 802.1Q), it is deprecated and not as widely used in modern Cisco switches (and routers). Instead, most only support the widely adopted 802.1Q. ISL encapsulated the entire Ethernet frame, including the original Ethernet header and the VLAN tag, adding its 26-byte header and 4-byte trailer.

### IEEE 802.1Q

To ensure interoperability of VLAN technologies from the various network-equipments vendors, the Institute of Electrical and Electronics Engineers (IEEE) developed the [802.1Q](https://ieeexplore.ieee.org/document/10004498) specification in 1998. The IEEE 802 committee had to change the 802.3 Ethernet frame format by adding a pair of 2-byte fields, TPID and TCI (which consists of three subfields, PCP, DEI, and VID), resulting in a VLAN-compliant 802.1Q Ethernet frame.

![image](https://github.com/user-attachments/assets/a00a91ca-2ab1-42d8-ac5f-ed7b8d186ffb)

Tag protocol identifier (TPID) is a 16-bit field always set to 0x8100 to identify the Ethernet frame as an 802.1Q-tagged frame. Tag Control Information (TCI) is a 16-bit field containing Priority code point (PCP), Drop eligible indicator (DEI) (previously known as Canonical format indicator (CFI)), and VLAN identifier (VID). The main field concerning VLANs is VID, occupying the low-order 12-bits of TCI. Since it is 12 bits, it allows 2^12 - 2 = 4096 (remember, 0 and 4095 are reserved) VLAN IDs. Therefore, an 802.1Q-tagged frame can contain information for 4094 VLANs; the practice of inserting multiple 802.1Q tags within a single packet is known as Double Tagging, introduced by [802.1ad](https://standards.ieee.org/ieee/802.1Q/10323/). VLAN tagging is the process of inserting VLAN information into an 802.1Q Ethernet header, while VLAN untagging is the process of removing the VLAN information from an 802.1Q-tagged Ethernet frame and forwarding the packet to the destined ports.

## VLAN-Capable NICs

Some **network interface cards** (**NICs**) attached to computers/servers support **VLAN tagging**. Let us see how we can assign a **VLAN** ID to a **NIC** using Linux and Windows.

### Assigning NICs a VLAN in Linux

In Linux, creating a **VLAN** is done by creating an interface on top of another, called a **parent** interface. This **VLAN** interface will tag packets with the assigned **VLAN** ID while returning packets will be untagged.

To assign a network adapter a **VLAN** in Linux, many tools can be used, such as [ip](https://man7.org/linux/man-pages/man8/ip.8.html), [nmcli](https://linux.die.net/man/1/nmcli), and [vconfig](https://linux.die.net/man/8/vconfig) (deprecated). However, first, we need to ensure that the Kernel has the [802.1Q](https://elixir.bootlin.com/linux/v6.4.7/source/net/8021q/vlan.c) module loaded:
