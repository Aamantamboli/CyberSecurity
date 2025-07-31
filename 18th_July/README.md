**Network Sniffing & Packet Capturing Guide (Wireshark & Ettercap)**

This guide, based on the provided video tutorial, offers a comprehensive understanding of network sniffing. It covers its foundations, different types of attacks, prevention methods, and practical demonstrations using tools like Wireshark. It also delves into essential networking protocols and virtual machine network adapter configurations relevant to performing sniffing.

**Table of Contents**

1.  Introduction to Sniffing
2.  Types of Sniffing
    * Passive Sniffing
    * Active Sniffing
3.  Understanding ARP and DHCP Protocols
4.  Practical Demonstration: Sniffing with Wireshark
5.  Configuring Virtual Machine Network Adapter
6.  Introduction to Ettercap

---

**1. Introduction to Sniffing**

Sniffing is the act of intercepting and monitoring network traffic. This can be done using software that captures data packets passing through a given network interface or by using hardware devices specifically designed for this purpose.

* **Definition**: Intercepting and monitoring network traffic.
* **Historical Context (Wired Sniffing / Wiretapping)**: Physically connecting to a wire between two communicating parties to eavesdrop. This acted as a "man-in-the-middle" attack.
* **Modern Context (Wireless Sniffing)**: Predominantly performed wirelessly.

**2. Types of Sniffing**

There are two primary types of sniffing:

* **Passive Sniffing**: The attacker monitors traffic passing through a network without interfering. This type of attack can be beneficial for gathering information about targets on a network and the types of data (e.g., login credentials, email messages) they are transmitting. It is less likely to raise suspicion than other types of attacks because it does not involve any interference with the target systems.
* **Active Sniffing**: This type of sniffing involves sending crafted packets to one or more targets on a network to extract sensitive data. By using specially crafted packets, attackers can often bypass security measures that would otherwise protect data from being intercepted. Active sniffing can also involve injecting malicious code into target systems that allows attackers to take control of them or steal sensitive information.

**3. Understanding ARP and DHCP Protocols**

* **ARP (Address Resolution Protocol)**: This protocol is responsible for mapping IP addresses (which are logical addresses) to MAC addresses (which are physical addresses). When a device needs to communicate with another device on the same local network, it uses ARP to find out the destination device's MAC address.
* **DHCP (Dynamic Host Configuration Protocol)**: This protocol automates the process of assigning IP addresses to devices on a network. A DHCP server provides IP addresses, subnet masks, gateway addresses, and other network configuration parameters to devices that request them.

**4. Practical Demonstration: Sniffing with Wireshark**

Wireshark is a powerful network protocol analyzer that can be used for sniffing.

**Detailed Tasks to Capture and Analyze Traffic:**

1.  **Launch Wireshark**:
    * Navigate to the Kali Linux Applications menu.
    * Go to "Sniffing & Spoofing."
    * Click on "Wireshark" to open the application.
2.  **Select an Interface for Capture**:
    * Upon opening Wireshark, you will see a list of available network interfaces (e.g., `eth0`, `wlan0`, `lo`).
    * Look for the interface that has active traffic (often indicated by a small graph or fluctuating numbers).
    * For wired connections, `eth0` is typically the correct choice. Click on `eth0` to select it.
3.  **Start Packet Capture**:
    * Once the interface is selected, click the "Start capturing packets" icon (usually a green shark fin) in the toolbar.
    * Wireshark will immediately begin displaying live network traffic in its main window.
4.  **Generate Target Traffic (e.g., Login on Insecure Website)**:
    * Minimize Wireshark (do not close it) and open a web browser (like Firefox).
    * Navigate to an unencrypted (HTTP) test website, such as `testphp.vulnweb.com`.
    * Locate a login or sign-up form on the website.
    * Enter a test username (e.g., "test") and a test password (e.g., "test").
    * Submit the form to generate network traffic containing these credentials.
5.  **Stop Packet Capture and Analyze Data**:
    * Return to the Wireshark application.
    * Click the "Stop capturing packets" icon (usually a red square) in the toolbar.
    * **Filter for HTTP Traffic**: In the "Apply a display filter" bar at the top, type `http` and press Enter. This will narrow down the displayed packets to only HTTP protocol traffic.
    * **Identify POST Request**: Scroll through the filtered packets. Look for entries where the "Protocol" column is `HTTP` and the "Info" column indicates a `POST` request (e.g., "POST /login.php HTTP/1.1"). POST requests are typically used for submitting form data like login credentials.
    * **Examine Request Details for Credentials**:
        * Click on the identified HTTP POST request in the packet list pane.
        * In the "Packet Details" pane (middle pane), expand the "Hypertext Transfer Protocol" section.
        * Look for a sub-section often labeled "HTML Form URL Encoded" or similar (e.g., "Line-based text data: application/x-www-form-urlencoded").
        * Expand this section. Here, you will clearly see the plaintext username and password that were entered on the website. This demonstrates how easily sensitive information can be intercepted on unencrypted HTTP websites.

**5. Configuring Virtual Machine Network Adapter**

To effectively sniff network traffic, especially from other devices on your physical network, it's crucial to configure your virtual machine's network adapter settings.

**Detailed Configuration Tasks:**

1.  **Access Virtual Machine Settings**:
    * Open your virtual machine software (e.g., VirtualBox, VMware Workstation).
    * Right-click on your Kali Linux virtual machine in the list of VMs.
    * Select "Settings" from the context menu.
2.  **Navigate to Network Settings**:
    * In the VM settings window, go to the "Network" section (usually located on the left-hand side).
    * Ensure "Adapter 1" is enabled.
3.  **Choose Network Adapter Mode**:
    * Click the "Attached to:" dropdown menu.
    * **NAT (Network Address Translation)**: Select this mode if your VM only needs internet access and does not need to directly interact with other devices on your local physical network. In this mode, the VM shares the host's IP address, and its traffic is limited within its virtual "box."
    * **Bridged Adapter**: Select this mode if you need your VM to act as a full participant on your physical network, obtaining its own IP address from your router. This mode is essential for sniffing traffic from other devices on the same physical network.
4.  **Confirm Settings**:
    * Click "OK" to apply the network adapter settings.
    * Restart your virtual machine if prompted or if network changes don't take effect immediately.

**6. Introduction to Ettercap**

Ettercap is a versatile suite commonly used for man-in-the-middle attacks, including active sniffing and content filtering.

**Detailed Ettercap Usage Tasks:**

1.  **Launch Ettercap**:
    * Navigate to the Kali Linux Applications menu.
    * Go to "Sniffing & Spoofing."
    * Click on "Ettercap" (often "ettercap-graphical" for the GUI version) to open the application.
2.  **Select Primary Interface**:
    * Upon launch, Ettercap will typically present a dialog to select the network interface for sniffing.
    * Choose your primary network interface, usually `eth0` for wired connections.
3.  **Start Unified Sniffing**:
    * Once the interface is selected, go to the "Sniff" menu in the Ettercap toolbar.
    * Select "Start unified sniffing" to begin the process of monitoring network traffic and preparing for man-in-the-middle operations.
