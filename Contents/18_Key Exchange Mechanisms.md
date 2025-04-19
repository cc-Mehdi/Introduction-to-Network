# Key Exchange Mechanisms

Key exchange methods are used to exchange [cryptographic keys](https://www.cloudflare.com/learning/ssl/what-is-a-cryptographic-key/) between two parties securely. This is an essential part of many cryptographic protocols, as the security of the encryption used to protect communication relies on the secrecy of the keys. There are many key exchange methods, each with unique characteristics and strengths. Some key exchange methods are more secure than others, and the appropriate method depends on the situation's specific circumstances and requirements.

These methods typically work by allowing the two parties to agree on a **shared secret key** over an insecure communication channel that encrypts the communication between them. This is generally done using some form of mathematical operation, such as a computation based on the properties of a mathematical function or a series of simple manipulations of the key.

## Diffie-Hellman

![image](https://github.com/user-attachments/assets/d8010f30-fdf4-4938-917d-ccdf27294649)

One common key exchange method is the [Diffie-Hellman key exchange](https://www.comparitech.com/blog/information-security/diffie-hellman-key-exchange/), which allows two parties to agree on a shared secret key without any prior communication or shared private information. It is based on the concept of two parties generating a shared secret key that can be used to encrypt and decrypt messages between them. It is often used as the basis for establishing secure communication channels, such as in the [Transport Layer Security](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/) (**TLS**) protocol that is used to protect web traffic.

One of the main limitations of the **Diffie-Hellman** key exchange is that it is vulnerable to **MITM attacks**. In a MITM attack, we intercept the communication between the two parties and pretend to be one of the parties, generating a different secret key and tricking both parties into using it. This allows the attacker to read and modify the messages sent between the parties.

Another limitation is that it requires a relatively large amount of **CPU power** to generate the shared secret key. This can make it impractical for use in low-power devices or in situations where the key needs to be generated quickly.

## RSA

![image](https://github.com/user-attachments/assets/79c30bbd-9078-4779-b27e-f637cf3feff0)
