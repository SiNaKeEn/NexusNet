[README.fa.md](https://github.com/user-attachments/files/32896119/README.fa.md)
<div align="center" dir="rtl">

**زبان:** [English](README.md) · [فارسی](README.fa.md)

# NexusNet Node

**مدیریت چندنود Tor Exit** — یک سرور، چندین کشور خروجی.

[![Version](https://img.shields.io/badge/version-v2.1-blue?style=for-the-badge)](https://github.com)
[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-Personal-orange?style=for-the-badge)](#)
[![Platform](https://img.shields.io/badge/Platform-Ubuntu%20%7C%20Debian-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](#)

<br>

**زبان برنامه‌نویسی:** Python 3  
**پنل‌ها:** 3X-UI · Pasargad · Marzban (limited)

</div>

---

## NexusNet چیست؟

NexusNet یک **VPS** را به مجموعه‌ای از **نودهای Tor Exit** تبدیل می‌کند؛ هر نود روی یک کشور خاص تنظیم می‌شود.  
با یک دستور، این نودها به پنل شما (3X-UI / Pasargad) وصل می‌شوند — شامل inbound، outbound SOCKS، routing و host.

| قابلیت | توضیح |
|--------|------|
| 🌍 **بیش از 50 کشور** | Germany, Turkey, US, France, NL, FI, CH و … |
| 🔌 **Panel Tools** | کلون خودکار inbound و host داخل 3X-UI / Pasargad |
| 🔄 **NEWNYM** | مدار و IP خروجی جدید با هر restart |
| 💾 **Backup & restore** | لیست نودها و پورت‌ها در یک فایل |
| 🧹 **Clean delete** | سرویس محلی **و** کانفیگ پنل با هم پاک می‌شود |

---

## پیش‌نیاز

| مورد | پیشنهاد |
|------|---------|
| **Location** | ترجیحاً **Germany 🇩🇪** |
| **CPU** | حداقل 2 هسته |
| **RAM** | حداقل 4 گیگابایت |
| **OS** | Ubuntu / Debian |
| **Access** | Root (`sudo`) |

> **درباره ping:** پینگ نهایی به مسیر شبکه کاربر از طریق Tor بستگی دارد. هرچه مسیر سازگارتر باشد، تأخیر کمتر است.  
> **درباره Exit IP:** در کشورهایی که Exit Node کم دارند (مثل AE)، ممکن است همیشه یک IP ثابت ببینید. از نسخه 1.13 با هر restart، سیگنال `NEWNYM` ارسال می‌شود تا در صورت وجود Exit دیگر، IP عوض شود.

---

## نصب

```bash
curl -sL "https://raw.githubusercontent.com/SiNaKeEn/NexusNet-Node/Multi/install.sh" \
  -o /tmp/install.sh && sudo bash /tmp/install.sh
```

> **نکته:** اگر خطای `Argument list too long` دیدید، حتماً از دستور دو مرحله‌ای بالا استفاده کنید.  
> از `bash -c "$(curl ...)"` برای این فایل استفاده **نکنید**.

بعد از نصب:

```bash
nexusnet
```

---

## منوی برنامه

### منوی اصلی (`nexusnet`)

| # | عملیات |
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

**حالت‌های Host address** (هنگام کلون host در Pasargad):

1. Keep source domain/address *(recommended)*  
2. Server public IP  
3. Custom address  

> **توجه:** آدرس host باید همان آدرسی باشد که **کلاینت به سرور شما وصل می‌شود** (دامنه یا IP خود VPS).

---

## Tech stack

| لایه | تکنولوژی |
|------|----------|
| Core | **Python 3** |
| Networking | Tor, SOCKS5, Xray |
| Panels | 3X-UI (SQLite + API), Pasargad (REST), Marzban (manual SOCKS) |
| Installer | Bash + embedded Base64 payloads |

---

## Backup & restore

- **Backup:** `/root/nexusnet_backup.txt` (nodes + ports)  
- **Restore:** نودهای موجود در فایل که روی سرور نیستند دوباره ساخته می‌شوند  

با حذف نود از گزینه **7**، inbound / outbound / routing / host مربوط در **3X-UI** و **Pasargad** هم تا حد امکان پاک می‌شود.

---

## پشتیبانی

| کانال | لینک |
|-------|------|
| Telegram channel | [@NexusNet_Plus](https://t.me/NexusNet_Plus) |
| Telegram bot | [@NexusNet_PlusBot](https://t.me/NexusNet_PlusBot) |
| Support | [@NexusNet_Sup](https://t.me/NexusNet_Sup) |

---

<div align="center" dir="rtl">

**Based on the T.Sin idea** · Developed by **SiNa (KeEn)**

`nexusnet` · v2.1 · Personal Edition

</div>
