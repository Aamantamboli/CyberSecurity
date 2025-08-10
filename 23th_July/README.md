# 🛡️ What is Malware?

**Malware** is short for **malicious software** — software designed with **intent to harm**, **exploit**, or **illegally control** computers, networks, or data. Malware can:

* Steal personal data (e.g., passwords, banking info)
* Disrupt or damage systems
* Spy on your activities
* Encrypt your files and demand ransom
* Grant remote access to an attacker

> Malware can spread via email attachments, infected websites, pirated software, USB drives, and even trusted-looking applications.

---

## 💣 Types of Malware (with Examples)

### 1. **Virus**

A **virus** is a piece of malicious code that **attaches itself to legitimate files or programs**. It activates **when the infected file is opened**, and then spreads to other files or systems.

* **Propagation**: Requires user action (e.g., opening a file)
* **Effect**: Corrupts files, crashes systems, or opens backdoors

🔍 **Example**:

* The **ILOVEYOU virus (2000)** disguised as a love letter spread via email and deleted critical files on infected computers.

---

### 2. **Worm**

A **worm** is self-replicating malware that **spreads automatically** across networks without needing a host file or user interaction.

* **Propagation**: Automatically over network vulnerabilities
* **Effect**: Consumes bandwidth, crashes networks, drops more malware

🔍 **Example**:

* The **SQL Slammer worm** (2003) spread in minutes, disrupting internet traffic globally.

---

### 3. **Trojan Horse (Trojan)**

A **Trojan** disguises itself as a **legitimate or useful program** to trick users into installing it. Once inside, it can:

* Steal data

* Spy on you

* Install backdoors

* Let attackers take control

* **Propagation**: User is tricked into installing it

* **Effect**: Varies—data theft, surveillance, etc.

🔍 **Example**:

* **Emotet Trojan** originally spread as a banking Trojan and evolved to deliver other malware like ransomware.

---

### 4. **Ransomware**

**Ransomware** encrypts the victim’s files or locks them out of their system. It then **demands a ransom** (usually in cryptocurrency) in exchange for a decryption key.

* **Propagation**: Email attachments, exploits, RDP attacks
* **Effect**: Files become inaccessible until payment is made

🔍 **Example**:

* **WannaCry (2017)**: Exploited a Windows vulnerability to spread globally in hours. It affected hospitals, banks, and government systems, demanding Bitcoin to unlock files.

---

### 5. **Spyware**

**Spyware** secretly monitors your device, capturing:

* Browsing history
* Screenshots
* Email activity
* Camera/microphone input

It often runs silently in the background and is used to steal personal or corporate data.

* **Propagation**: Bundled with free software or trojans
* **Effect**: Privacy invasion, identity theft, corporate espionage

🔍 **Example**:

* **Pegasus**: A military-grade spyware that could take full control of iPhones and Android devices via zero-click exploits.

---

### 6. **Keylogger**

A **keylogger** is a specific type of spyware that **records every keystroke** typed on a keyboard. It is used to capture:

* Usernames and passwords

* Credit card numbers

* Private messages

* **Propagation**: Trojan downloads, physical access

* **Effect**: Silent theft of sensitive information

🔍 **Video Demonstration**:
The video shows how a **Python script** can be written to log keystrokes using libraries like `pynput` or `keyboard`.

🧪 Example Python Code Snippet (educational purposes only):

```python
from pynput.keyboard import Listener

def log_key(key):
    with open("keylog.txt", "a") as f:
        f.write(str(key) + "\n")

with Listener(on_press=log_key) as listener:
    listener.join()
```

⚠️ **This code is for educational use only. Do not deploy it without consent.**

---

## 🚨 Why Is Malware Dangerous?

| Danger                | Explanation                              |
| --------------------- | ---------------------------------------- |
| **Data theft**        | Credentials, photos, banking info stolen |
| **System damage**     | Files deleted or corrupted               |
| **Financial loss**    | Due to fraud or ransomware payments      |
| **Privacy violation** | Webcam/mic spying, activity tracking     |
| **Spread to others**  | Worms and Trojans infect other users     |

---

## 🛡️ How to Protect Against Malware

| Prevention Tip                      | How It Helps                                |
| ----------------------------------- | ------------------------------------------- |
| Use trusted antivirus software      | Detects and blocks malware                  |
| Keep OS and software updated        | Patches security holes                      |
| Don't click on suspicious links     | Avoid phishing and drive-by downloads       |
| Download only from official sources | Avoids trojans in fake programs             |
| Use strong, unique passwords        | Limits damage if one account is compromised |
| Regularly back up important data    | Allows recovery from ransomware or damage   |

---
