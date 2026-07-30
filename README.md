# ChanZAi Script v4
### By Christian Geronimo (ChanZAi)

<img width="898" height="675" alt="1" src="https://github.com/user-attachments/assets/7f76da63-6110-4fb5-9d49-880380f4858b" />



---

## ⚠️ DISCLAIMER

> **This script is intended for personal, educational, and troubleshooting use only.**
>
> - The author **is not responsible** for any damage, data loss, or system instability caused by misuse of this script.
> - **Run at your own risk.** Always create a system restore point before using any activation or system tool.
> - Activation features use publicly available KMS keys and Microsoft Activation Scripts (MAS). These are provided as-is, with no guarantee of permanent activation status.
> - This script **does not** collect any personal data or phone home to any server other than the ones explicitly listed (KMS servers, GitHub for IDM activator).
> - All third-party tools and scripts referenced (MAS, IDM activator) belong to their respective authors.
> - **Do not use this script on systems you do not own or have permission to manage.**

---

## 🛡️ Antivirus Detection Disclaimer

Some antivirus engines may detect this tool as a **HackTool, PUA (Potentially Unwanted Application), AutoKMS, Activator, or Trojan-like behavior**.

These detections may happen because this utility performs advanced Windows system operations such as:

- Process management and termination
- Network reset and repair commands
- System cleanup operations
- Software activation-related functions
- Registry and system configuration changes
- Automated maintenance tasks

Security software may classify these actions as suspicious because similar techniques are also used by malicious programs. However, **a detection does not always mean the file is infected.**

### VirusTotal Detection Explanation

If some antivirus engines report:

- `HackTool`
- `WinActivator`
- `AutoKMS`
- `Dropper`
- `Trojan-like behavior`

...it may be caused by the tool's **system-level functionality** rather than an actual malware infection.

Many legitimate administration tools, optimization utilities, and repair tools receive similar classifications because they perform actions that require advanced system access.

### Safety Recommendation

Before running:

1. Verify the file source
2. Scan the file using multiple antivirus engines
3. Review the source code if available
4. Run inside Windows Sandbox or a virtual machine if you are unsure

> ⚠️ Do not download modified versions from unknown sources.

---

## 📋 Requirements

- Windows 10 / 11 (some features support Windows Server editions)
- **Administrator privileges** — the script auto-requests elevation on launch
- PowerShell (built into Windows — no install needed)
- Internet connection (required for options that are marked `[needs internet]`)

---

## 🚀 How to Run

1. Right-click `ChanZAiScriptV4.exe` → **Run as Administrator**
2. The script will auto-request admin if not already elevated
3. Select an option from the menu

---

## 📦 Features

---

### (1) Remove Cache
Cleans junk files and frees up disk space.

Targets:
- Windows Temp folder
- User Temp folder
- Windows Prefetch
- Thumbnail cache
- INet / Browser cache (Chrome, Edge)
- Recent Files list
- Recycle Bin
- Windows Update Download cache

Also runs Windows Disk Cleanup and resets the Microsoft Store cache in the background.

---

### (2) Kill Non-Essential Apps `[AUTO-DETECT]`
Smart process killer that automatically detects all running processes and terminates anything that is **not** a critical Windows system process.

**Always keeps safe:**
- Core Windows system processes (`svchost`, `lsass`, `winlogon`, `dwm`, etc.)
- Your current CMD/PowerShell session
- Windows Explorer (desktop)
- Windows Defender / Security processes

**Kills:**
- Browsers, games, background apps, and any non-whitelisted process

> ⚠️ Warning: This will close all open applications without saving. Save your work first.

---

### (3) Network Operations / Reset
Full network stack reset and refresh.

Steps performed (14 total):
1. Release IPv4 address
2. Release IPv6 address
3. Flush DNS cache
4. Renew IPv4 address
5. Renew IPv6 address
6. Register DNS
7. Reset Winsock
8. Set TCP autotune (restricted mode)
9. Enable TCP RSS
10. Enable TCP timestamps
11. Reset IP stack
12. Reset IPv4 stack
13. Reset IPv6 stack
14. Clear ARP cache

