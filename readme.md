# CTF Tools and Commands

---

# Kali Linux Tools and Commands

This repository contains a collection of useful tools and commands for Kali Linux. It includes essential commands for penetration testing, system administration, and cybersecurity tasks.

---

## 📌 Table of Contents

1. [🐟 Basic Linux Commands](#-basic-linux-commands)
2. [💎 Network Tools](#-network-tools)
3. [🌐 Web Exploitation Tools](#-web-exploitation-tools)
4. [🕵️‍♂️ Forensics Tools](#-forensics-tools)
5. [📂 Miscellaneous Commands](#-miscellaneous-commands)
6. [🎨 Steganography Tools](#-steganography-tools)
7. [🔍 Useful Command Examples](#-useful-command-examples)
8. [🎯 Tool Downloads](#-tool-downloads)

---

## 💻 Basic Linux Commands

These are fundamental commands every Kali Linux user should know.

| Command | Description                          |
| ------- | ------------------------------------ |
| `cd`    | Change directory                     |
| `ls`    | List files and directories           |
| `pwd`   | Print current working directory      |
| `cp`    | Copy files or directories            |
| `mv`    | Move or rename files and directories |
| `rm`    | Remove files or directories          |
| `cat`   | View file content                    |
| `echo`  | Print text to terminal or file       |
| `chmod` | Change file permissions              |
| `chown` | Change file ownership                |
| `find`  | Search for files and directories     |
| `grep`  | Search for patterns inside files     |

---

## 💎 Network Tools

Useful commands and tools for network-related tasks in Kali Linux.

| Tool            | Description                                | Command                   |
| --------------- | ------------------------------------------ | ------------------------- |
| **Nmap**        | Network scanning & vulnerability detection | `nmap [options] [target]` |
| **Netcat**      | Network debugging and port scanning        | `nc -l -p [port]`         |
| **Wireshark**   | GUI-based network protocol analyzer        | `wireshark`               |
| **Tcpdump**     | CLI-based network packet capture tool      | `tcpdump -i eth0`         |
| **Aircrack-ng** | Wireless security auditing                 | `airmon-ng start wlan0`   |

---

## 🌐 Web Exploitation Tools

These tools help in penetration testing of web applications.

| Tool           | Description                      | Command                  |
| -------------- | -------------------------------- | ------------------------ |
| **Burp Suite** | Web security testing framework   | `burpsuite`              |
| **Nikto**      | Web server vulnerability scanner | `nikto -h [target]`      |
| **SQLmap**     | Automated SQL injection tool     | `sqlmap -u [target_url]` |
| **Gobuster**   | Directory and file brute-forcing | `gobuster dir -u [URL]`  |

- **Burp Suite for Windows**: [Download](https://portswigger.net/burp/communitydownload)

---

## 🕵️‍♂️ Forensics Tools

Tools for digital forensics and evidence analysis.

| Tool         | Description                            | Command              |
| ------------ | -------------------------------------- | -------------------- |
| **Exiftool** | Extract metadata from images and files | `exiftool [file]`    |
| **Binwalk**  | Analyze and extract firmware images    | `binwalk -e [file]`  |
| **Foremost** | File recovery based on headers         | `foremost -i [file]` |

---

## 🎨 Steganography Tools

Steganography tools help in hiding or extracting data from images and files.

- **Aperisolve**: [🔗 Visit Aperisolve](https://www.aperisolve.com/)
- **Steghide**: Hide/extract data in images
  - Embed data: `steghide embed -cf image.jpg -ef secret.txt`
  - Extract data: `steghide extract -sf image.jpg`

---

## 🔍 Useful Command Examples

### ✅ Scan a target for open ports:

```bash
nmap -p- -A [target]
```

### ✅ Check running processes:

```bash
ps aux
```

### ✅ Find all files modified in the last 24 hours:

```bash
find / -mtime -1 -type f
```

### ✅ Download a file from the terminal:

```bash
wget [URL]
```

---

## 🎯 Tool Downloads

- **Nmap**: [Download](https://nmap.org/download.html)
- **Wireshark**: [Download](https://www.wireshark.org/download.html)
- **SQLmap**: [Download](https://github.com/sqlmapproject/sqlmap)
- **Steghide**: [Download](http://steghide.sourceforge.net/download.php)

---

## 🤝 Contributing

If you want to contribute, feel free to open an issue or submit a pull request.

💌 Contact: [Your Email or GitHub Profile]

---

🚀 **Happy Hacking! Stay Ethical.** 🛡️

