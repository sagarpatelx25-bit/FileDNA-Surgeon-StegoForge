<div align="center">

```
███████╗██╗██╗     ███████╗    ██████╗ ███╗   ██╗ █████╗ 
██╔════╝██║██║     ██╔════╝    ██╔══██╗████╗  ██║██╔══██╗
█████╗  ██║██║     █████╗      ██║  ██║██╔██╗ ██║███████║
██╔══╝  ██║██║     ██╔══╝      ██║  ██║██║╚██╗██║██╔══██║
██║     ██║███████╗███████╗    ██████╔╝██║ ╚████║██║  ██║
╚═╝     ╚═╝╚══════╝╚══════╝    ╚═════╝ ╚═╝  ╚═══╝╚═╝  ╚═╝
         SURGEON & STEGO FORGE  ·  V-MAX ELITE
```

# 🧬 File DNA Surgeon & Stego Forge

**God-Level Binary Manipulation Suite for Cybersecurity Researchers**

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-success?style=for-the-badge)](https://github.com/sagarpatelx25-bit)
[![License](https://img.shields.io/badge/License-MIT-red?style=for-the-badge)](LICENSE)
[![GUI](https://img.shields.io/badge/GUI-CustomTkinter-blueviolet?style=for-the-badge)](https://github.com/TomSchimansky/CustomTkinter)
[![Purpose](https://img.shields.io/badge/Purpose-Educational%20%7C%20CTF-yellow?style=for-the-badge)](README.md)
[![Domain](https://img.shields.io/badge/Domain-Reverse%20Engineering%20%7C%20Forensics-darkred?style=for-the-badge)](https://github.com/sagarpatelx25-bit/FileDNA-Surgeon-StegoForge)

> *"Aam hacker file ka extension dekhta hai. Elite hacker uske Magic Bytes dekhta hai."*

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Requirements](#-requirements)
- [Installation](#️-installation)
- [Usage](#-usage)
- [Module Breakdown](#-module-breakdown)
- [Magic Bytes Reference](#-magic-bytes-quick-reference)
- [Educational Context](#-educational-context)
- [Disclaimer](#️-disclaimer)

---

## 🌐 Overview

**File DNA Surgeon & Stego Forge** is a hands-on, GUI-based binary manipulation suite built for **cybersecurity students, CTF players, and reverse engineering enthusiasts**.

It lets you inspect and surgically modify files at the **raw byte level** — directly on the physical disk — turning theoretical knowledge of Magic Bytes, PE Headers, Endianness, and Steganography into **live, executable tradecraft**.

> ⚠️ This is not a scanner. This is not a viewer. This is a **surgical instrument**.

---

## ⚡ Features

```
┌──────────────────────────────────────────────────────────────────────┐
│                        WEAPON LOADOUT · 6 MODULES                    │
├──────────────────────────────────────────────────────────────────────┤
│  🔬  True Hex Microscope     —  Read any file's raw DNA (hex dump)   │
│  ✍️  Live Disk Patcher       —  Overwrite bytes at any file offset   │
│  💀  PE Header Stomper       —  Wipe MZ header  (Kill Switch / EDR)  │
│  🖼️  Magic Byte Spoof        —  Forge a file's identity to the OS    │
│  🔄  Endianness Flipper      —  Little-Endian converter for BoF      │
│  👻  Steganography Injector  —  Hide payloads after JPEG EOF marker  │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 📦 Requirements

| Dependency | Version |
|------------|---------|
| Python | `>= 3.8` |
| customtkinter | `>= 5.2.0` |
| tkinter | Built-in |

---

## 🛠️ Installation

```bash
# 1. Clone the repository
git clone https://github.com/sagarpatelx25-bit/FileDNA-Surgeon-StegoForge.git
cd FileDNA-Surgeon-StegoForge

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch the tool
python File_DNA_Surgeon___Stego_Forge.py
```

---

## 🚀 Usage

1. Launch the tool via the command above
2. Click **📁 LOAD TARGET FILE** to select any target file
3. The Hex Microscope auto-loads the file's raw DNA
4. Choose your operation from the 3 panels

---

## 🔩 Module Breakdown

### 🔬 Panel 1 — True Hex Microscope & Live Disk Patcher

Renders the first **4KB** of any file in standard Hex Editor format:

```
Offset     │ Hex Bytes (16 per row)                          │ ASCII
───────────┼─────────────────────────────────────────────────┼────────────────
0x00000000 │ 4D 5A 90 00 03 00 00 00 04 00 00 00 FF FF 00 00 │ MZ..............
0x00000010 │ B8 00 00 00 00 00 00 00 40 00 00 00 00 00 00 00 │ ........@.......
```

**Live Disk Patcher** — write any byte(s) to any offset in real time:

```
Offset (Hex) : 0x00000000
New Bytes    : FFD8FFE0
→ [ ✍️ WRITE TO DISK ]   ←  Physical file modified instantly
```

---

### 🔪 Panel 2 — Header Surgery Forge

| Button | What It Does | Real-World Technique |
|--------|-------------|----------------------|
| `💀 STOMP MZ HEADER` | `4D 5A` → `00 00` at offset 0 | PE Header Stomping — hides EXE from EDR/AV memory scanners |
| `🖼️ FAKE-OUT (JPEG)` | First 4 bytes → `FF D8 FF E0` | Magic Byte Spoofing — OS misidentifies the file type |

> 🧠 **PE Stomping Insight:** Advanced malware (Cobalt Strike, Metasploit Reflective DLLs) wipes `MZ` from RAM *after* loading, because EDR scanners search for `MZ` during live memory scans. No `MZ` = invisible.

---

### 🔄 Panel 3 — Endianness Flipper & Stego Forge

**Endian Flipper** (Intel x86/x64 Little-Endian converter):

```
Input  (Big Endian) : 12345678
Output (BoF Payload): \x78\x56\x34\x12    ← Ready for exploit scripts
```

**Steganography Injector:**
- Appends your hidden payload *after* the JPEG `FF D9` (End-of-Image) marker
- The image continues to open perfectly in any viewer
- Hidden data is **invisible** to the OS but recoverable via Hex Editor

```
[VMAX_SECRET]: your_hidden_payload_here
```

---

## 🗺️ Magic Bytes Quick Reference

| File Type | Magic Bytes (Hex) | ASCII Sig | Notes |
|-----------|------------------|-----------|-------|
| JPEG | `FF D8 FF` | `ÿØÿ` | Most common image format |
| PNG | `89 50 4E 47 0D 0A 1A 0A` | `.PNG....` | Lossless image |
| EXE / DLL | `4D 5A` | `MZ` | Mark Zbikowski (DOS PE format) |
| PDF | `25 50 44 46` | `%PDF` | |
| ZIP / DOCX / JAR | `50 4B 03 04` | `PK..` | ZIP-based formats |
| ELF (Linux binary) | `7F 45 4C 46` | `.ELF` | Linux/Android executables |
| GIF | `47 49 46 38` | `GIF8` | |
| MP4 / MOV | `66 74 79 70` | `ftyp` | At offset 4 |
| RAR | `52 61 72 21` | `Rar!` | |

---

## 🧠 Educational Context

This tool was built as the **practical companion** to Phase 1 of an Elite Ethical Hacking Masterclass covering computer architecture and binary fundamentals.

| Concept | Where It Appears |
|---------|-----------------|
| Magic Bytes & File Identity | Hex Microscope + Fake-Out |
| PE Executable Format | Kill Switch / PE Stomper |
| Little-Endian CPU Architecture | Endianness Flipper |
| JPEG Structure & EOF Marker | Steganography Injector |
| Raw Physical Disk I/O (`r+b`) | Live Disk Patcher |
| EDR/AV Evasion Concepts | PE Header Stomping module |

---

## ⚠️ Disclaimer

> **This project is built strictly for educational purposes, CTF (Capture the Flag) challenges, and authorized security research.**
>
> - Only use on files and systems **you own** or have **explicit written permission** to test.
> - The author is **not responsible** for any misuse, damage, or illegal activity involving this tool.
> - Always practice ethical hacking within the boundaries of the law.
> - Recommended platforms for practice: [HackTheBox](https://hackthebox.com), [TryHackMe](https://tryhackme.com), [PicoCTF](https://picoctf.org)

---

<div align="center">

**Built with 💀 by [@sagarpatelx25-bit](https://github.com/sagarpatelx25-bit)**

*Phase 1 Reboot — Computer Architecture & Binary Manipulation Masterclass*

*If this helped your learning journey, drop a ⭐ — it means a lot.*

</div>