> 💡 A restart is recommended after running this option for full effect.

---

### (4) Activate PC (Product Key)

Full PC activation suite with 4 methods. Displays current Windows edition and live activation status before you choose.

---

#### └─ (1) KMS Offline `[no internet needed, 180 days renewable]`
Auto-detects your Windows edition and installs the correct KMS client key locally — no internet required.

Supports:
- Windows 11/10: Home, Home N, Home Single Language, Pro, Pro N, Pro Education, Pro for Workstations, Education, Enterprise, Enterprise LTSC/LTSB
- Windows Server: 2016, 2019, 2022, 2025 (Standard & Datacenter)

Then checks current activation status and guides you to the next step if offline activation is not enough.

---

#### └─ (2) KMS Online `[needs internet, 180 days renewable]`
Tries additional online-only KMS servers for activation. Renewable every 180 days.

> 🔁 **No internet fallback:** Automatically launches the embedded MAS_AIO if no internet is detected.

---

#### └─ (3) Online (MAS) `[needs internet]`
Downloads and runs Microsoft Activation Scripts (MAS) directly from the official source for a reliable online activation.

> 🔁 **No internet fallback:** Automatically launches the embedded MAS_AIO if no internet is detected.

---

#### └─ (4) Manual Product Key `[offline ok]`
Enter your own valid Windows product key.

- Uses `slmgr /ipk` to install the key
- Confirms success or failure after installation
- No internet needed to install the key

---

#### └─ (5) Permanent - HWID `[needs internet once, then forever]`
Hardware-tied permanent activation via Microsoft Activation Scripts (MAS HWID method).

- Activation is tied to your hardware fingerprint
- Survives Windows reinstalls on the same hardware
- Only needs internet **once**

> 🔁 **No internet fallback:** Automatically launches the embedded MAS_AIO if no internet is detected.

---

### (5) Activate IDM
Activates Internet Download Manager (IDM) using the ChanZAi IDM activator script.

- Downloads and runs the activator from the official ChanZAi GitHub repository
- Requires internet connection
- Prompts for confirmation before proceeding

---

### (6) Auto Shutdown Scheduler
Schedule an automatic shutdown or restart with a custom timer.

Options:
- **(1) Schedule Shutdown** — enter time in seconds (e.g. `3600` = 1 hour)
- **(2) Schedule Restart** — same, but restarts instead of shutting down
- **(3) Cancel Scheduled Shutdown/Restart** — cancels any active shutdown timer
- **(0) Back to Main Menu**

---

### (7) App Opener
Quickly launch commonly used Windows applications from the menu.

Apps include:
- Task Manager
- Device Manager
- Disk Management
- Registry Editor
- Group Policy Editor
- System Information
- Windows Update
- Control Panel
- Event Viewer
- Resource Monitor

---

### (8) View Running Processes
Displays all currently running processes with their PID, CPU usage, and memory usage — sorted by resource consumption.

Powered by PowerShell for accurate real-time data.

---

### (9) Virus Scanner & Remover
Triggers a Windows Defender quick scan and removes any detected threats.

- Uses built-in `MpCmdRun.exe` (Windows Defender CLI)
- No third-party antivirus required
- Shows scan results after completion

---

## 🔁 Embedded MAS_AIO Fallback

For PC Activation options **(2), (3), and (5)** — if no internet is detected, the script automatically extracts and launches the **embedded Microsoft Activation Scripts (MAS_AIO)**, which works both **online and offline**.

- MAS_AIO is embedded directly inside the script — no separate file needed
- Extracted to a temporary file at runtime, then deleted after launch
- The embedded section is clearly marked — **do not edit or delete anything below the warning block**

---

## 📁 File Structure

```
ChanZAiScriptV4.exe     ← Main script (compiled, run this)
README.md               ← This file
```

---

## 👤 Author

**Christian Geronimo** (ChanZAi)
- GitHub: [Christianzgaming](https://github.com/Christianzgaming)
- Script Version: v4.0

---

## 📄 License

This script is free to use for personal use. Redistribution or modification without credit to the original author is not permitted.
