![image](https://github.com/user-attachments/assets/b9b64f8a-8e85-4185-8d3d-a56a79ddce0b)
In understanding computer networks, it's important to categorize and identify networks based on their **types** and **topologies**. This helps in understanding how data is transferred, what range the network covers, and what it’s best suited for. The terminology related to network types can sometimes be overwhelming due to the mix of practical terms used in everyday scenarios and theoretical ones learned primarily in academic settings.
We rarely hear some of the terminologies in practice, so this section will be broken up into **Common Terms** and **Book Terms**.


# Network Types
Types refer to the nature of the network, often based on scale or purpose, such as **Local Area Network (LAN)**, **Wide Area Network (WAN)**, **Metropolitan Area Network (MAN)**, and others. They define how far the network spans geographically and the structure of its connectivity.
![image](https://github.com/user-attachments/assets/3df4d008-e113-4aeb-aeae-091be4a5c953)
![image](https://github.com/user-attachments/assets/0ae75375-bd08-4fe5-bd8e-0dbdc805a33e)

### 1. Common Terms:
These are the network types and terminologies that you will frequently encounter in real-world applications:

LAN (Local Area Network): This is a network that covers a small, specific area such as a single building, office, or home. LANs are used for connecting computers and devices within close proximity to share resources like printers or data files.

WAN (Wide Area Network): This type spans a much larger geographical area and is often used to connect multiple LANs. The internet is the most prominent example of a WAN.

WLAN (Wireless Local Area Network): Similar to a LAN, but with the capability to connect devices wirelessly. This is commonly seen in homes, cafes, and offices with Wi-Fi connectivity.

MAN (Metropolitan Area Network): A network that covers a larger area than a LAN but is not as vast as a WAN. Typically, it connects multiple LANs within a city or campus, facilitating communication between branches of an organization or public systems like city-wide Wi-Fi.

PAN (Personal Area Network): A very localized network used for connecting devices around an individual, such as Bluetooth connections between a smartphone and a headset or a laptop and a mouse.

### 2. Book Terms:
These terms are more academic or less commonly used outside specialized discussions or exams:

CAN (Campus Area Network): A network larger than a LAN but confined to a limited geographic area such as a university campus, business campus, or industrial complex.

SAN (Storage Area Network): A network that provides access to consolidated, block-level data storage. SANs are typically used in data centers and enterprise storage environments to enhance performance and availability.

EPN (Enterprise Private Network): A network built and maintained by an organization for private use to connect various sites and ensure secure communication.

VPN (Virtual Private Network): While not exactly a type of network based on geographical range, a VPN extends a private network across a public network. It enables users to send and receive data as if their devices were directly connected to the private network.

BAN (Body Area Network): A specialized type of network involving wearable computing devices that communicate with each other. Common in medical and fitness technology, it covers the area around an individual’s body.

# Read More

### WAN
- The WAN (Wide Area Network) is commonly referred to as **The Internet**.
- a WAN is just a large number of LANs joined together. Many large companies or government agencies will have an "Internal WAN" (also called Intranet, Airgap Network, etc.).
- Generally speaking, the primary way we identify if the network is a WAN is to use a WAN Specific routing protocol such as BGP and if the IP Schema in use is not within RFC 1918 (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16).

### VPN
VPNs **(Virtual Private Networks)** are tools that allow users to **securely** connect to another network as if they were physically connected to it. This is achieved through **secure**, **encrypted connections** over the internet. There are **three** main types of VPNs, each designed for different use cases but all with the same goal: **ensuring privacy**, **security**, and the appearance of being part of a different network. Here's an explanation of the **three** main types:

1. Remote Access VPN:
This type allows individual users to connect to a private network from a remote location. It's commonly used by employees working from home or traveling who need to access their company’s internal resources like files, applications, or databases.
If the VPN only creates routes for specific networks (ex: 10.10.10.0/24), this is called a **Split-Tunnel VPN**, meaning the Internet connection is not going out of the VPN.
However, for a company, **split-tunnel VPN's** are typically not ideal because if the machine is infected with malware, network-based detection methods will most likely not work as that traffic goes out the Internet.

3. Site-to-Site VPN:


4. Client-to-Site VPN:


