# Burp Suite: Linux System Hacking & Packet Capturing Guide

This guide, based on the provided video tutorial, covers two distinct but important cybersecurity topics: resetting a forgotten password on a Linux system and effectively capturing and filtering web traffic using Burp Suite for penetration testing.

## Table of Contents

1.  [Linux System Hacking: Password Reset](https://www.google.com/search?q=%231-linux-system-hacking-password-reset)
2.  [Packet Capturing using Burp Suite](https://www.google.com/search?q=%232-packet-capturing-using-burp-suite)
      * [Burp Suite & Browser Proxy Configuration](https://www.google.com/search?q=%23burp-suite--browser-proxy-configuration)
      * [Observing and Filtering HTTP History](https://www.google.com/search?q=%23observing-and-filtering-http-history)
      * [Understanding HTTP Methods (GET vs. POST)](https://www.google.com/search?q=%23understanding-http-methods-get-vs-post)

-----

## 1\. Linux System Hacking: Password Reset

This section demonstrates a method to reset a forgotten password on a Linux system by modifying GRUB boot parameters.

**Steps to Reset Linux Password:**

1.  **Restart the Linux System:** Initiate a restart of your Linux machine.
2.  **Access GRUB Interface:** During the boot process, as soon as the GRUB bootloader appears (or by quickly clicking on the screen/pressing a key like `Esc` or `Shift` to reveal it), press the `e` key on your keyboard to enter the GRUB edit interface.
3.  **Edit Linux Boot Parameters:**
      * Use the arrow keys (mouse is not functional here) to navigate to the line that begins with "Linux".
      * Locate the "ro" (read-only) parameter within this line.
      * **Modify Parameter:** Change "ro" to "rw" (read-write).
      * **Add Init Shell:** After "rw", add `init=/bin/bash`. This instructs the system to boot directly into a bash shell.
      * **Case Sensitivity:** Remember that Linux is case-sensitive, so ensure all commands and parameters are typed in lowercase.
4.  **Boot into Modified System:** Press `Ctrl + X` or `F10` to boot the system using the modified parameters. This will drop you into a root bash shell.
5.  **Change the Password:**
      * In the bash shell, type `passwd` followed by the username you wish to reset (e.g., `passwd kali`).
      * You will be prompted to enter the new password twice. Note that characters typed will not be visible for security reasons.
6.  **Reboot the System:** After successfully changing the password, type `reboot -f` to forcefully reboot the system.
7.  **Login with New Password:** The system will restart, and you can now log in using the newly set password.

-----

## 2\. Packet Capturing using Burp Suite

This section explains how to leverage Burp Suite to capture and effectively filter web traffic, which is crucial for analyzing web application behavior and identifying vulnerabilities.

### Burp Suite & Browser Proxy Configuration

1.  **Start Burp Suite:** Launch the Burp Suite application.
2.  **Configure Burp Suite Proxy:** Ensure that Burp Suite's proxy listener is active. The default listener is typically set to `127.0.0.1:8080`.
3.  **Configure Browser Proxy (FoxyProxy):**
      * Use a browser extension like FoxyProxy (as demonstrated in the video) to direct your browser's traffic through Burp Suite.
      * Set the proxy address in FoxyProxy to `127.0.0.1` and the port to `8080`.
      * Make sure to enable this proxy in your browser when you want to intercept traffic.
4.  **Browse Target Website:** Navigate to the website you intend to test in your configured browser (e.g., `kachkart.com`).

### Observing and Filtering HTTP History

1.  **View HTTP History:** In Burp Suite, go to the "HTTP history" tab. This tab displays all captured requests and responses.
2.  **Filter Requests by Scope:** To reduce clutter from irrelevant domains (like analytics or third-party content) and focus only on your target:
      * Right-click on any request originating from your target website (e.g., `kachkart.com`).
      * Select "Add to scope."
3.  **Apply Scope Filter:**
      * In the "HTTP history" tab, locate the "Filter settings" (often at the top or bottom of the history pane).
      * Select the option "Show only in-scope items." This will filter the history to display only traffic related to your defined target, making analysis much more efficient.

### Understanding HTTP Methods (GET vs. POST)

Understanding HTTP methods is fundamental for web penetration testing, as they dictate how data is exchanged between the client and server.

  * **GET Method:**
      * **Purpose:** Used to retrieve data from the server.
      * **Characteristics:** Data is appended to the URL as query parameters, making it visible in the URL bar and browser history.
      * **Example:** Clicking on a link to view a page, such as an "About Us" page.
  * **POST Method:**
      * **Purpose:** Used to send or "post" data to the server, typically for creating or updating resources.
      * **Characteristics:** Data is sent in the body of the HTTP request, making it less visible than GET parameters.
      * **Example:** Submitting a form, such as a "Contact Us" form or a login form.

Understanding when and how these methods are used is crucial for effectively manipulating requests during web penetration testing.

-----
