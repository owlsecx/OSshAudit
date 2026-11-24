# 🦉 OSshAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSshAudit --help   # watch every network call
firejail --net=none ./OSshAudit --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
