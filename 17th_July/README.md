# Network Scanning & System Hacking with Nmap and Networking Fundamentals

This `readme.md` file summarizes key networking concepts, Nmap scanning techniques, and a Linux password reset method, based on the provided video tutorial. It's designed to give a foundational understanding for cybersecurity enthusiasts and professionals.

## Table of Contents

1.  [Networking Fundamentals](https://www.google.com/search?q=%231-networking-fundamentals)
      * [IP Address Types](https://www.google.com/search?q=%23ip-address-types)
      * [Communication Methods (Unicast, Broadcast, Multicast)](https://www.google.com/search?q=%23communication-methods-unicast-broadcast-multicast)
      * [TCP vs. UDP Protocols](https://www.google.com/search?q=%23tcp-vs-udp-protocols)
2.  [Nmap: Network Scanning Tool](https://www.google.com/search?q=%232-nmap-network-scanning-tool)
      * [Nmap Scanning Techniques](https://www.google.com/search?q=%23nmap-scanning-techniques)
      * [Host Discovery](https://www.google.com/search?q=%23host-discovery)
      * [Service and OS Detection](https://www.google.com/search?q=%23service-and-os-detection)
      * [Information Gathering Tools (`nslookup`, `whois`)](https://www.google.com/search?q=%23information-gathering-tools-nslookup-whois)
-----

## 1\. Networking Fundamentals

Understanding core networking concepts is crucial for any cybersecurity professional.

### IP Address Types

  * **Loopback Address (127.0.0.1):** Represents your own system or machine; used for self-communication, not for external network interaction.
  * **Network Address (e.g., 192.168.159.129):** The address used to communicate with other devices and send data packets across a network.

### Communication Methods (Unicast, Broadcast, Multicast)

  * **Unicast (One-to-One):** Data is sent from a single source to a single, specific destination (e.g., WhatsApp messages).
  * **Broadcast (One-to-All):** Data is sent from a single source to all devices connected to a network (e.g., YouTube live streams to all subscribers).
  * **Multicast (One-to-Specific Group):** Data is sent from a single source to a defined group of devices that have subscribed to receive that data (e.g., Netflix streaming, online gaming, specific live events).

### TCP vs. UDP Protocols

These are the two primary transport layer protocols, each with distinct characteristics:

| Feature           | TCP (Transmission Control Protocol)                               | UDP (User Datagram Protocol)                               |
| :---------------- | :---------------------------------------------------------------- | :--------------------------------------------------------- |
| **Connection** | Connection-oriented (establishes connection first)                | Connectionless (sends data without prior connection)       |
| **Reliability** | Reliable (guarantees delivery, order, and integrity via ACKs)     | Unreliable (does not guarantee delivery, order, or integrity) |
| **Order** | Delivers packets in the same order they were sent                 | Packets may arrive out of order or be lost                  |
| **Speed** | Slower (due to overhead of connection establishment and reliability) | Faster (less overhead, suitable for real-time applications) |
| **Use Cases** | Web browsing (HTTP/S), Email (SMTP), File Transfer (FTP)          | Online gaming, Video streaming, Live broadcasting, DNS     |

-----

## 2\. Nmap: Network Scanning Tool

Nmap (Network Mapper) is a free and open-source utility for network discovery and security auditing. It's widely used for port scanning, OS detection, service version detection, and more.

### Nmap Scanning Techniques

| Scan Type                | Command      | Description                                                                                                                              |
| :----------------------- | :----------- | :--------------------------------------------------------------------------------------------------------------------------------------- |
| **SYN Scan / Stealth Scan** | `nmap -sS`   | Performs a partial TCP three-way handshake, making it stealthier and faster. Does not complete the connection.                          |
| **TCP Connect Scan** | `nmap -sT`   | Completes the full TCP three-way handshake. Less stealthy, but works reliably.                                                         |
| **UDP Scan** | `nmap -sU`   | Scans for open UDP ports. Can be slow and unreliable due to UDP's connectionless nature.                                                |
| **Null Scan** | `nmap -sN`   | Sends a TCP packet with no flags set. Exploits TCP RFC behavior to determine port state.                                                 |
| **FIN Scan** | `nmap -sF`   | Sends a TCP packet with only the FIN flag set. Exploits TCP RFC behavior.                                                               |
| **Xmas Scan** | `nmap -sX`   | Sends a TCP packet with FIN, PSH, and URG flags set (like Christmas tree lights). Exploits TCP RFC behavior.                           |
| **Idle Scan / Zombie Scan** | `nmap -sI`   | An advanced, highly stealthy scan that uses a "zombie" host to bounce scans off, concealing your own IP address from the target.      |

### Host Discovery

| Command      | Description                                     |
| :----------- | :---------------------------------------------- |
| **List Scan** | `nmap -sL`   | Lists targets without performing a scan.          |
| **Ping Scan** | `nmap -sn`   | Discovers live hosts on a network.                |
| **No Ping Scan** | `nmap -Pn`   | Skips the host discovery phase (assumes host is up). |

### Service and OS Detection

| Command        | Description                                                                                             |
| :------------- | :------------------------------------------------------------------------------------------------------ |
| **Service Version Detection** | `nmap -sV`   | Attempts to determine the version of services running on open ports.                                    |
| **OS Detection** | `nmap -O`    | Attempts to determine the operating system of the target host.                                          |
| **Aggressive Scan** | `nmap -A`    | Enables OS detection, version detection, script scanning, and traceroute for a comprehensive scan. |

### Information Gathering Tools (`nslookup`, `whois`)

These command-line tools are vital for initial reconnaissance:

  * **`nslookup`:** Used to query Domain Name System (DNS) to obtain domain name or IP address mapping or for any other specific DNS record.
      * Example: `nslookup example.com`
  * **`whois`:** Used to retrieve detailed registration information about a domain name, including registrar, creation/expiration dates, and contact information.
      * Example: `whois example.com`

-----
