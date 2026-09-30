# Prompt Shorthand Analyzer V3.2

> **Aplikasi Web Cerdas Analisis Prompt Semantik, Rekomendasi Notasi Shorthand Visual, dan Preservasi Identitas (Generasi V3.2).**
> **Arsitektur: SAFE PATCH-ONLY ARCHITECTURE &bull; Basis / Source of Truth: Prompt Shorthand Analyzer V3.1 (Stable Base).**

[![Version: 3.2.0](https://img.shields.io/badge/Version-3.2.0-blue.svg)](package.json)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Architecture: Safe Patch-Only](https://img.shields.io/badge/Architecture-Safe%20Patch--Only-orange.svg)](#arsitektur-safe-patch-only)
[![BYOK Gemini](https://img.shields.io/badge/Gemini%20API-BYOK%20Enabled-blueviolet.svg)](https://aistudio.google.com/)

---

## 🏛️ Fitur Unggulan Baru V3.2: ✨ PERKAYA DENGAN AI

Pada bagian **PROMPT OPTIMAL**, tersedia tombol baru:
`✨ PERKAYA DENGAN AI`

- **Prinsip Utama**: *"ENRICH, NOT REPLACE"*. Prompt Optimal asli adalah SOURCE OF TRUTH.
- **Kondisi Tombol**: Aktif hanya ketika Gemini API Key terhubung; disabled dengan indikator jelas saat belum terhubung.
- **Preservasi Mutlak**: AI tidak mengubah subjek, objek, aktivitas, maksud, batasan, maupun kode shorthand yang terpasang.
- **Peningkatan Kualitas**: AI memperkaya deskripsi visual, tekstur, pencahayaan alami/sinematik, atmosfer, dan koherensi komposisi untuk generator gambar AI.
- **Penyajian Terpadu**: Hasil pengayaan langsung ditampilkan pada kolom Prompt Optimal yang sama tanpa memakan ruang vertikal tambahan.

---

## 🏛️ Prinsip Dasar & Source of Truth

Proyek ini dibangun dengan mematuhi hierarki stabilitas yang ketat:
1. **Prompt Shorthand Analyzer V3 (v3.0.0-stable) sebagai BASIS / SOURCE OF TRUTH**:
   - Seluruh kode, struktur direktori, UI, fitur Kamus Shorthand, deduplikasi semantik, rekomendasi resolusi `/highresolution`, box Saran Solusi pada Shorthand Konflik, dan Default-Hide pada Shorthand Dikecualikan dipertahankan 100%.
   - V3 ditandai sebagai versi stabil (`v3.0.0-stable`) dan tidak diubah/dirusak (`prompt-shorthand-analyzer-v3/` tetap bersih dan utuh).
2. **Tidak Rebuild dari Nol**:
   - Fondasi V3.1 mewarisi seluruh stabilitas, optimasi responsif, dan 239 skenario uji bawaan V3.
3. **SAFE PATCH-ONLY ARCHITECTURE**:
   - Semua modifikasi, aturan tambahan, perbaikan, dan fitur baru di masa mendatang **HANYA** diterapkan pada V3.1 melalui sistem patch modular terisolasi (`src/patches/`).
   - Setiap patch dibungkus pelindung eksekusi aman (`safeExecuteHook`) sehingga kegagalan patch tidak akan pernah merusak sistem inti atau memicu crash.

---

## 🚀 Fitur Lengkap Warisan V3 Stabil (100% Preserved)

- **📚 Kamus Shorthand Terpadu**:
  - Kolom pencarian tunggal cerdas untuk katalog lokal dan online fallback.
  - Alur kerja berkelanjutan (Search &rarr; Tambah `[+]` &rarr; Search Lagi &rarr; Batch Copy).
  - Deduplikasi fungsi semantik cerdas: hanya menampilkan satu shorthand representatif terbaik untuk fungsi yang setara.
- **💡 Box Saran Solusi pada Shorthand Konflik (Card G)**:
  - Rekomendasi kontekstual cerdas pada setiap pertentangan direktif (misal: lock vs edit atau direktif bertolak belakang).
  - Tombol aksi resolusi presisi: memilih salah satu atau melepaskan kunci secara instan.
- **👁️ Fitur Show/Hide pada Shorthand Dikecualikan (Card H)**:
  - Default Hide saat render awal agar tidak memakan ruang vertikal pada layar utama.
  - Tombol toggle `[ 👁️ Tampilkan / Show ]` & `[ 🙈 Sembunyikan / Hide ]`.
- **Pipeline Analisis Semantik Menyeluruh**:
  - `User Prompt` &rarr; `Normalisasi` &rarr; `Semantic Intent` &rarr; `Ekstraksi Area & Entitas` &rarr; `Edit vs Lock Intent` &rarr; `Deteksi Konflik` &rarr; `Pemetaan Shorthand` &rarr; `Rekomendasi Berjenjang` &rarr; `Prompt Optimal`.
- **Preservasi & Lock Cerdas**:
  - Deteksi akurat instruksi preservasi: misal *"hapus hijab, jangan ubah wajah"* secara presisi memasang `/headwear-remove` dan `/facelock`.
- **Rekomendasi Berjenjang (WAJIB, DISARANKAN, OPSIONAL)**:
  - Pembagian tegas antara Primary (aktif otomatis) dan Related Shorthand.
- **Centralized BYOK (Bring Your Own Key) Gemini API**:
  - Mendukung Google Gemini API (model `gemini-2.5-flash`, `gemini-2.5-pro`, `gemini-2.0-flash`, `gemini-1.5-flash`).
  - Fallback otomatis ke heuristik lokal jika offline atau tanpa API Key.
- **Katalog Lengkap & Interaktif**:
  - 58 notasi shorthand terverifikasi, persistensi IndexedDB, filter kategori, dan ekspor/impor aman.

---

## 🛡️ Struktur Proyek V3.1

```
prompt-shorthand-analyzer-v3.1/
├── index.html
├── package.json               # v3.1.0
├── vite.config.js
├── src/
│   ├── main.js                # State Management & App Controller
│   ├── components/            # UI Components (Analyzer, Dictionary, Catalog, etc.)
│   ├── data/                  # Knowledge Base & Shorthand Catalog
│   ├── lib/                   # Semantic Engine & Intent Analyzers
│   ├── patches/               # Safe Patch-Only Extension Modules
│   ├── services/              # Gemini API, Dictionary Service, Catalog Repo
│   └── styles/                # CSS Design System & Responsive Tokens
└── test/
    └── run-tests.js           # Test Suite (239+ automated assertions)
```

---

## 💻 Menjalankan Aplikasi

```bash
# Menjalankan development server
npm run dev

# Menjalankan pengujian otomatis (293 tests)
npm test

# Build production web bundle
npm run build

# Sinkronisasi asset web ke Android
npm run android:sync

# Build Android APK Debug
npm run android:apk:debug

# Build Android APK Release
npm run android:apk:release
```

---

## 📱 Aplikasi Android (APK Wrapper V3.2)

- **Package ID**: `com.sevenprojectchannel.promptshorthand.v32`
- **Application Name**: `Prompt Shorthand Analyzer V3.2`
- **Version**: `versionName = 3.2` | `versionCode = 320`
- **Arsitektur**: Native Android WebView Hybrid Wrapper (mendukung online GitHub Pages dan fallback offline lokal otomatis).
- **File APK Tersedia** pada folder `apks/`:
  - `Prompt-Shorthand-Analyzer-v3.2-debug.apk` (Debug APK)
  - `Prompt-Shorthand-Analyzer-v3.2-release.apk` (Release APK)
- **Fitur Khusus Android**:
  - Pull-to-refresh (`SwipeRefreshLayout`)
  - Tombol Back hardware Android dengan history navigasi (`OnBackPressedDispatcher`)
  - Indikator koneksi internet & layar error ramah pengguna dengan tombol *"Coba Lagi"* dan *"Mode Offline (Lokal)"*
  - Dukungan rotasi Portrait & Landscape tanpa me-reload aplikasi atau menghilangkan input prompt pengguna
  - Penyimpanan BYOK Gemini API Key di dalam secure Web Storage perangkat (tanpa hardcode key)

