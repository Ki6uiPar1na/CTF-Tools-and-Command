<div align = "center">
    <h1>CTF Tools and Command</h1>
    <img src="/src/hi.webp" alt="image">
</div>

# Kali Linux Tools and Commands

This repository contains a collection of useful tools and commands for Kali Linux. It includes essential commands for penetration testing, system administration, and other tasks.

## Table of Contents

1. [Network Tools](#network-tools)
2. [Web Exploitation Tools](#web-exploitation-tools)
3. [Forensics Tools](#forensics-tools)
4. [Miscellaneous Commands](#miscellaneous-commands)
5. [Steganography Tools](#steganography-tools)

## ![Kali Linux Logo](https://www.kali.org/images/kali-logo.svg)

---

## Network Tools

Here are some useful commands and tools for network-related tasks in Kali Linux.

| Tool           | Description                               | Command                       |
|----------------|-------------------------------------------|-------------------------------|
| **Nmap**       | Network exploration and vulnerability scanning tool. | `nmap [options] [target]`      |
| **Netcat**     | Utility for network connections and debugging. | `nc -l -p [port]`             |
| **Wireshark**  | Network protocol analyzer.               | `wireshark`                   |

---

## Web Exploitation Tools

These tools are designed for web application testing.

- **Burp Suite**: A comprehensive platform for web security testing.
  - Start Burp Suite: `burpsuite`
  
- **Nikto**: A web server scanner for identifying vulnerabilities.
  - Start Nikto scan: `nikto -h [target]`

## 

### Command for Directory Traversal Testing:
```bash
curl -X GET http://example.com/../../etc/passwd
```

## Steganography Tools

- **Aperisolve**: [Aperisolve](https://www.aperisolve.com/)

