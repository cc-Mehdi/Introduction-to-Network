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

### Broadcast Address

If we set all bits in the **host part** of the IPv4 address to **1**, we get the **broadcast address**.

![image](https://github.com/user-attachments/assets/45dbfdd3-ae44-4938-8603-9826334104d5)

Since we now know that the IPv4 addresses **192.168.12.128** and **192.168.12.191** are assigned, all other IPv4 addresses are accordingly between **192.168.12.129-190**. Now we know that this subnet offers us a total of **64 - 2** (network address & broadcast address) or **62** IPv4 addresses that we can assign to our hosts.

![image](https://github.com/user-attachments/assets/b429c77c-a138-4d5f-888b-26b80bf8966f)

### Subnetting Into Smaller Networks

Let us now assume that we, as administrators, have been given the task of dividing the subnet assigned to us into 4 additional subnets. Thus, it is essential to know that we can only divide the subnets based on the binary system.

![image](https://github.com/user-attachments/assets/41371a2b-32d3-4c64-97a6-be047649f60e)

Therefore we can divide the 64 hosts we know by 4. The 4 is equal to the exponent 2^2 in the binary system, so we find out the number of bits for the subnet mask by which we have to extend it. So we know the following parameters:

- Subnet: **192.168.12.128/26**
- Required Subnets: **4**

Now we increase/expand our subnet mask by **2 bits** from **/26** to **/28**, and it looks like this:

![image](https://github.com/user-attachments/assets/f00fe1fa-8a9d-43c9-9405-d4938f93a0a3)

Next, we can divide the **64** IPv4 addresses that are available to us into **4 parts**:

![image](https://github.com/user-attachments/assets/223fd0d3-55e4-4de7-8e67-001e25ddaffe)

So we know how big each subnet will be. From now on, we start from the network address given to us (192.168.12.128) and add the **16** hosts **4** times:

![image](https://github.com/user-attachments/assets/a06521db-f303-4396-832d-80128d6891af)

### Mental Subnetting

It may seem like there is a lot of math involved in subnetting, but each octet repeats itself, and everything is a power of two, so there doesn't have to be a lot of memorization. The first thing to do is identify what octet changes.

![image](https://github.com/user-attachments/assets/7341ab2e-c31a-4af6-84ec-3a4fa940b287)

It is possible to identify what octet of the IP Address may change by remembering those four numbers. Given the Network Address: **192.168.1.1/25**, it is immediately apparent that 192.168.2.4 would not be in the same network because the **/25** subnet means only the fourth octet may change.

![image](https://github.com/user-attachments/assets/ebfde63d-0325-47a1-833e-4c6cb369f37d)

By remembering the powers of two up to eight, it can become an instant calculation. However, if forgotten, it may be quicker to remember to divide 256 in half the number of times of the remainder.

The tricky part of this is getting the actual IP Address range because 0 is a number and not null in networking. So in our **/25** with 128 IP Addresses, the first range is **192.168.1.0-127**. The first address is the network, and the last is the broadcast address, which means the usable IP Space would become **192.168.1.1-126**. If our IP Address fell above 128, then the **usable ip space** would be 192.168.1.129-254 (128 is the network and 255 is the broadcast).
