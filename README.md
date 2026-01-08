# 📡 WiFi Tracker Bot: Complete Installation Guide

Welcome to the documentation for **WiFi Tracker**.
This guide will walk you step-by-step through creating a home surveillance system that monitors your Wi-Fi network and sends real-time notifications to Discord when specific devices connect.

---

## 📑 Table of Contents
1. [Prerequisites](#1-prerequisites)
2. [Discord Configuration](#2-discord-configuration)
3. [Python Environment Setup](#3-python-environment-setup)
4. [The Code (Script)](#4-the-code-script)
5. [Network Mapping](#5-network-mapping)
6. [System Startup](#6-system-startup)

---

## 1. Prerequisites
Before starting, ensure you have:
* A **Windows PC** (acting as the server; it must remain powered on to monitor).
* A **Wi-Fi** or Ethernet connection.
* A **Discord** account.

---

## 2. Discord Configuration
We need to create the "brain" that will send us messages.

1.  Go to the [Discord Developer Portal](https://discord.com/developers/applications).
2.  Click on **New Application** and give it a name (e.g., "Guardian").
3.  Go to the **Bot** section (left menu) and click **Add Bot**.
4.  **IMPORTANT:** Scroll down to "Privileged Gateway Intents" and enable **Message Content Intent**. Without this, the bot is blind!
5.  Click on **Reset Token**, copy it, and save it. *Do not share this with anyone!*
6.  To invite the bot to your server:
    * Go to **OAuth2** > **URL Generator**.
    * Check `bot`.
    * Check `Administrator` (for easier permission handling).
    * Copy the generated link and paste it into your browser to authorize it.

---

## 3. Python Environment Setup
The bot is written in Python. We need to prepare the host PC.The script is in italian, so check translator for foreigner words.

1.  Download and install [Python](https://www.python.org/downloads/). (Make sure to check **"Add Python to PATH"** during installation).
2.  Open your terminal (PowerShell or CMD) and install the necessary libraries:
    ```bash
    pip install discord.py scapy
    ```
3.  **Windows Users Only:** Download and install [Npcap](https://npcap.com/).
    * ⚠️ During installation, you MUST check the option: **"Install Npcap in WinPcap API-compatible Mode"**. This is critical for Scapy to function correctly.

---

## 4. The Code (Script)
Create a folder on your desktop. Inside, create a file named `bot.py` and paste the script code.
*(Make sure to use the version with the `BERSAGLI` dictionary).*
Where needed, copy and paste your discord channel id (ID_CANALE).

---

## 5. Network Mapping
To use the "Sniper" function (Targeting), you need to know the IPs of the devices you want to track.

1.  Access your router (usually `192.168.1.1` or `192.168.1.254`).
2.  Look for the **Connected Devices**, **LAN**, or **DHCP** section.
3.  Find the MAC Address of the target phones and note the assigned IP address.
4.  Insert these IPs into the `BERSAGLI` (TARGETS) dictionary inside the script.

---

## 6. System Startup
1.  Open PowerShell as **Administrator** (Right-click Start > Terminal (Admin)).
2.  Navigate to the bot's folder:
    ```powershell
    cd C:\Path\To\Your\Folder
    ```
3.  Launch the bot:
    ```powershell
    python bot.py
    ```

If you see the message `✅ RADAR ACTIVE`, the system is operational.
