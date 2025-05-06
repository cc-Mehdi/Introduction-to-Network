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

