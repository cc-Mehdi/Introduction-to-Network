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

Imagine this scenario: A startup called XQ hired a network administrator to create a network for their single-office company, and due to budget limitations, they can only afford one switch and router. The sysadmin of XQ stated that in addition to hosting the web and database servers in the network, staff from different departments will be using it. As a seasoned network security specialist, the network administrator immediately thought about the security attacks that an insider can perform, especially ones abusing broadcast traffic, such as **broadcast storms**. Therefore, to tackle this problem, the network administrator decided to logically segment the network with **Virtual Local Area Networks** (**VLANS**), conceptually breaking down one switch into smaller mini-switches.
