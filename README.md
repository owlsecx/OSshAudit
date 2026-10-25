# 🦉 OSshAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSshAudit** — SSH Configuration & Exposure Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSshAudit is a defensive, read-only SSH configuration and exposure auditor that never attempts authentication and never modifies a file. It parses sshd_config (including Include globs and Match blocks), runs 40+ CIS/Mozilla-style hardening checks, inventories host keys and authorized_keys, and probes live SSH banners. Results are scored and graded per category, support baseline snapshots and regression diffs, and export to TXT, Markdown, JSON or CSV.

---

## ✨ Features


- sshd_config parser with Include globs, drop-in directories and first-value-wins semantics
- 40+ CIS/Mozilla-style hardening checks (root login, passwords, ciphers, MACs, KEX, forwarding, timeouts)
- Weighted 0-100 score with A..F grade per category
- Host-key inventory (type, bits, SHA256 fingerprint) and authorized_keys auditor (types, options, duplicates)
- Client-config audit plus a live banner probe (identification string only, no auth or brute force)
- Baseline snapshots with regression diff and TXT/MD/JSON/CSV export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSshAudit --config /etc/ssh/sshd_config --format md -o ssh.md
./OSshAudit --all --fix
./OSshAudit --banner 10.0.0.5 --port 22
./OSshAudit --save-baseline base.json
./OSshAudit --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
