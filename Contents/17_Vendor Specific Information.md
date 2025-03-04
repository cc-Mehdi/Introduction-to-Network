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
