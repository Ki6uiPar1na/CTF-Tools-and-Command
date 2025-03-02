<div align="center">

  # CTF Tools and Commands  

  <img src="/src/hi.webp" alt="image" width="400">

</div>

---

# Kali Linux Tools and Commands  

This repository contains a collection of useful tools and commands for Kali Linux. It includes essential commands for penetration testing, system administration, and cybersecurity tasks.

---

## 📌 Table of Contents  

1. [📡 Network Tools](#network-tools)  
2. [🌐 Web Exploitation Tools](#web-exploitation-tools)  
3. [🕵️‍♂️ Forensics Tools](#forensics-tools)  
4. [📂 Miscellaneous Commands](#miscellaneous-commands)  
5. [🖼️ Steganography Tools](#steganography-tools)  

---

## 💻 Basic Linux Commands  

These are fundamental commands every Kali Linux user should know.

| Command       | Description |
|--------------|------------|
| `cd`         | Change directory |
| `ls`         | List files and directories |
| `pwd`        | Print current working directory |
| `cp`         | Copy files or directories |
| `mv`         | Move or rename files and directories |
| `rm`         | Remove files or directories |
| `cat`        | View file content |
| `echo`       | Print text to terminal or file |
| `chmod`      | Change file permissions |
| `chown`      | Change file ownership |
| `find`       | Search for files and directories |
| `grep`       | Search for patterns inside files |

---

## 📡 Network Tools  

Useful commands and tools for network-related tasks in Kali Linux.

| Tool           | Description                                      | Command                     |
|---------------|-------------------------------------------------|-----------------------------|
| **Nmap**       | Network scanning & vulnerability detection     | `nmap [options] [target]`   |
| **Netcat**     | Network debugging and port scanning            | `nc -l -p [port]`           |
| **Wireshark**  | GUI-based network protocol analyzer            | `wireshark`                 |
| **Tcpdump**    | CLI-based network packet capture tool          | `tcpdump -i eth0`           |
| **Aircrack-ng** | Wireless security auditing                    | `airmon-ng start wlan0`     |

---

## 🌐 Web Exploitation Tools  

These tools help in penetration testing of web applications.

| Tool        | Description                                   | Command                  |
|------------|----------------------------------------------|--------------------------|
| **Burp Suite** | Web security testing framework          | `burpsuite`              |
| **Nikto**      | Web server vulnerability scanner       | `nikto -h [target]`      |
| **SQLmap**     | Automated SQL injection tool          | `sqlmap -u [target_url]` |
| **Gobuster**   | Directory and file brute-forcing      | `gobuster dir -u [URL]`  |

---

## 🕵️‍♂️ Forensics Tools  

Tools for digital forensics and evidence analysis.

| Tool         | Description                                | Command                   |
|-------------|-------------------------------------------|---------------------------|
| **Exiftool** | Extract metadata from images and files  | `exiftool [file]`         |
| **Binwalk**  | Analyze and extract firmware images     | `binwalk -e [file]`       |
| **Foremost** | File recovery based on headers          | `foremost -i [file]`      |

---

## 🖼️ Steganography Tools  

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
