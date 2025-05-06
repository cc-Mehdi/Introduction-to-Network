# Cryptography

![image](https://github.com/user-attachments/assets/b498f2ac-6177-4954-abda-262025d65b72)

Encryption is used on the Internet to transmit data, such as payment information, e-mails, or personal data, confidentially and protected against manipulation. Data is encrypted using various cryptographic algorithms based on mathematical operations. With the help of encryption, data can be transformed into a form that unauthorized persons can no longer read. Digital keys in **symmetric** or **asymmetric** encryption processes are used for encryption. It is easier to crack cipher texts or keys depending on the encryption methods used. If state-of-the-art cryptographic methods with extensive key lengths are used, they work very securely and are almost impossible to compromise for the time being. In principle, we can distinguish between **symmetric** and **asymmetric** encryption techniques. Asymmetric methods have only been known for a few decades. Nevertheless, they are the most frequently used methods in digital communication.

### Symmetric Encryption

Symmetric encryption, also known as secret key encryption, is a method that uses the same key to encrypt and decrypt the data. This means the sender and the receiver must have the same key to decrypt the data correctly.

![image](https://github.com/user-attachments/assets/b015e2d1-7a4c-4dac-bc25-b688c06f3864)

If the secret key is shared or lost, the security of the data is no longer guaranteed. Critical actions for symmetric encryption methods represent the distribution, storage, and exchange of the keys. [Advanced Encryption Standard](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) (**AES**) and Data [Encryption Standard](https://en.wikipedia.org/wiki/Data_Encryption_Standard) (**DES**) are examples of symmetric encryption algorithms. This type of encryption is often used to encrypt large amounts of data, such as files on a hard drive or data sent over a network. **AES** is considered to be the most secure encryption algorithm nowadays.

### Asymmetric Encryption

Asymmetric encryption, also known as **public-key encryption**, is a method of encryption that uses two different keys:

- a **public key**
- a **private key**

![image](https://github.com/user-attachments/assets/37a5bbf5-5d7a-4a1e-9ef1-6022a56fa110)

The public key is used to encrypt the data, while the private key is used to decrypt the data. This means anyone can use a public key to encrypt data for someone, but only the recipient with the associated private key can decrypt the data. Examples of asymmetric encryption methods include [Rivest–Shamir–Adleman](https://en.wikipedia.org/wiki/RSA_(cryptosystem)) (**RSA**), [Pretty Good Privacy](https://en.wikipedia.org/wiki/Pretty_Good_Privacy) (**PGP**), and [Elliptic Curve Cryptography](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography) (**ECC**). Asymmetric encryption is used in a variety of applications, some of which include:

![image](https://github.com/user-attachments/assets/79994bfb-b1da-47a5-92d6-8d3160fd4b20)

