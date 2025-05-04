# TCP/UDP Connections

![image](https://github.com/user-attachments/assets/b57cc232-4b6f-485a-837a-ba3d84c0bd55)

[Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) (**TCP**) and [User Datagram Protocol](https://en.wikipedia.org/wiki/User_Datagram_Protocol) (**UDP**) are both protocols used in information and data transmission on the Internet. Typically, TCP connections transmit important data, such as web pages and emails. In contrast, UDP connections transmit real-time data such as streaming video or online gaming.

**TCP** is a connection-oriented protocol that ensures that all data sent from one computer to another is received. It is like a telephone conversation where both parties remain connected until the call is terminated. If an error occurs while sending data, the receiver sends a message back so the sender can resend the missing data. This makes **TCP** reliable and slower than UDP because more time is required for transmission and error recovery.

**UDP**, on the other hand, is a connectionless protocol. It is used when speed is more important than reliability, such as for video streaming or online gaming. With **UDP**, there is no verification that the received data is complete and error-free. If an error occurs while sending data, the receiver will not receive this missing data, and no message will be sent back to resend it. Some data may be lost with UDP, but the overall transmission is faster.
