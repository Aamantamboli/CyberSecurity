# Distributed Denial-of-Service (DDoS) Attacks: A Detailed Guide
---

## 1. The Theory: DoS vs. DDoS

### Denial-of-Service (DoS) Attacks 
A **DoS attack** is a cyberattack where a single attacker floods a target server with a massive amount of traffic from a **single source**. This overwhelms the server's resources (such as bandwidth and memory), causing it to crash or become unresponsive to legitimate users.

### Distributed Denial-of-Service (DDoS) Attacks 
A **DDoS attack** is a more powerful and sophisticated version of a DoS attack. It uses a large network of compromised computers, known as a **botnet**, to launch the attack from **multiple sources**. Because the traffic comes from many different locations, it is much more difficult to trace and block. Each computer in the botnet is often referred to as a "zombie."

---

## 2. Practical Demonstration: Performing a DDoS Attack Task

The video demonstrates a DDoS attack using a command-line tool within a **Kali Linux** virtual environment. The task involves a series of steps to target a website and launch the attack.

### Step-by-Step Task:

1.  **Target Identification**: The first task is to find the target's IP address. The video uses an online tool called **DNS Dumpster** to resolve a website's domain name to its corresponding IP address. For the demonstration, the IP address `92.112.198.69` is identified as the target.
2.  **Launching the Attack**: The attack is launched from the Kali Linux terminal using the **hping3** command. This is a network tool used to send custom TCP/IP packets. The video uses the following command:

    `sudo hping3 -S -p 80 -c 100000 92.112.198.69`

    **Breakdown of the command:**
    * `sudo`: Executes the command with superuser privileges.
    * `hping3`: The name of the tool being used.
    * `-S`: Sets the SYN flag, indicating that the packets are part of a SYN flood attack (a common type of DDoS).
    * `-p 80`: Specifies the destination port, which is the standard port for HTTP traffic.
    * `-c 100000`: Sets the packet count, telling the tool to send **100,000 packets** to the target.
    * `92.112.198.69`: The IP address of the target server.

3.  **Monitoring the Results**: The `hping3` command's output shows how many packets were sent and received. A successful attack is indicated by a high number of sent packets and a very low or zero number of received packets, which means the target is not responding due to being overwhelmed.

---

## 3. Legal and Ethical Considerations

This information is provided for educational purposes only. Performing DDoS attacks is **illegal** and can lead to severe legal consequences. It is crucial to understand that such activities are strictly prohibited.
