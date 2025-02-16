 # Wireless Networks

![image](https://github.com/user-attachments/assets/924f27b3-2f67-4f98-add1-574709ae583e)

Wireless networks are computer networks that use wireless data connections between network nodes. These networks allow devices such as laptops, smartphones, and tablets to communicate with each other and the Internet without needing physical connections such as cables.

Wireless networks use radio frequency (**RF**) technology to transmit data between devices. Each device on a wireless network has a wireless adapter that converts data into RF signals and sends them over the air. Other devices on the network receive these signals with their own wireless adapters, and the data is then converted back into a usable form. Those can operate over various ranges, depending on the technology used. For example, a local area network (LAN) that covers a small area, such as a home or small office, might use a wireless technology called **WiFi**, which has a range of a few hundred feet. On the other hand, a wireless wide area network (**WWAN**) might use mobile telecommunication technology such as cellular data (**3G, 4G LTE, 5G**), which can cover a much larger area, such as an entire city or region.

Therefore, to connect to a wireless network, a device must be within range of the network and configured with the correct network settings, such as the network name and password. Once connected, devices can communicate with each other and the Internet, allowing users to access online resources and exchange data.

Communication between devices occurs over RF in the **2.4 GHz** or **5 GHz** bands in a WiFi network. When a device, like a laptop, wants to send data over the network, it first communicates with the [Wireless Access Point](https://en.wikipedia.org/wiki/Wireless_access_point) (**WAP**) to request permission to transmit. The WAP is a central device, like a router, that connects the wireless network to a wired network and controls access to the network.
Once the WAP grants permission, the transmitting device sends the data as RF signals, which are received by the wireless adapters of other devices on the network. The data is then converted back into a usable form and passed on to the appropriate application or system.

The strength of the RF signal and the distance it can travel are influenced by factors such as the transmitter's power, the presence of obstacles, and the density of RF noise in the environment. So, to ensure reliable communication, WiFi networks use techniques such as spread spectrum transmission and error correction to overcome these challenges.

## WiFi Connection

The device must also be configured with the correct network settings, such as the network name / [Service Set Identifier](https://www.geeksforgeeks.org/service-set-identifier-ssid-in-computer-network/) (**SSID**) and **password**. So, to connect to the router, the laptop uses a wireless networking protocol called [IEEE 802.11](https://en.wikipedia.org/wiki/IEEE_802.11). This protocol defines the technical details of how wireless devices communicate with each other and with WAPs. When a device wants to join a WiFi network, it sends a request to the WAP to initiate the connection process. This request is known as a **connection request frame** or **association request** and is sent using the **IEEE 802.11** wireless networking protocol. The connection request frame contains various fields of information, including the following but not limited to:

![image](https://github.com/user-attachments/assets/5f5492c6-790c-4adb-ae54-c5c026103f87)

The device then uses this information to configure its wireless adapter and connect to the WAP. Once the connection is established, the device can communicate with the WAP and other network devices. It can also access the Internet and other online resources through the WAP, which acts as a gateway to the wired network. However, the **SSID** can be hidden by disabling broadcasting. That means that devices that search for that specific WAP will not be able to identify its **SSID**. Nevertheless, the **SSID** can still be found in the authentication packet.

In addition to the **IEEE 802.11** protocol, other networking protocols and technologies may also be used, like TCP/IP, DHCP, and WPA2, in a WiFi network to perform tasks such as assigning IP addresses to devices, routing traffic between devices, and providing security.

## WEP Challenge-Response Handshake

The challenge-response handshake is a process to establish a secure connection between a WAP and a client device in a wireless network that uses the WEP security protocol. This involves exchanging packets between the WAP and the client device to authenticate the device and establish a secure connection.

![image](https://github.com/user-attachments/assets/e1d717f0-43df-4cf9-af22-261c93f5e741)

Nevertheless, some packets can get lost, so the so-called **CRC** checksum has been integrated. [Cyclic Redundancy Check](https://en.wikipedia.org/wiki/Cyclic_redundancy_check) (**CRC**) is an error-detection mechanism used in the WEP protocol to protect against data corruption in wireless communications. A CRC value is calculated for each packet transmitted over the wireless network based on the packet's data. It is used to verify the integrity of the data. When the destination device receives the packet, the CRC value is recalculated and compared to the original value. If the values match, the data has been transmitted successfully without any errors. However, if the values do not match, the data has been corrupted and needs to be retransmitted.

The design of the **CRC** mechanism has a flaw that allows us to decrypt a single packet **without** knowing the **encryption key**. This is because the **CRC** value is calculated using the **plaintext** data in the packet rather than the encrypted data. In WEP, the **CRC** value is included in the packet header along with the encrypted data. When the destination device receives the packet, the CRC value is recalculated and compared to the original one to ensure that the data has been transmitted successfully without any errors. However, we can use the **CRC** to determine the plaintext data in the packet, even if the data is encrypted.

## Security Features

WiFi networks have several security features to protect against unauthorized access and ensure the privacy and integrity of data transmitted over the network. Some of the leading security features include but are not limited to:

- Encryption
- Access Control
- Firewall

### Encryption

We can use various encryption algorithms to protect the confidentiality of data transmitted over wireless networks. The most common encryption algorithms in WiFi networks are [Wired Equivalent Privacy](https://en.wikipedia.org/wiki/Wired_Equivalent_Privacy) (**WEP**), [WiFi Protected Access 2](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access#WPA2) (**WPA2**), and [WiFi Protected Access 3](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access#WPA3) (**WPA3**).

### Access Control

WiFi networks are configured by default to allow authorized devices to join the network using specific authentication methods. However, these methods can be changed by requiring a password or a unique identifier (such as a MAC address) to identify authorized devices.

### Firewall

A firewall is a security system that controls incoming and outgoing network traffic based on predetermined security rules. For example, WiFi routers often have built-in firewalls that can block incoming traffic from the Internet and protect against various types of cyber threats.

## Encryption Protocols

[Wired Equivalent Privacy](https://en.wikipedia.org/wiki/Wired_Equivalent_Privacy) (**WEP**) and [WiFi Protected Access](https://en.wikipedia.org/wiki/Wi-Fi_Protected_Access) (**WPA**) are encryption protocols that secure data transmitted over a WiFi network. WPA can use different encryption algorithms, including [Advanced Encryption Standard](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) (**AES**).

### WEP

**WEP** uses a **40-bit** or **104-bit** key to encrypt data, while **WPA using AES** uses a **128-bit** key. Longer keys provide more robust encryption and are more resistant to attacks. However, it is vulnerable to various attacks that can allow an attacker to decrypt data transmitted over the network. In addition, WEP is not compatible with newer devices and operating systems and is generally no longer considered secure. Finally, **WEP** uses the **RC4 cipher** encryption algorithm, which makes it vulnerable to attacks.

However, WEP uses a **shared key** for authentication, which means the same key is used for encryption and authentication. There are two versions of the WEP protocol:

- WEP-40/WEP-64
- WEP-104

**WEP-40**, also known as **WEP-64**, uses a **40-bit** (secret) key, while **WEP-104** uses a **104-bit** key. The key is divided into an [Initialization Vector](https://en.wikipedia.org/wiki/Initialization_vector) (**IV**) and a **secret key**.

The **IV** is a small value included in the packet header along with the encrypted data and is used to create the key for both **WEP-40** and **WEP-104** and is included to ensure that each key is unique. The secret key is a series of random bits used to encrypt the data. However, the **WEP-104** has a **80-bits** long **secret key**. Let us look at the following table to see the differences clearly:

![image](https://github.com/user-attachments/assets/1adbe58d-0746-4499-90da-0b841c0b6af0)

However, since the IV in WEP is relatively small, we can brute force it, try every possible combination of characters for it, and determine the correct value. Afterward, we can use it to decrypt the data in the packet. This allows us to access the data transmitted over the wireless network and potentially compromise the network's security.

### WPA

**WPA** provides the highest level of security and is not susceptible to the same types of attacks as WEP. In addition, WPA uses more secure authentication methods, such as a [Pre-Shared Key](https://en.wikipedia.org/wiki/Pre-shared_key) (**PSK**) or an 802.1X authentication server, which provide stronger protection against unauthorized access. Although older devices may not support WPA is compatible with most devices and operating systems. All wireless networks, especially in critical infrastructure like offices, should generally implement at least **WPA2** or even **WPA3** encryption.

### Authentication Protocols

[Lightweight Extensible Authentication Protocol](https://en.wikipedia.org/wiki/Lightweight_Extensible_Authentication_Protocol) (**LEAP**) and [Protected Extensible Authentication Protocol](https://en.wikipedia.org/wiki/Protected_Extensible_Authentication_Protocol) (**PEAP**) are authentication protocols used to secure wireless networks to provide a secure method for authenticating devices on a wireless network and are often used in conjunction with WEP or WPA to provide an additional layer of security.

LEAP and PEAP are both based on the [Extensible Authentication Protocol](https://en.wikipedia.org/wiki/Extensible_Authentication_Protocol) (**EAP**), a framework for authentication used in various networking contexts. However, one key difference between **LEAP** and **PEAP** is how they secure the authentication process.

- **LEAP** uses a **shared key** for authentication, which means that the **same key** is used for **encryption and authentication**.

This can make it relatively easy for us to gain access to the network if the key is compromised.

However, **PEAP** uses a more secure authentication method called tunneled [Transport Layer Security](https://en.wikipedia.org/wiki/Transport_Layer_Security) (**TLS**). This method establishes a secure connection between the device and the WAP using a **digital certificate**, and an encrypted tunnel protects the authentication process. This provides more robust protection against unauthorized access and is more resistant to attacks.

#### At simple explanation (Authentication Protocols)

LEAP and PEAP are two methods for securing wireless networks that help devices connect to Wi-Fi securely.

🔹 LEAP uses a shared key for authentication, meaning the same key is used for both encryption and authentication. This method has lower security because if the key is compromised, hackers can easily access the network.

🔹 PEAP uses a method called TLS, which creates an encrypted tunnel between the device and the modem (WAP). This method provides higher security as it uses a digital certificate and offers better protection against hacking attempts.

Simply put, LEAP is like a simple lock with a shared key, so if someone finds the key, they can easily get in. But PEAP is like a high-security door with strong encryption, making it much harder to break in. 🚀🔐

### TACACS+

In a wireless network, when a wireless access point (WAP) sends an authentication request to a [Terminal Access Controller Access-Control System Plus](https://www.ciscopress.com/articles/article.asp?p=422947&seqNum=4) (**TACACS+**) server, it is likely that the **entire request packet** will be encrypted to protect the confidentiality and integrity of the request.
