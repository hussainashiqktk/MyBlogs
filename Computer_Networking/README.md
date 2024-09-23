# Computer Networking

## Resources

- THM Room : https://tryhackme.com/r/room/introtonetworking
- Practical Networking : https://tryhackme.com/r/room/introtonetworking
- Free Comptia Network+ Practice Questions : https://joshmadakor.tech/network-plus/

## TEST Yourself
- CompTIA Network+ Certification Practice Test Questions : https://www.examcompass.com/comptia/network-plus-certification/free-network-plus-practice-tests
- 

## Other Notes

## Checking local dns cache in windows

To display the contents of the DNS resolver cache: Type ```ipconfig /displaydns``` and press Enter. Observe the contents of the DNS resolver cache

##  How a URL gets converted into an IP address that your computer can understand? 

Ever wondered how a URL gets converted into an IP address that your computer can understand? The answer lies in a TCP/IP protocol called **DNS (Domain Name System)**.

At the most basic level, DNS allows us to ask a special server for the IP address of the website we're trying to access. For example, if we request `www.google.com`, our computer sends a request to a DNS server (which it already knows how to find). The server then looks up the IP address for Google and sends it back, allowing our computer to connect to Google’s server.

1. **Initial Request**:
   - You make a request to a website. The first action your computer takes is to check its local **Hosts File** for any explicit IP-to-Domain mappings. This is an older system than DNS and is less commonly used today, but it takes precedence in most operating systems.

2. **Local DNS Cache**:
   - If no mapping is found, your computer checks its local **DNS cache** for a stored IP address for the website. If it finds one, great! If not, it moves on to the next step.

3. **Recursive DNS Server**:
   - Assuming the address hasn't been found, your computer sends a request to a **recursive DNS server**. These servers are typically known to the router on your network. Many Internet Service Providers (ISPs) maintain their own recursive servers, while companies like Google and OpenDNS also operate them.
   - The recursive server maintains a cache of results for popular domains. If the requested website isn’t in its cache, it forwards the request to a **root name server**.

4. **Root Name Servers**:
   - Before 2004, there were exactly 13 root name DNS servers globally. Today, there are more, but they still use the same 13 IP addresses assigned to the original servers, balanced so you access the closest one.
   - Root name servers keep track of DNS servers in the next tier, directing your request to the appropriate **Top-Level Domain (TLD) server**.

5. **Top-Level Domain (TLD) Servers**:
   - TLD servers are organized by extensions. For example:
     - For `tryhackme.com`, your request goes to a TLD server that handles `.com` domains.
     - For `bbc.co.uk`, it’s directed to a TLD server for `.co.uk` domains.
   - TLD servers, like root servers, keep track of the next level down: **Authoritative name servers**.

6. **Authoritative Name Servers**:
   - These servers store DNS records for domains directly. Every domain has its DNS records stored on an authoritative name server.
   - When your request reaches the authoritative name server for the domain you’re querying, it sends the relevant information back, allowing your computer to connect to the requested IP address.
  

## Where is the DNS Cache stored in Windows?

```
There is no "cache file" – the cache is kept in memory only. It is maintained by the "DNS Client" service (internally named Dnscache), therefore the cache data would be somewhere inside one of the svchost.exe processes.
```
Read more here : https://superuser.com/questions/1029285/where-is-dns-cache-located-on-windows-8-1

---

## OSI Model Deep Dive

![image](https://github.com/user-attachments/assets/c11ff928-5a13-4b80-88f6-f2c059ddbe86)

- https://www.youtube.com/watch?v=oVVlMqsLdro&t=1867s

