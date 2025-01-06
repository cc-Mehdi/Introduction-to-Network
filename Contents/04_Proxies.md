# The Proxy

![image](https://github.com/user-attachments/assets/3a1fc021-8673-4823-b7bf-696b42f56d45)

## What is proxy ?

A proxy, in general, refers to a device or service that acts as an intermediary in communication between two parties. The key role of being an intermediary in a proxy is that the middle device must be able to inspect the contents of the traffic. If the middle device simply passes the traffic through without inspection, it is called a Gateway, not a proxy.

## Difference Between VPN and Proxy:

Many people mistakenly think that changing an IP address means using a proxy. However, a VPN (Virtual Private Network) is more commonly used for changing geographical location and encrypting traffic. But a VPN in most cases is not a proxy, because it doesn’t act as an intermediary for inspecting content; instead, it encrypts and tunnels the traffic.


## OSI Layer and Proxy:

A proxy typically operates at Layer 7 (Application Layer) of the OSI model, as it deals with inspecting content (such as HTTP requests). This differentiates it from a Gateway or VPN, which may operate at lower layers, such as Layer 3 (Network Layer).

## Types of Proxies:

1. Dedicated Proxy / Forward Proxy
- This type of proxy helps end users connect to the internet.
- The user sends their requests to the proxy, and the proxy forwards them to the destination.
- It is usually used for purposes such as bypassing restrictions, caching data, or access control.

2. Reverse Proxy
- This type of proxy is placed on the server side and manages incoming requests from users.
- It is often used to improve security, load balancing, or to hide the details of actual servers.
- Tools like Cloudflare or ModSecurity fall into this category.

3. Transparent Proxy
- In this type of proxy, users may not be aware that their traffic is passing through a proxy.
- It is often used by organizations for traffic control or monitoring.


## Dedicated Proxy / Forward Proxy

The **Forward Proxy**, is what most people imagine a proxy to be. A Forward Proxy is when a client makes a request to a computer, and that computer carries out the request.

For example, in a corporate network, sensitive computers may not have direct access to the Internet. To access a website, they must go through a proxy (or web filter). This can be an incredibly powerful line of defense against malware, as not only does it need to bypass the web filter (easy), but it would also need to be proxy aware or use a non-traditional C2 (a way for malware to receive tasking information). If the organization only utilizes FireFox, the likelihood of getting proxy-aware malware is improbable.

Web Browsers like Internet Explorer, Edge, or Chrome all obey the "System Proxy" settings by default. If the malware utilizes [WinSock](https://en.wikipedia.org/wiki/Winsock) (Native Windows API), it will likely be proxy aware without any additional code. Firefox does not use WinSock and instead uses [libcurl](https://curl.se/libcurl/), which enables it to use the same code on any operating system. This means that the malware would need to look for Firefox and pull the proxy settings, which malware is highly unlikely to do.

Alternatively, malware could use DNS as a [c2 mechanism](https://pentera.io/glossary/command-and-control-c2-attacks/#:~:text=Command%20and%20Control%20(C2)%20refers%20to%20the%20mechanisms%20used%20by,to%20malware%20on%20compromised%20devices.), but if an organization is monitoring DNS (which is easily done using [Sysmon](https://medium.com/falconforce/sysmon-11-dns-improvements-and-filedelete-events-7a74f17ca842) ), this type of traffic should get caught quickly.

Another example of a Forward Proxy is [Burp Suite](https://www.geeksforgeeks.org/what-is-burp-suite/), as most people utilize it to forward HTTP Requests. However, this application is the swiss army knife of HTTP Proxies and can be configured to be a reverse proxy or transparent!

![image](https://github.com/user-attachments/assets/74174c18-9fa6-41da-aed3-d63794427b0c)

## Reverse Proxy

As you may have guessed, a **reverse proxy**, is the reverse of a **Forward Proxy**. Instead of being designed to filter outgoing requests, it filters incoming ones. The most common goal with a Reverse Proxy, is to listen on an address and forward it to a closed-off network.

Many organizations use CloudFlare as they have a robust network that can withstand most DDOS Attacks. By using Cloudflare, organizations have a way to filter the amount (and type) of traffic that gets sent to their webservers.

Penetration Testers will configure reverse proxies on infected endpoints. The infected endpoint will listen on a port and send any client that connects to the port back to the attacker through the infected endpoint. This is useful to bypass firewalls or evade logging. Organizations may have [IDS (Intrusion Detection Systems)](https://en.wikipedia.org/wiki/Intrusion_detection_system), watching external web requests. If the attacker gains access to the organization over SSH, a reverse proxy can send web requests through the SSH Tunnel and evade the IDS.

Another common Reverse Proxy is [ModSecurity](https://modsecurity.org/), a [Web Application Firewall (WAF)](https://www.cloudflare.com/learning/ddos/glossary/web-application-firewall-waf/). Web Application Firewalls inspect web requests for malicious content and block the request if it is malicious. If you want to learn more about this, we recommend reading into the [ModSecurity Core Rule Set](https://owasp.org/www-project-modsecurity-core-rule-set/), as its a great starting point. Cloudflare, also can act as a WAF but doing so requires letting them decrypt HTTPS Traffic, which some organizations may not want.

![image](https://github.com/user-attachments/assets/d2312fce-e684-4b8a-92d9-c83cac494ac3)

## (Non-) Transparent Proxy

All these proxy services act either **transparently** or **non-transparently**.

With a **transparent proxy**, the client doesn't know about its existence. The transparent proxy intercepts the client's communication requests to the Internet and acts as a substitute instance. To the outside, the transparent proxy, like the non-transparent proxy, acts as a communication partner.

If it is a **non-transparent proxy**, we must be informed about its existence. For this purpose, we and the software we want to use are given a special proxy configuration that ensures that traffic to the Internet is first addressed to the proxy. If this configuration does not exist, we cannot communicate via the proxy. However, since the proxy usually provides the only communication path to other networks, communication to the Internet is generally cut off without a corresponding proxy configuration.
