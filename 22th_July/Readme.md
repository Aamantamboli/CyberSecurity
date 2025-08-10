# Man-in-the-Middle (MITM) Attacks: An Overview & Practical Guide

This guide provides a detailed overview of Man-in-the-Middle (MITM) attacks, based on the provided video tutorial. It covers the core concepts of passive and active sniffing, along with a step-by-step practical demonstration of a passive sniffing attack using a virtual environment with Kali Linux and the Ettercap tool. The guide concludes with essential prevention strategies for both users and website operators.

---

## Table of Contents

1.  What are Man-in-the-Middle (MITM) Attacks?
2.  Types of Sniffing Attacks
    * Passive Sniffing
    * Active Sniffing
3.  Practical Demonstration: Passive Sniffing with Ettercap
    * Setting up the Virtual Environment
    * Identifying Network Information
    * Starting the Ettercap Tool
    * Scanning and Selecting Targets
    * Performing ARP Poisoning
    * Monitoring Network Traffic
    * Stopping the Attack
4.  Man-in-the-Middle Attack Prevention

---

## 1. What are Man-in-the-Middle (MITM) Attacks?

A Man-in-the-Middle (MITM) attack is a type of cyberattack where a perpetrator secretly positions themselves in a conversation or data exchange between a user and an application. The attacker can then eavesdrop, steal sensitive information, or manipulate the data being exchanged without either party being aware of the intrusion.

---

## 2. Types of Sniffing Attacks

The video highlights two main types of sniffing attacks, which are crucial for understanding how MITM attacks are executed:

* **Passive Sniffing:** In this type of attack, the hacker's primary goal is to simply monitor network traffic without interfering. They can capture login credentials, email messages, and other sensitive data that passes through the network. This method is considered passive because the attacker is not actively changing any data; they are merely listening in on the communication.

* **Active Sniffing:** This is a more aggressive form of attack where the attacker actively injects malicious code or manipulates the data packets being sent between the user and the application. Examples of active sniffing attacks include:
    * **IP Spoofing:** Altering packet headers to disguise the attacker's IP address.
    * **ARP Spoofing:** A method of linking an attacker's MAC address to a legitimate IP address on the local network, tricking other devices into sending data to the attacker instead of the intended host.
    * **DNS Spoofing:** Manipulating the Domain Name System (DNS) to redirect users to malicious websites.

---

## 3. Practical Demonstration: Passive Sniffing with Ettercap

This section provides a step-by-step guide on how to perform a passive sniffing attack using the Ettercap tool within a virtual environment.

### Detailed Tasks:

1.  **Set up the Virtual Environment:**
    * The demonstration uses VMware Workstation with two virtual machines: a Windows machine (the user) and a Kali Linux machine (the attacker).
    * Ensure both machines are connected to the same virtual network adapter to simulate a shared network environment.

2.  **Identify Network Information:**
    * **On the Kali Linux machine**: Open a terminal and run the command `ifconfig` to find its IP address.
    * **On the Windows machine**: Open the Command Prompt and run the command `ipconfig` to find its own IP address as well as the default gateway's IP address.

3.  **Start the Ettercap Tool:**
    * **On the Kali Linux machine**: Search for and launch the Ettercap tool.
    * Provide the authentication password for Kali Linux when prompted.
    * In the Ettercap window, select the primary interface as `eth0`.
    * Set the sniffing mode to "Unified sniffing."

4.  **Scan and Select Targets:**
    * **Start sniffing**: Click the "Start sniffing" button.
    * **Scan for hosts**: Go to the `Hosts` menu and click `Scan for hosts`.
    * **View hosts list**: After the scan is complete, go to the `Hosts` menu again and click `Hosts list`.
    * **Add targets**:
        * Select the IP address of the default gateway (the router) and add it as **Target 1**.
        * Select the IP address of the Windows machine (the victim) and add it as **Target 2**.

5.  **Perform ARP Poisoning:**
    * **Start the MITM attack**: Click on the world-like icon in the toolbar, go to `MITM`, and select `ARP poisoning`.
    * **Configure options**: In the ARP poisoning options, choose "Sniff remote connections" and click "OK".

6.  **Monitor Network Traffic:**
    * Once the attack is started, any data exchanged between the Windows machine and the internet will now pass through the Kali Linux machine.
    * On the Windows machine, a user logs into a test e-commerce site.
    * The Ettercap window on the Kali Linux machine will then display the intercepted traffic, including the plaintext username and password.

7.  **Stop the Attack:**
    * To stop the MITM attack, click the red square button on the toolbar or go back to the world-like icon and select `Stop MITM attacks`.
    * Close the Ettercap tool.

---

## 4. Man-in-the-Middle Attack Prevention

To protect against MITM attacks, users and applications should follow several practical prevention steps:

* **Avoid unsecured public Wi-Fi networks**: Do not connect to public Wi-Fi networks that are not password protected, as these are easy targets for passive sniffing.
* **Pay attention to browser notifications**: Immediately heed warnings from your browser about insecure websites.
* **Use secure applications**: Log out of applications immediately when they are not in use.
* **Avoid sensitive transactions on public networks**: Refrain from conducting sensitive transactions like online banking or e-commerce purchases when connected to public networks.
* **For website operators**: Implement secure communication protocols like **TLS (Transport Layer Security)** and **HTTPS (Hypertext Transfer Protocol Secure)**. This encrypts data, making it difficult for attackers to intercept and read sensitive information. Additionally, use secure session cookies that are not easily hijacked.
