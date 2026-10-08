# B1connect — Website Company Profile

> **B1connect** adalah middleware integrasi enterprise tingkat lanjut yang menghubungkan toko e-commerce **Shopify** dengan ERP **SAP Business One** secara otomatis, aman, dan real-time.

![B1connect Preview](/og.jpg)

![Astro](https://img.shields.io/badge/Astro-6.4.2-FF5D01?logo=astro&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.14-38B2AC?logo=tailwind-css&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-7.3.3-646CFF?logo=vite&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

---

## 🚀 Mengenai Produk B1connect

B1connect menyelesaikan tantangan integrasi klasik antara platform penjualan online Shopify dan sistem ERP SAP Business One:
- ❌ **Sebelumnya:** Staf gudang dan operasional harus input ratusan order penjualan secara manual setiap hari, rentan typo, serta risiko *overselling* akibat stok tidak sinkron.
- ✅ **Dengan B1connect:** Sinkronisasi inventori, daftar harga, dan katalog produk berjalan otomatis dari SAP ke Shopify, sementara pesanan yang dibayar langsung diterbitkan menjadi Sales Order resmi di SAP Business One dalam hitungan detik.

### Fitur Utama Produk
1. **Bi-Directional Sync:**
   - **SAP → Shopify:** Master item, varian, multi-warehouse stock level, dan price list.
   - **Shopify → SAP:** Sales orders, customer / Business Partner matching, status fulfillment.
2. **Arsitektur Multi-Tenant:**
   - Satu middleware instance dapat melayani banyak toko Shopify sekaligus dengan konfigurasi terisolasi per tenant.
3. **Enterprise Security:**
   - Enkripsi kredensial database & API token dengan algoritma **AES-256-GCM**.
   - Validasi HMAC-SHA256 untuk webhook Shopify dan verifikasi session token.
4. **Resilient Background Processing:**
   - Menggunakan Hangfire dengan antrean job independen, retry otomatis, dan dead-letter queue.
5. **Dashboard & Monitoring:**
   - Visual event stream, HTTP telemetry audit log, dan health check `/health`.

---

## 🌐 Halaman & Navigasi Web Company Profile

Website ini dibangun menggunakan stack ultra-cepat **Astro 6 + Tailwind CSS v4** dengan dark mode bawaan, layout responsif, dan performa Lighthouse 95+:

| Halaman | Rute | Deskripsi |
|---------|------|-----------|
| **Home** | `/` | Hero interaktif, ekosistem ERP, 3 problem statement, 5 pipeline data, 6 fitur unggulan, preview dashboard real-time, skema harga, FAQ, & CTA. |
| **Features** | `/features` | 6 modul detail fitur produk dengan alternating mockups (katalog, webhook, multi-tenant, sekuriti, wizard, monitoring). |
| **How It Works** | `/how-it-works` | Diagram arsitektur visual Shopify ↔ B1connect ↔ SAP, panduan setup 3 langkah, spesifikasi alur data, dan ringkasan tech stack. |
| **Pricing** | `/pricing` | Paket Starter (Rp 1,5 Jt), Business (Rp 3,5 Jt), Enterprise (Custom), tabel komparasi 14 fitur, dan pricing FAQ. |
| **About** | `/about` | Kisah pendirian B1connect, nilai-nilai perusahaan, dan timeline rilis (v0.1 POC hingga Roadmap Q4). |
| **Contact** | `/contact` | Formulir konsultasi & demo, kontak WhatsApp, email resmi, alamat kantor, dan FAQ konsultasi. |
| **Blog** | `/blog` | Artikel wawasan teknis, tutorial integrasi Shopify × SAP, dan best practice keamanan data. |
| **Changelog** | `/changelog` | Catatan rilis versi produk (v1.0.0, v1.1.0, v1.2.0) dengan badge versioning. |
| **404 Not Found** | `/404` | Halaman error 404 ramah pengguna dengan tombol navigasi cepat. |
| **RSS Feed** | `/rss.xml` | Sindikasi konten blog otomatis untuk agregator dan pembaca RSS. |

---

## 🛠️ Tech Stack Web Company Profile

- **Framework:** [Astro 6.4.2](https://astro.build) (Static Site Generation / Content Layer)
- **Styling:** [Tailwind CSS v4.1](https://tailwindcss.com) dengan design tokens di `src/styles/global.css`
- **Animasi & Interaktivitas:** [AOS](https://michalsnik.github.io/aos/) (Scroll reveals) + [motion.js](https://motion.dev/)
- **Icons:** [Lucide Icons](https://lucide.dev/) (`@lucide/astro`)
- **Konten:** MDX (`@astrojs/mdx`) untuk Blog dan Changelog
- **SEO & Feed:** `@astrojs/sitemap`, `@astrojs/rss`, Open Graph, dan Twitter Cards
- **Type Checking:** TypeScript + `astro check`

---

## 💻 Panduan Menjalankan di Lokal (Local Development)

### Kebutuhan Sistem
- **Node.js:** `>=22.12.0`
- **pnpm:** `>=9.0.0`

### 1. Masuk ke Direktori Project
```bash
cd ricoui-saas-template
```

### 2. Install Dependensi (jika belum)
```bash
pnpm install
```

### 3. Konfigurasi Environment (`.env`)
Pastikan file `.env` sudah terbuat di root direktori:
```env
PUBLIC_SITE_URL=https://b1connect.id
```

### 4. Jalankan Dev Server
```bash
pnpm dev
```
Buka browser di `http://localhost:5200` (atau port yang ditampilkan di terminal).

### 5. Validasi Tipe & Build Produksi
```bash
# Validasi TypeScript dan diagnostik Astro
pnpm astro check

# Build static bundle ke folder dist/
pnpm build

# Preview hasil build lokal
pnpm preview
```

---

## 📁 Struktur Direktori Penting

```
ricoui-saas-template/
├── public/                     # Aset statis (og.jpg, favicon.svg, robots.txt)
├── src/
│   ├── collections/            # Data navigasi menu (menu.json) & media sosial
│   ├── components/
│   │   ├── cards/              # Kartu UI (TechStack, dsb.)
│   │   ├── elements/           # Elemen UI reusable (SectionHeader, Badge, Accordion)
│   │   ├── home/               # Komponen spesifik beranda (HeroSection.astro)
│   │   ├── sections/           # Section global (Header, Footer, Pricing, FAQ, BlogSection)
│   │   └── ui/                 # Komponen dasar (Logo.astro, Button.astro, BrowserFrame.astro)
│   ├── config/
│   │   └── site.js             # Konfigurasi nama brand, URL, kontak, dan meta tags
│   ├── content/                # Konten berbasis file
│   │   ├── changelog/          # File MDX rilis (v1.0.0, v1.1.0, v1.2.0)
│   │   └── post/               # Artikel MDX blog dengan subfolder
│   ├── layouts/                # Layout halaman (Layout.astro, Meta.astro, PostLayout.astro)
│   ├── pages/                  # Rute halaman Astro (index, features, pricing, dll.)
│   └── styles/                 # global.css (Tailwind v4 tokens) & styling artikel
└── dist/                       # Output build produksi (statis HTML/CSS/JS)
```

---

## 📝 Mengelola Konten

### Menambah Artikel Blog Baru
1. Buat folder baru di `src/content/post/[slug-artikel]/`
2. Buat file `index.mdx` dengan frontmatter:
```mdx
---
title: "Judul Artikel Anda"
description: "Ringkasan artikel dalam 1-2 kalimat untuk meta description."
publishDate: 2026-10-10
tags: ["shopify", "sap-b1", "tutorial"]
read: 5
img: "/assets/blog/cover.jpg"
img_alt: "Deskripsi gambar"
featured: false
---

Konten artikel Anda dalam format Markdown atau MDX...
```

### Menambah Riwayat Changelog
Buat file baru di `src/content/changelog/[id-versi].mdx`:
```mdx
---
title: "v1.3.0 — Fitur Baru"
publishDate: 2026-10-10
version: "1.3.0"
description: "Ringkasan perubahan versi ini."
---

## Fitur Baru
- Peningkatan sinkronisasi real-time...
```

---

## 🚢 Panduan Deployment

Output `pnpm build` menghasilkan folder statis `dist/` murni tanpa memerlukan node server di runtime:

- **Vercel:** Hubungkan git repository, framework preset otomatis terdeteksi sebagai `Astro`.
- **Netlify:** Build command: `pnpm build`, Publish directory: `dist`.
- **Cloudflare Pages:** Build command: `pnpm build`, Output directory: `dist`.
- **Web Server / Nginx (Self-Hosted):** Copy isi folder `dist/` ke direktori web server Anda (`/var/www/html/`).

---

## 📄 Lisensi
Didistribusikan di bawah lisensi MIT.
© 2026 **B1connect**. Hak Cipta Dilindungi.
