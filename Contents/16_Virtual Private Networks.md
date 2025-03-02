# Virtual Private Networks

![image](https://github.com/user-attachments/assets/2f9d663f-dc44-490b-a3b9-ae3d23e45df8)

A **Virtual Private Network** (**VPN**) is a technology that allows a secure and encrypted connection between a private network and a remote device. This allows the remote machine to access the private network directly, providing secure and confidential access to the network's resources and services. For example, an administrator from another location has to manage the internal servers so that the employees can continue to use the internal services. Many companies limit servers' access, so clients can only reach those servers from the local network. This is where VPN comes into play, where the administrator connects to the VPN server via the internet, authenticates himself, and thus creates an encrypted tunnel so that others cannot read the data transfer. In addition, the administrator's computer is also assigned a local (internal) IP address through which he can access and manage the internal servers. Administrators commonly use VPNs to provide secure and cost-effective remote access to a company's network. VPN typically uses the ports **TCP/1723** for [Point-to-Point Tunneling Protocol](https://www.lifewire.com/home-networking-4781492) **PPTP** VPN connections and **UDP/500** for [IKEv1](https://www.cisco.com/c/en/us/support/docs/security-vpn/ipsec-negotiation-ike-protocols/217432-understand-ipsec-ikev1-protocol.html) and [IKEv2](https://nordvpn.com/blog/ikev2ipsec/) VPN connections.

This allows employees to access the network and its resources, such as email and file servers, from remote locations, such as their homes or while traveling. There are several reasons why administrators use VPNs. VPNs encrypt the connection between the remote device and the private network, making it much more difficult for attackers to intercept and steal sensitive information. With this, the entire communication is more secure.

Another reason is that VPNs allow employees to access the private network and its resources remotely from anywhere, as long as they have an internet connection. This is particularly useful for employees who need to work remotely, such as those traveling or working from home. Additionally, VPNs can be more cost-effective than other remote access solutions, such as leased lines or dedicated connections, because they use the public internet to connect remote users to the private network.

Moreover, we can use VPNs to connect multiple remote locations, such as branch offices, into a single private network, making it easier to manage and access network resources. However, several components and requirements are necessary for a VPN to work:

![image](https://github.com/user-attachments/assets/e56022cb-af9a-463a-a04e-ec94fd401397)

The VPN client and server use these ports to establish and maintain the VPN connection. At the TCP/IP layer, a VPN connection typically uses the [Encapsulating Security Payload](https://www.ibm.com/docs/en/i/7.4?topic=protocols-encapsulating-security-payload) (**ESP**) protocol to encrypt and authenticate the VPN traffic. This allows the VPN client and server to exchange data over the public internet securely.

## IPsec

[Internet Protocol Security](https://www.cloudflare.com/learning/network-layer/what-is-ipsec/) (**IPsec**) is a network security protocol that provides encryption and authentication for internet communications. It is a powerful and widely-used security protocol that provides encryption and authentication for internet communications and works by encrypting the data payload of each IP packet and adding an **authentication header** (**AH**), which is used to verify the integrity and authenticity of the packet. IPsec uses a combination of two protocols to provide encryption and authentication:

1. [Authentication Header](https://www.ibm.com/docs/en/i/7.1?topic=protocols-authentication-header) (**AH**): This protocol provides integrity and authenticity for IP packets but does not provide encryption. It adds an authentication header to each IP packet, which contains a cryptographic checksum that can be used to verify that the packet has not been tampered with.

2. [Encapsulating Security Payload](https://www.ibm.com/docs/en/i/7.4?topic=protocols-encapsulating-security-payload) (**ESP**): This protocol provides encryption and optional authentication for IP packets. It encrypts the data payload of each IP packet and optionally adds an authentication header, similar to AH.
