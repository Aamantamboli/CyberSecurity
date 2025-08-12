# A Practical Guide to Social Engineering & Network Security

This guide provides a hands-on overview of **social engineering** and **network security**
---

## 1. What is Social Engineering?

**Social engineering** is a manipulation technique that exploits human error to gain private information, access, or valuables. In cybersecurity, it often involves tricking users into clicking malicious links, revealing sensitive information, or unknowingly granting access.

This video demonstrates a real-world example using the **Seeker** tool to capture a target’s **geolocation** through a fake **WhatsApp group invite link**.

---

## 2. Tools Used in the Video 🧰

The tutorial walks through the setup and use of two main tools:

### Seeker

* A social engineering tool used to **track GPS location** of targets.
* Generates fake web pages that mimic real services.
* Captures IP address and geolocation when the victim clicks the link.

### Ngrok

* A reverse proxy tool that allows port forwarding.
* Exposes the local Seeker server to the internet via a **public URL**.
* Useful for sharing local services with external users securely.

---

## 3. Linux File Permissions (CHMOD) 📂

The video explains the **Linux file permission system**, which controls access to files:

### Permission Types:

* **Read (r)** – Value: 4
* **Write (w)** – Value: 2
* **Execute (x)** – Value: 1

### User Categories:

* **User (u)** – File owner
* **Group (g)** – Members of the file’s group
* **Others (o)** – All other users

### Example:

To make a script executable:

```bash
chmod +x seeker.py
```

To assign permissions using numbers (e.g., 755):

```bash
chmod 755 filename
```

Which gives:

* User: Read, Write, Execute
* Group: Read, Execute
* Others: Read, Execute

---

## 4. Installing and Using Seeker

### Cloning Seeker from GitHub

```bash
git clone https://github.com/thewhiteh4t/seeker.git
cd seeker
```

### Making the script executable

```bash
chmod +x seeker.py
```

---

## 5. Installing and Using Ngrok

### Download & Setup

* Download Ngrok from [https://ngrok.com/](https://ngrok.com/)
* Extract and run Ngrok using:

```bash
./ngrok http 8080
```

This command creates a tunnel from your local port `8080` (where Seeker is running) to a public URL like `https://randomsubdomain.ngrok.io`.

---

## 6. Social Engineering Workflow

1. **Start Seeker** and generate a **fake WhatsApp invite page**.
2. **Expose the local Seeker server** using Ngrok on port `8080`.
3. **Resize the image** used in the invite to `300x300px` using an online tool.
4. **Send the Ngrok link** to the target (e.g., via WhatsApp).
5. When the **target clicks**, Seeker captures:

   * IP address
   * Location (latitude & longitude)
   * Device details

---

## 7. Quick Wins & Pro Tips ⚡

* **Image Resizing** is required for proper rendering:

  * Resize to **300x300px** using a tool like [resizeimage.net](https://resizeimage.net)
* **Use paid Ngrok for custom domains**:

  * Free Ngrok gives random subdomains, which may appear suspicious.

---

## 8. Limitations & Warnings ⚠️

* **Ngrok Free Plan**:

  * Limited customization (no branded domains).
  * May appear untrustworthy to savvy users.

* **Tool Limitations**:

  * Seeker requires target interaction.
  * GPS accuracy depends on device/browser settings.
  * Some services (like browsers) may block fake pages.
---
