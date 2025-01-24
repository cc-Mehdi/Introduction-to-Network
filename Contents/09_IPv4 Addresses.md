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


The **IPv4** format allows 4,294,967,296 unique addresses. The IP address is divided into a **host part** and a **network part**. The **router** assigns the **host part** of the IP address at home or by an administrator. The respective **network administrator** assigns the **network part**. On the Internet, this is **IANA** [(Internet Assigned Numbers Authority)](https://www.iana.org/), which allocates and manages the unique IPs.

In the past, further classification took place here. The IP network blocks were divided into **classes A - E**. The different classes differed in the host and network shares' respective lengths.

![image](https://github.com/user-attachments/assets/dde16279-abf2-4a23-8346-024cd3697967)

## Subnet Mask

A further separation of these classes into small networks is done with the help of **subnetting**. This separation is done using the **netmasks**, which is as long as an IPv4 address. As with classes, it describes which bit positions within the IP address act as **network part** or **host part**.

![image](https://github.com/user-attachments/assets/3bd8ab9b-0390-45a1-9c78-3752a2fd13e4)

## Network and Gateway Addresses

The **two** additional **IPs** added in the **IPs column** are reserved for the so-called **network address** and the **broadcast address**. Another important role plays the **default gateway**, which is the name for the IPv4 address of the **router** that couples networks and systems with different protocols and manages addresses and transmission methods. It is common for the **default gateway** to be assigned the first or last assignable IPv4 address in a subnet. This is not a technical requirement, but has become a de-facto standard in network environments of all sizes.

![image](https://github.com/user-attachments/assets/334d9561-5166-478b-8781-dc6a4d8d1770)

## Broadcast Address

The **broadcast** IP address's task is to connect all devices in a network with each other. **Broadcast** in a network is a message that is transmitted to all participants of a network and does not require any response. In this way, a host sends a data packet to all other participants of the network simultaneously and, in doing so, communicates its **IP address**, which the receivers can use to contact it. This is the **last IPv4** address that is used for the **broadcast**.

![image](https://github.com/user-attachments/assets/5d0bd1d0-1668-498c-ab2a-5b184df72006)

## Binary system

The binary system is a number system that uses only two different states that are represented into two numbers (**0** and **1**) opposite to the decimal-system (0 to 9).

An IPv4 address is divided into 4 octets, as we have already seen. Each **octet** consists of **8 bits**. Each position of a bit in an octet has a specific decimal value. Let's take the following IPv4 address as an example:

- IPv4 Address: **192.168.10.39**

Here is an example of how the **first octet** looks like:

### 1st Octet - Value: 192

![image](https://github.com/user-attachments/assets/eeb5b750-49e5-4c6c-aaee-2dfb9dce7bd4)

If we calculate the sum of all these values for each octet where the bit is set to 1, we get the sum:

![image](https://github.com/user-attachments/assets/a00ca544-6c45-4775-9fec-8a03162df9c4)

The entire representation from binary to decimal would look like this:

### IPv4 - Binary Notation

![image](https://github.com/user-attachments/assets/327a9ae7-d3d4-4888-a592-af692d0b15f3)

- IPv4 Address: **192.168.10.39**

This addition takes place for each octet, which results in a decimal representation of the **IPv4 address**. The subnet mask is calculated in the same way.

### IPv4 - Decimal to Binary

![image](https://github.com/user-attachments/assets/9df5dfcb-7052-4ff6-b4a2-ecd6dbfc3fd5)

### Subnet Mask

![image](https://github.com/user-attachments/assets/0ba343eb-b1c3-4e7e-aa61-9c1bd3ffca4a)

- IPv4 Address: **192.168.10.39**
- Subnet mask: **255.255.255.0**

### CIDR

**Classless Inter-Domain Routing** (**CIDR**) is a method of representation and replaces the fixed assignment between IPv4 address and network classes (A, B, C, D, E). he division is based on the subnet mask or the so-called **CIDR suffix**, which allows the bitwise division of the IPv4 address space and thus into **subnets** of any size. he **CIDR suffix** indicates how many bits from the beginning of the IPv4 address belong to the network. It is a notation that represents the **subnet mask** by specifying the number of **1**-bits in the subnet mask.

Let us stick to the following IPv4 address and subnet mask as an example:

- IPv4 Address: **192.168.10.39**
- Subnet mask: **255.255.255.0**

Now the whole representation of the IPv4 address and the subnet mask would look like this:

- CIDR: **192.168.10.39/24**

The CIDR suffix is, therefore, the sum of all ones in the subnet mask.

![image](https://github.com/user-attachments/assets/892b9a3e-8b80-43d9-9276-d605acf799b1)

**(you can read with more simple description of this topic (CIDR) that generated with AI in ([More Information](#cidr-1))**

---
## More Information

![image](https://github.com/user-attachments/assets/d5addb2e-2af9-4fde-a069-16b1f43bc24e)
![image](https://github.com/user-attachments/assets/ec4b8467-1470-447d-a679-11ed75f212e0)


### CIDR
#### What is CIDR?
CIDR (Classless Inter-Domain Routing) is a way to describe and organize IP addresses and networks. It replaces the old system where IP addresses were divided into fixed groups (Classes A, B, C, etc.).
Instead of using those fixed groups, CIDR uses a number called the CIDR suffix (e.g., /24) to show how much of the IP address belongs to the "network" part and how much is for individual devices.

#### What’s the CIDR Suffix?
The CIDR suffix is the number of 1s in the subnet mask.
A subnet mask is just a way to divide an IP address into two parts:

- Network part (shared by all devices in the same network)
- Host part (unique to each device in the network)

For example:

**Subnet mask:** 255.255.255.0

- In binary, this is `11111111.11111111.11111111.00000000`.
- It has 24 ones, so the CIDR suffix is **/24**.

So, instead of writing an IP address and subnet mask separately, we write:
`192.168.10.39/24`

#### Example Breakdown

Let’s use the example you gave:
- **IP Address:** 192.168.10.39
- **Subnet Mask:** 255.255.255.0
- **CIDR Notation:** 192.168.10.39/24

This means:

1. The first 24 bits of the IP address (`192.168.10`) belong to the network part.
2. The remaining 8 bits (the `.39`) are for devices (hosts) within that network.
