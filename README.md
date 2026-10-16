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

SSH configuration & exposure auditor (sshd_config, host keys, authorized_keys)

---

## ✨ Features

- sshd_config parser — comments, quoting, Include globs and drop-in directories (sshd_config.d), first-value-wins semantics, Match block capture
- Hardening evaluator — 40+ CIS / Mozilla-style checks (root login, passwords, PAM, empty passwords, ciphers, MACs, KEX, host-key algorithms, forwarding, ClientAlive*, MaxAuthTries, LoginGraceTime, Banner, LogLevel, AllowUsers/Groups, StrictModes, ...)
- Weighted 0–100 score + A…F grade per category
- Host key inventory — type, bits, SHA256 fingerprint (ssh-keygen -l or native parser), permission checks
- authorized_keys auditor — key types, RSA bit length, comments, duplicates across users, options (from=, command=, no-*), file/dir/home permission risks
- Client config audit — ssh_config + ~/.ssh/config (StrictHostKeyChecking, ForwardAgent, weak crypto)
- Live banner probe — TCP connect + SSH identification string only (no auth, no brute force), version risk
- Listening socket check — ss / netstat / /proc/net
- Baseline snapshots (JSON) + regression diff
- Export TXT / Markdown / JSON / CSV, save chooser, clipboard summary
- Full CLI mode (--config, --keys, --auth-keys, ...)

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSshAudit
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
