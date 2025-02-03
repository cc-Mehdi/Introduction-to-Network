# Common Protocols

Internet protocols are standardized rules and guidelines defined in RFCs that specify how devices on a network should communicate with each other. They ensure that devices on a network can exchange information consistently and reliably, regardless of the hardware and software used. For devices to communicate on a network, they need to be connected through a communication channel, such as a wired or wireless connection. The devices then exchange information using a set of standardized protocols that define the format and structure of the data being transmitted. The two main types of connections used on networks are [Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) (**TCP**) and [User Datagram Protocol](https://en.wikipedia.org/wiki/User_Datagram_Protocol) (**UDP**).

We need to deal with and know the different and most used protocols. As we have already learned, these protocols are the basis of all communication between our devices and computers in the networks. We have compiled below many of these protocols that we will be dealing with throughout the modules. The better we understand them, the more effectively we can work with them.

## Transmission Control Protocol

**TCP** is a **connection-oriented** protocol that establishes a virtual connection between two devices before transmitting data by using a [Three-Way-Handshake](https://en.wikipedia.org/wiki/Transmission_Control_Protocol#Connection_establishment). This connection is maintained until the data transfer is complete, and the devices can continue to send data back and forth as long as the connection is active.

For example, When we enter a URL into our web browser, the browser sends an HTTP request to the server hosting the website using **TCP**. The server responds by sending the HTML code for the website back to the browser using **TCP**. The browser then uses this code to render the website on our screen. This process relies on a **TCP** connection being established between the browser and the web server and maintained until the data transfer is complete. As a result, **TCP** is reliable but slower than UDP because it requires additional overhead for establishing and maintaining the connection.

![image](https://github.com/user-attachments/assets/c385dea1-9fa9-4088-a413-8d5c2a8a8c23)
![image](https://github.com/user-attachments/assets/d446b470-fad1-4527-9a6d-02f75f15f550)
![image](https://github.com/user-attachments/assets/aa929886-3883-4efb-93d3-94a9cd72d4e3)

## User Datagram Protocol

On the other hand, **UDP** is a **connectionless** protocol, which means it does not establish a virtual connection before transmitting data. Instead, it sends the data packets to the destination without checking to see if they were received.

For example, when we stream or watch a video on a platform like YouTube, the video data is transmitted to our device using **UDP**. This is because the video can tolerate some data loss, and the transmission speed is more important than the reliability. If a few packets of video data are lost along the way, it will not significantly impact the overall quality of the video. This makes **UDP** faster than TCP but less reliable because there is no guarantee that the packets will reach their destination.

![image](https://github.com/user-attachments/assets/95e90b22-b861-4681-9c37-050e9ed538c1)
![image](https://github.com/user-attachments/assets/ebb968a6-4f4a-4b74-a1fe-5940b2bb38fb)

### ICMP

[Internet Control Message Protocol](https://en.wikipedia.org/wiki/Internet_Control_Message_Protocol) (**ICMP**) is a protocol used by devices to communicate with each other on the Internet for various purposes, including error reporting and status information. It sends requests and messages between devices, which can be used to report errors or provide status information.

### ICMP Requests

A request is a message sent by one device to another to request information or perform a specific action. An example of a request in ICMP is the ping request, which tests the connectivity between two devices. When one device sends a **ping** request to another, the second device responds with a **ping reply** message.

### ICMP Messages

A message in ICMP can be either a request or a reply. In addition to ping requests and responses, ICMP supports other types of messages, such as error messages, **destination unreachable**, and **time exceeded** messages. These messages are used to communicate various types of information and errors between devices on the network.

For example, if a device tries to send a packet to another device and the packet cannot be delivered, the device can use ICMP to send an error message back to the sender. ICMP has two different versions:

**ICMPv4**: For IPv4 only
**ICMPv6**: For IPv6 only

ICMPv4 is the original version of **ICMP**, developed for use with IPv4. It is still widely used and is the most common version of ICMP. On the other hand, ICMPv6 was developed for IPv6. It includes additional functionality and is designed to address some of the limitations of ICMPv4.

![image](https://github.com/user-attachments/assets/5713ad92-7184-4a70-b90b-c9a1402d3880)

Another crucial part of ICMP for us is the [Time-To-Live](https://en.wikipedia.org/wiki/Time_to_live) (**TTL**) field in the ICMP packet header that limits the packet's lifetime as it travels through the network. It prevents packets from circulating indefinitely on the network in the event of routing loops. Each time a packet passes through a router, the router decrements the **TTL value by 1**. When the TTL value reaches **0**, the router discards the packet and sends an ICMP **Time Exceeded** message back to the sender.

We can also use **TTL** to determine the number of hops a packet has taken and the approximate distance to the destination. For example, if a packet has a **TTL** of 10 and takes 5 hops to reach its destination, it can be inferred that the destination is approximately 5 hops away. For example, if we see a ping with the **TTL** value of **122**, it could mean that we are dealing with a Windows system (**TTL 128** by default) that is 6 hops away.

However, it is also possible to guess the operating system based on the default **TTL** value used by the device. Each operating system typically has a default **TTL** value when sending packets. This value is set in the packet's header and is decremented by 1 each time the packet passes through a router. Therefore, examining a device's default **TTL** value makes it possible to infer which operating system the device is using. For example: Windows systems (**2000/XP/2003/Vista/10**) typically have a default **TTL** value of 128, while macOS and Linux systems typically have a default **TTL** value of 64 and Solaris' default **TTL** value of 255. However, it is important to note that the user can change these values, so they should be independent of a definitive way to determine a device's operating system.

### VoIP

[Voice over Internet Protocol](https://www.fcc.gov/general/voice-over-internet-protocol-voip) (**VoIP**) is a method of transmitting voice and multimedia communications. For example, it allows us to make phone calls using a broadband internet connection instead of a traditional phone line, like Skype, Whatsapp, Google Hangouts, Slack, Zoom, and others.

The most common VoIP ports are **TCP/5060** and **TCP/5061**, which are used for the [Session Initiation Protocol](https://en.wikipedia.org/wiki/Session_Initiation_Protocol) (SIP). However, the port TCP/1720 may also be used by some VoIP systems for the [H.323 protocol](https://en.wikipedia.org/wiki/H.323), a set of standards for multimedia communication over packet-based networks. Still, SIP is more widely used than H.323 in VoIP systems.

![image](https://github.com/user-attachments/assets/7718a4c7-5ed4-4b83-a7c9-6b5fa263a9dd)

### Information Disclosure

However, SIP allows us to enumerate existing users for potential attacks. This can be done for various purposes, such as determining a user's availability, finding out information about the user's capabilities or services, or performing brute-force attacks on user accounts later on.

One of the possible ways to enumerate users is the SIP **OPTIONS** request. It is a method used to request information about the capabilities of a SIP server or user agents, such as the types of media it supports, the codecs it can decode, and other details. The **OPTIONS** request can probe a SIP server or user agent for information or test its connectivity and availability.

During our analysis, it is possible to discover a **SEPxxxx.cnf** file, where **xxxx** is a unique identifier, is a configuration file used by Cisco Unified Communications Manager, formerly known as Cisco CallManager, to define the settings and parameters for a Cisco Unified IP Phone. The file specifies the phone model, firmware version, network settings, and other details.
