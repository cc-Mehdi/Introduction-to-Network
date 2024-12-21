
# Network Overview
A network enables two computers to communicate with each other. There is a wide array of **topologies** (mesh/tree/star), **mediums** (ethernet/fiber/coax/wireless), and **protocols** (TCP/UDP/IPX) that can be used to facilitate the network.


# Basic Information
Let us look at the following high-level diagram of how a Work From Home setup may work.
![basic_information_image](https://github.com/user-attachments/assets/bcc3f0c5-ae6c-4d11-a2cd-6e19bd95bf80)

The entire internet is based on many subdivided networks, as shown in the example and marked as "Home Network" and "Company Network." We can imagine networking as the delivery of mail or packages sent by one computer and received by the other.
Suppose we imagine as a scenario that we want to visit a company's website from our **"Home Network."** In that case, we exchange data with the company's website located in their **"Company Network."** As with sending mail or packets, we know the address where the packets should go. The website address or **Uniform Resource Locator (URL)** which we enter into our browser is also known as **Fully Qualified Domain Name (FQDN)**.

The fact is that we know the address, but not the exact **geographical location** of the address. In this situation, the post office can determine the exact location, which then forwards the packets to the desired location. Therefore, our post office forwards our packets to the main post office, representing our **Internet Service Provider (ISP)**.

Our post office is our **router** which we utilize to connect to the **"Internet"** in networking.

As soon as we send our packet through our post office **(router)**, the packet is forwarded to the **main post office (ISP)**. This main post office looks in the **address register/phonebook (Domain Name Service)** where this address is located and returns the corresponding geographical coordinates **(IP address)**. Now that we know the address's exact location, our packet is sent directly there by a direct flight via our main post office.

After the web server has received our packet with the request of what their website looks like, the webserver sends us back the packet with the data for the presentation of the website via the post office **(router)** of the **"Company Network"** to the specified return address **(our IP address)**.

