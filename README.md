<div align="center">

**Language:** [English](README.md) · [فارسی](README.fa.md)

```
███╗   ██╗███████╗██╗  ██╗██╗   ██╗███████╗███╗   ██╗███████╗████████╗
████╗  ██║██╔════╝╚██╗██╔╝██║   ██║██╔════╝████╗  ██║██╔════╝╚══██╔══╝
██╔██╗ ██║█████╗   ╚███╔╝ ██║   ██║███████╗██╔██╗ ██║█████╗     ██║
██║╚██╗██║██╔══╝   ██╔██╗ ██║   ██║╚════██║██║╚██╗██║██╔══╝     ██║
██║ ╚████║███████╗██╔╝ ██╗╚██████╔╝███████║██║ ╚████║███████╗   ██║
╚═╝  ╚═══╝╚══════╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝╚═╝  ╚═══╝╚══════╝   ╚═╝
```

# NexusNet Node

**Multi-country Tor Exit node manager** — one VPS, many exit locations.

[![Version](https://img.shields.io/badge/version-v2.1-blue?style=for-the-badge)](https://github.com)
[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-Personal-orange?style=for-the-badge)](#)
[![Platform](https://img.shields.io/badge/Platform-Ubuntu%20%7C%20Debian-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](#)

<br>

**Language:** Python 3  
**Panels:** 3X-UI · Pasargad · Marzban (limited)

</div>

---

## What is NexusNet?

NexusNet turns a **single VPS** into a fleet of **Tor Exit nodes**, each pinned to a different country.  
It wires those nodes into your existing panel (3X-UI / Pasargad) with one command — inbounds, SOCKS outbounds, routing rules, and hosts included.

| Feature | Description |
|--------|-------------|
| 🌍 **50+ countries** | Germany, Turkey, US, France, NL, FI, CH, … |
| 🔌 **Panel Tools** | Auto-clone inbounds & hosts into 3X-UI / Pasargad |
| 🔄 **NEWNYM** | Fresh circuit / exit IP on every restart |
| 💾 **Backup & restore** | Node list + ports in one file |
| 🧹 **Clean delete** | Removes local services **and** panel configs |

---

## Requirements

| Item | Recommendation |
|------|----------------|
| **Location** | Preferably **Germany 🇩🇪** |
| **CPU** | 2+ cores |
| **RAM** | 4 GB+ |
| **OS** | Ubuntu / Debian |
| **Access** | Root (`sudo`) |

> **About latency:** Final ping depends on the user's path through Tor. Better path affinity → lower delay.  
> **About exit IPs:** Countries with few exit relays (e.g. AE) may show a stable IP. From v1.13+, every restart sends `NEWNYM` so Tor can pick another exit when available.

---

## Install

```bash
curl -sL "https://raw.githubusercontent.com/SiNaKeEn/NexusNet-Node/Multi/install.sh" \
  -o /tmp/install.sh && sudo bash /tmp/install.sh
```

> **Tip:** If you hit `Argument list too long`, use the two-step command above.  
> Do **not** run `bash -c "$(curl ...)"` on this installer.

After install:

```bash
nexusnet
```

---

## Menu overview

### Main (`nexusnet`)

| # | Action |
|---|--------|
| 1 | Install engine (dependencies) |
| 2 | Update system |
| 3 | Full uninstall |
| 4 | Add one location |
| 5 | Bulk deploy nodes |
| 6 | List active nodes |
| 7 | Edit / delete node (+ panel cleanup) |
| 8 | Port settings |
| 9 | Latency check |
| 10 | Restart all nodes (+ NEWNYM) |
| 11 | Active ports |
| 12 | Quick country test |
| 13 | Delete all nodes |
| 14 | System status |
| 15 | Backup / restore |
| 16 | **Panel Tools** (3X-UI / Pasargad) |

### Panel Tools

```
── Create ──
  [1] Add installed NexusNet nodes     ← primary workflow
  [2] Create all countries
  [3] Create selected countries

── Manage ──
  [4] Delete configurations
  [0] Exit
```

**Host address modes** (when cloning hosts in Pasargad):

1. Keep source domain/address  
2. Server public IP  
3. **Each node's own Tor exit IP** *(default)* — TR gets a Turkey IP, US gets a US IP, …  
4. Custom address  

---

## Tech stack

| Layer | Stack |
|-------|--------|
| Core | **Python 3** |
| Networking | Tor, SOCKS5, Xray |
| Panels | 3X-UI (SQLite + API), Pasargad (REST), Marzban (manual SOCKS) |
| Installer | Bash + embedded Base64 payloads |

---

## Backup & restore

- **Backup:** `/root/nexusnet_backup.txt` (nodes + ports)  
- **Restore:** Recreates missing nodes from that file  

Deleting a node from option **7** also tries to remove matching inbounds / outbounds / routing / hosts from **3X-UI** and **Pasargad**.

---

## Support

| Channel | Link |
|---------|------|
| Telegram channel | [@NexusNet_Plus](https://t.me/NexusNet_Plus) |
| Telegram bot | [@NexusNet_PlusBot](https://t.me/NexusNet_PlusBot) |
| Support | [@NexusNet_Sup](https://t.me/NexusNet_Sup) |

---

<div align="center">

**Based on the T.Sin idea** · Developed by **SiNa (KeEn)**

`nexusnet` · v2.1 · Personal Edition

</div>
