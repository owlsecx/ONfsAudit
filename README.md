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

Offline NFS export & share configuration auditor

---

## ✨ Features

- Tolerant /etc/exports + /etc/exports.d/*.exports parser (line continuation, quoted paths, octal escapes, "-" default options, malformed recovery)
- Effective-option engine mirroring exports(5) defaults (ro, sync, root_squash, secure, sec=sys)
- Client classifier — world (*), space-before-paren world bug, CIDR / netmask breadth, IPv6, wildcards, @netgroups, hostnames (DNS-trust)
- Export ruleset — no_root_squash, rw without all_squash, sec=sys, sys downgrade, insecure ports, insecure_locks, subtree_check, crossmnt / nohide, duplicate / zero fsid, anonuid=0, sensitive paths
- /etc/nfs.conf (+ include) analyser — NFSv2, UDP, unpinned mountd / statd / lockd ports, RDMA
- Legacy /etc/default/nfs-kernel-server and /etc/sysconfig/nfs argument analysis
- /etc/idmapd.conf — Domain, Nobody mapping, Method
- /etc/fstab NFS client mounts — soft, nolock, intr, timeo, vers=2, udp, nosuid / nodev hygiene
- Collected-tree mode (--root) with filesystem cross checks: keytab, world-writable export dirs, etab drift
- CWE + MITRE ATT&CK (T1135 / T1039 / T1548 ...) map
- Weighted score + grade, hardened exports generator
- Reports: TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Built-in --demo self-test, full CLI with CI gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ONfsAudit
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
