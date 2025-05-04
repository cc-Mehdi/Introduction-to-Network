# Authentication Protocols

![image](https://github.com/user-attachments/assets/bc8c8e49-2b5e-4622-b81f-86c7568641b0)

Many different authentication protocols are used in networking to **verify the identity** of devices and users. Those protocols are essential because they provide a secure and standardized way of verifying the identity of users, devices, and other entities in a network. Without authentication protocols, it would be difficult to securely and reliably identify entities in a network, making it easy for attackers to gain unauthorized access and potentially compromise the network.

Authentication protocols also provide a means for **securely exchanging information** between entities in a network which we will discuss briefly. This is important for ensuring the confidentiality and integrity of sensitive data and preventing unauthorized access and other security threats. Let us take a look at a few most commonly used authentication protocols:

![image](https://github.com/user-attachments/assets/f61bd3b9-4a2f-4066-8b70-11f79570ada0)
![image](https://github.com/user-attachments/assets/8023b63f-19cf-476d-b05a-06bb7097eb27)

For example, LEAP and PEAP may be used to authenticate wireless clients when they access the wireless network or to authenticate remote employees connecting to the network via a VPN. In these cases, using SSH or HTTPS would be challenging to implement, as they are designed for different purposes. In terms of security, **PEAP** is generally more secure than **LEAP** because it uses a server-side public key certificate to authenticate the server and encrypting **MSCHAPv2** hash, while LEAP relies on a shared secret that is negotiated between the client and the server and does **not** encrypt **MSCHAPv2** hashes. PEAP also supports the use of stronger encryption algorithms, such as AES and 3DES, for encrypting the authentication information, whereas LEAP uses the weaker RC4 algorithm.

However, both protocols are vulnerable to specific attacks and have been largely replaced by more secure protocols such as EAP-TLS.

As physical connections, protocols with **SSL** or **TLS** are used by default, such as **SSH** or **HTTPS**. Both protocols use robust encryption algorithms to protect the authentication information transmitted between the client and the server. This helps to prevent interception or to tamper the authentication data, which is essential for maintaining the security of the authentication process. Also, they support using digital certificates and **PKI** for authenticating the server to the client. This ensures that the client can verify the server's identity and helps to prevent MITM attacks. SSH and HTTPS are widely used and well-supported protocols, with implementations available for various operating systems and devices and makes them easy to use and deploy in a variety of environments.
