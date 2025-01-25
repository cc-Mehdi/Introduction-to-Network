# MAC Addresses

![image](https://github.com/user-attachments/assets/32196890-25f6-4436-b21f-eadcd81cd7b7)

Each host in a network has its own **48**-bit (**6 octets**) **Media Access Control** (**MAC**) address, represented in hexadecimal format. **MAC** is the **physical address** for our network interfaces. There are several different standards for the MAC address:

- Ethernet (IEEE 802.3)
- Bluetooth (IEEE 802.15)
- WLAN (IEEE 802.11)

This is because the **MAC** address addresses the physical connection (network card, Bluetooth, or WLAN adapter) of a host. Each network card has its individual MAC address, which is configured once on the manufacturer's hardware side but can always be changed, at least temporarily.

Let's have a look at an example of such a MAC address:

MAC address:

- **DE:AD:BE:EF:13:37**
- **DE-AD-BE-EF-13-37**
- **DEAD.BEEF.1337**

![image](https://github.com/user-attachments/assets/528a32b8-1288-46a5-bc7d-a15860fe8cdd)

When an IP packet is delivered, it must be addressed on **layer 2** to the destination host's physical address or to the router / NAT, which is responsible for routing. Each packet has a **sender address** and a **destination address**.

The MAC address consists of a total of **6 bytes**. The first half (**3 bytes / 24 bit**) is the so-called **Organization Unique Identifier** (**OUI**) defined by the **Institute of Electrical and Electronics Engineers** (**IEEE**) for the respective manufacturers.

![image](https://github.com/user-attachments/assets/7977ec4d-ff60-4e31-b03c-1ee1da97e1b3)

