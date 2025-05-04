# TCP/UDP Connections

![image](https://github.com/user-attachments/assets/b57cc232-4b6f-485a-837a-ba3d84c0bd55)

[Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) (**TCP**) and [User Datagram Protocol](https://en.wikipedia.org/wiki/User_Datagram_Protocol) (**UDP**) are both protocols used in information and data transmission on the Internet. Typically, TCP connections transmit important data, such as web pages and emails. In contrast, UDP connections transmit real-time data such as streaming video or online gaming.

**TCP** is a connection-oriented protocol that ensures that all data sent from one computer to another is received. It is like a telephone conversation where both parties remain connected until the call is terminated. If an error occurs while sending data, the receiver sends a message back so the sender can resend the missing data. This makes **TCP** reliable and slower than UDP because more time is required for transmission and error recovery.

**UDP**, on the other hand, is a connectionless protocol. It is used when speed is more important than reliability, such as for video streaming or online gaming. With **UDP**, there is no verification that the received data is complete and error-free. If an error occurs while sending data, the receiver will not receive this missing data, and no message will be sent back to resend it. Some data may be lost with UDP, but the overall transmission is faster.

## IP Packet

![image](https://github.com/user-attachments/assets/c33d646e-60ef-45f0-be20-11caddee5bdb)

An [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol) (**IP**) packet is the data area used by the network layer of the [Open Systems Interconnection](https://en.wikipedia.org/wiki/OSI_model) (**OSI**) model to transmit data from one computer to another. It consists of a header and the payload, the actual payload data.

We can also think of the IP packet as a letter sent in an envelope. The envelope contains the header, which includes information on the sender and the recipient, as well as instructions for routing the letter, i.e., via which post offices the letter should be sent. The letter itself is the payload, the actual payload data.

### IP header

The header of an IP packet contains several fields that have important information.

![image](https://github.com/user-attachments/assets/709139a2-965e-46e7-8a20-00cf92fe32ec)

We may see a computer with multiple IP addresses in different networks. Here we should pay attention to the **IP ID** field. It is used to identify fragments of an IP packet when fragmented into smaller parts. It is a **16-bit** field with a unique number ranging from **0-65535**.

If a computer has multiple IP addresses, the **IP ID** field will be different for each packet sent from the computer but very similar. In TCPdump, the network traffic might look something like this:

![image](https://github.com/user-attachments/assets/b7ade117-89f2-428d-adc6-22e45ceb4fe0)

### IP Record-Route Field

The **Record-Route field** in the IP header also records the route to a destination device. When the destination device sends back the **ICMP Echo Reply** packet, the IP addresses of all devices that pass through the packet are listed in the **Record-Route field** of the IP header. This happens when we use the following command, for example:

![image](https://github.com/user-attachments/assets/11f25e9b-fb86-4a8d-a9ba-7d691da17107)

The output indicates that a ping request was sent and a response was received from the destination device and also shows the Record-Route field in the IP header of the ICMP Echo Request packet. The Record Route field contains the IP addresses of all devices that passed through the ICMP Echo Request packet on the way to the destination device. In this case, the Record-Route field contains the IP addresses:

![image](https://github.com/user-attachments/assets/507d90ed-dbef-452e-922c-5d8f64229069)
