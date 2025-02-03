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
