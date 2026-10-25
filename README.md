# 🦉 ONfsAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **ONfsAudit** — Offline NFS Export Configuration Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

ONfsAudit is an offline, read-only NFS export and share configuration auditor. It parses `/etc/exports`, nfs.conf, idmapd.conf, and fstab NFS mounts to evaluate squash, Kerberos/sec=, client CIDR breadth, NFSv2/UDP, and related hardening issues. It never mounts or writes; reports include score/grade and TXT/Markdown/JSON/CSV/SARIF export.

---

## ✨ Features

- Tolerant /etc/exports (+ exports.d) parser with effective-option engine mirroring exports(5) defaults
- Client classifier for world (`*`), CIDR breadth, IPv6, wildcards, netgroups, and hostname DNS-trust
- Export rules: no_root_squash, rw without all_squash, sec=sys, insecure ports/locks, sensitive paths, fsid issues
- nfs.conf / legacy nfs-kernel-server sysconfig analysis (NFSv2, UDP, unpinned ports, RDMA)
- idmapd.conf and fstab NFS client mount hygiene (soft, nolock, vers=2, udp, nosuid/nodev)
- Hardened exports proposal, rule catalogue, multi-format export, `--demo` and CI severity gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ONfsAudit --scan
./ONfsAudit --root ./collected --exports etc/exports --format sarif -o nfs.sarif
./ONfsAudit --check-line '/home *(rw,no_root_squash)' --demo
./ONfsAudit --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
