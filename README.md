<div align="center">

# 📦 STASHLY

**Smart Home & Personal Storage Inventory Management System**

Turn physical clutter into searchable digital vaults. Never spend hours digging through identical storage boxes again.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Flutter%20%7C%20Web-02569B?logo=flutter)](https://stashly.app)
[![Backend](https://img.shields.io/badge/Backend-Node.js%20%7C%20Prisma%20%7C%20PostgreSQL-339933?logo=node.js)](https://stashly.app)
[![Status](https://img.shields.io/badge/Status-Active%20Development-success)]()

[Demo Web App](https://stashly.app) • [Download Android](https://play.google.com) • [Download iOS](https://apple.com) • [Documentation](docs/)

---

</div>

## 📌 The Problem

Most households store belongings in labeled plastic bins or cardboard boxes (e.g., *"Motorcycle Parts"*, *"Winter Clothes"*, *"Holiday Decor"*). As collections grow:
* You end up with **multiple boxes sharing the same label** (e.g., 4 boxes of spare parts).
* Finding a specific nut, bolt, or cable requires tearing apart every single container.
* Household members duplicate purchases simply because they don't remember where items are placed.

## 💡 The Solution: Stashly

**Stashly** maps physical storage into a high-performance digital index:
1. **Container Tracking:** Assign a persistent, unique ID (e.g., `BOX-001`, `BOX-002`) and a scannable QR label to every box.
2. **Reverse Search:** Type any item name (e.g., *"Brake Pads"*), and Stashly immediately tells you the exact box and storage shelf.
3. **Scan-to-Peek:** Scan a box's QR code with your mobile camera to see everything inside without taking off the lid.
4. **Collaborative Households:** Share storage access across family members or roommates with granular access controls.

---

## ✨ Key Features

* **⚡ Instant QR Code Scanning:** Point your phone at any box to inspect contents, add items, or move items between boxes.
* **🔍 Deep Reverse Search:** Sub-second search across item names, descriptions, and custom tags.
* **📍 Location Hierarchy:** Organize items hierarchically: `Household` ➔ `Storage Area` (e.g., Balcony Shelf) ➔ `Container` (e.g., Box #04) ➔ `Item`.
* **👥 Multi-User Households:** Invite family members with role-based permissions (`Owner`, `Admin`, `Member`, `Viewer`).
* **📷 Photo & Tag Indexing:** Attach high-resolution photos and tags to items for visual inventory checks.
* **🖨️ Batch Label Generator:** Export printable PDF sheets of scannable QR labels formatted for home printers.

---

## 🛠️ Tech Stack & Architecture

<div align="center">

| Tier | Technologies |
|---|---|
| **Mobile** | Flutter (Dart) — Android & iOS, `mobile_scanner` for barcode parsing |
| **Web** | React 18, TypeScript, Tailwind CSS, Vite |
| **Backend** | Node.js, Express / Fastify, Prisma ORM |
| **Database** | PostgreSQL with indexed search and relational integrity |
| **Object Storage** | Cloudflare R2 / AWS S3 for item and box imagery |
| **Deployment** | Render, Supabase/Neon PostgreSQL, Docker |

</div>

---

## 💎 Pricing & Commercial Model

Stashly operates on a sustainable Freemium model:

<div align="center">

| Feature | Free Tier | Pro Plan ($2.99/mo or $24.99/yr) |
|---|:---:|:---:|
| **Storage Containers** | Up to 10 boxes | Unlimited |
| **Household Members** | 2 members | Unlimited family sharing |
| **Item Photos** | Low resolution | High-res cloud sync |
| **Export Formats** | Standard PDF | Custom sticker layouts & CSV/Excel export |
| **Expiration & Warranty Alerts** | ❌ | ✅ |
| **Offline-First Sync** | Basic | Advanced Conflict Resolution |

</div>
