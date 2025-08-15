# Operating System Installation and Password Reset Process

## Overview

This video demonstrates the process of installing an operating system using a bootable USB drive and resetting Windows passwords. The session includes downloading necessary tools, creating a bootable USB, BIOS configuration, booting from the USB, and resetting passwords. The discussion and actions take place in a classroom or group learning environment, with troubleshooting steps and some issues faced during the process.

---

## Theory

### What is a Bootable USB?

A bootable USB is a USB flash drive that contains a live operating system installer or utility software. It allows the computer to boot (start) directly from the USB, instead of the internal hard drive. This is useful for:

- Installing or reinstalling operating systems.
- Running diagnostic or recovery tools.
- Resetting system passwords or repairing systems.

### About HBCD Operating System

HBCD (Hiren’s BootCD) is a popular bootable utility toolkit for system maintenance. It contains various tools including password reset utilities, system diagnostics, and recovery software. It is often used when troubleshooting or repairing Windows machines.

### BIOS/UEFI and Secure Boot

- **BIOS/UEFI** is firmware used to perform hardware initialization during booting.
- **Secure Boot** is a security feature that ensures only trusted software loads during startup. It needs to be disabled when booting from some external devices like USBs with custom OS.

### Password Reset in Windows

Windows stores user account passwords securely. Tools like the Windows Login Unlocker in HBCD can reset or blank passwords by modifying system files offline, allowing access without the original password.

---

## Practical Demonstration

### 1. System Specs Check and Preparation

- Verify storage capacity (64GB in this case).
- Confirm minimum RAM requirement (4GB).
- Obtain a USB flash drive (pen drive).

### 2. Download Required Software

- Search and download the **HBCD Operating System** ISO.
- Download **Rufus** tool for creating bootable USB.

### 3. Creating Bootable USB

- Open Rufus.
- Select the downloaded HBCD ISO file.
- Choose the correct USB drive.
- Start the process and wait 5-20 minutes.

### 4. BIOS Setup and Booting

- Restart PC and enter BIOS using keys like F2, F10, F12.
- Change boot mode to EFI.
- Disable Secure Boot.
- Save and exit BIOS.
- Enter Boot Manager and select USB drive to boot.

### 5. Reset Windows Password

- Navigate through HBCD tools: Security → Passwords → Windows Login Unlocker.
- Select user accounts, right-click, and reset passwords.
- Clear administrator account passwords if necessary.
- Exit and reboot to Windows.

### 6. Troubleshooting Tips

- Use multiple BIOS keys if one doesn’t work.
- Ensure device is sufficiently charged.
- Record the process using Zoom or a camera as backup.
- Confirm USB boot priority in BIOS settings.

---

## Important Notes

- Collaboration is encouraged; sharing resources like pen drives is helpful.
- Recording is essential since BIOS doesn’t allow native screen recording.
- USB data will be erased during creation of the bootable drive.
- Some steps might need multiple attempts due to hardware differences.

---

## Summary

This video provides a detailed walkthrough for creating a bootable USB to install an OS and reset Windows passwords, highlighting BIOS configurations and necessary software tools. It blends theoretical understanding with practical steps and real-world troubleshooting.

---

## Additional Resources

- [Rufus Official Website](https://rufus.ie/)
- HBCD Operating System download (check video or official site)
- Tutorials on BIOS/UEFI navigation and Secure Boot management

---
