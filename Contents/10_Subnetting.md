# Subnetting 

![image](https://github.com/user-attachments/assets/7b9181f6-3c06-4d9a-904f-1ceb0531bc74)


The division of an address range of IPv4 addresses into several smaller address ranges is called **subnetting**.

A subnet is a logical segment of a network that uses IP addresses with the same network address. We can think of a subnet as a labeled entrance on a large building corridor. For example, this could be a glass door that separates various departments of a company building. With the help of subnetting, we can create a specific subnet by ourselves or find out the following outline of the respective network:

- Network address
- Broadcast address
- First host
- Last host
- Number of hosts

Let us take the following IPv4 address and subnet mask as an example:

- IPv4 Address: **192.168.12.160**
- Subnet Mask: **255.255.255.192**
- CIDR: **192.168.12.160/26**

We already know that an IP address is divided into the **network part** and the **host part**.

### Network Part

![image](https://github.com/user-attachments/assets/ff619ad7-a618-4bf2-8419-c4a3f233758a)

In subnetting, we use the subnet mask as a template for the IPv4 address. From the **1**-bits in the subnet mask, we know which bits in the IPv4 address **cannot** be changed. These are **fixed** and therefore determine the "main network" in which the subnet is located.

### Host Part

![image](https://github.com/user-attachments/assets/2e8e5016-aaa6-4be1-97a1-fc53d02c1eee)

The bits in the **host part** can be changed to the **first** and **last** address. The first address is the **network address**, and the last address is the **broadcast address** for the respective subnet.

The **network address** is vital for the delivery of a data packet. If the **network address** is the same for the source and destination address, the data packet is delivered within the same subnet. If the network addresses are different, the data packet must be routed to another subnet via the **default gateway**.

The **subnet mask** determines where this separation occurs.

### Separation Of Network & Host Parts

![image](https://github.com/user-attachments/assets/987ab36c-51f1-434b-803a-7c2830ffb2ea)

### Network Address

So if we now set all bits to **0** in the **host part** of the IPv4 address, we get the respective subnet's **network address**.

![image](https://github.com/user-attachments/assets/a203f0c8-19e7-41ae-a1de-27e92e32033b)

