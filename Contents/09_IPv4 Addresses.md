# IP Addresses

![image](https://github.com/user-attachments/assets/8f02fbc9-f541-4503-95c5-15f80290e7fe)

Each host in the network located can be identified by the so-called **Media Access Control** address (**MAC**). This would allow data exchange within this one network. If the remote host is located in another network, knowledge of the **MAC** address is not enough to establish a connection. Addressing on the Internet is done via the **IPv4** and/or **IPv6** address, which is made up of the **network address** and the **host address**.

It does not matter whether it is a smaller network, such as a home computer network, or the entire Internet. The IP address ensures the delivery of data to the correct receiver. We can imagine the representation of **MAC** and **IPv4** / **IPv6** addresses as follows:

- **IPv4** / **IPv6** - describes the unique postal address and district of the receiver's building.
- **MAC** - describes the exact floor and apartment of the receiver.

It is possible for a single IP address to address multiple receivers (broadcasting) or for a device to respond to multiple IP addresses. However, it must be ensured that each IP address is assigned only once within the network.


## IPv4 Structure

The most common method of assigning IP addresses is **IPv4**, which consists of a **32**-bit binary number combined into **4 bytes** consisting of **8**-bit groups (**octets**) ranging from **0-255**. These are converted into more easily readable decimal numbers, separated by dots and represented as dotted-decimal notation.

Thus an IPv4 address can look like this:

![image](https://github.com/user-attachments/assets/334ea9cf-20b4-4607-93d0-9c6d4e8c0b4f)

Each network interface (network cards, network printers, or routers) is assigned a **unique** IP address.


The **IPv4** format allows 4,294,967,296 unique addresses. The IP address is divided into a **host part** and a **network part**. The **router** assigns the **host part** of the IP address at home or by an administrator. The respective **network administrator** assigns the **network part**. On the Internet, this is [IANA (Internet Assigned Numbers Authority)](https://www.iana.org/), which allocates and manages the unique IPs.


---
## More Information

![image](https://github.com/user-attachments/assets/d5addb2e-2af9-4fde-a069-16b1f43bc24e)
![image](https://github.com/user-attachments/assets/ec4b8467-1470-447d-a679-11ed75f212e0)

