# DOKUMEN SERAH TERIMA SESI (SESSION HANDOFF LEDGER)
## Migrasi Lingkungan: Android Termux (HP) ➔ Laptop / PC (Desktop)

Dokumen ini disusun otomatis menggunakan skill `session-handoff` untuk menjamin transisi mulus tanpa degradasi konteks saat berpindah dari perangkat HP (Termux) ke Laptop/PC.

---

## 1. Metadata Sesi & Lingkungan Asal
- **Waktu Penyusunan**: 2026-11-18 07:20:00 (WITA / UTC+8)
- **ID Percakapan Asal**: `7812630c-a6cf-455a-b06d-0bac277bbef4`
- **Model / Provider Asal**: Antigravity Desktop (Windows 11)
- **Perangkat Asal**: Laptop / PC (Windows 11) & Android Termux Tersinkronisasi
- **Perangkat Tujuan**: Lintas Perangkat (Windows, macOS, Linux, Android Termux, Hermes Agent)
- **Status Repositori Distribusi (`ucuk048/persona`)**:
  - Remote: `https://github.com/ucuk048/persona.git`
  - Branch: `main` (Sinkron dengan origin/main)
  - Berkas Bundle Laptop: [`antigravity-laptop-bundle.zip`](https://github.com/ucuk048/persona/blob/main/antigravity-laptop-bundle.zip)
  - Berkas Bundle Hermes: [`antigravity-hermes-bundle.zip`](https://github.com/ucuk048/persona/blob/main/antigravity-hermes-bundle.zip)
  - Berkas Bundle HP: [`antigravity-hp-bundle.zip`](https://github.com/ucuk048/persona/blob/main/antigravity-hp-bundle.zip)

---

## 2. Ringkasan Eksekutif & Status Terkini Proyek

### A. Ekosistem Antigravity & Persona (776 Skills, 36 Plugins, 18 MCP Endpoints, Auto-Persona Always-On)
- **Suite Baru Terintegrasi (2026-11-18)**:
  - **PaperOrchestra (`google-research/paper-orchestra`)**: Multi-agent 5-tahap (Outline -> Literature -> Section Writer -> Plotting -> Autorater) + template CVPR/ICLR.
  - **Academic Research Skills (`imbad0202/academic-research-skills` v3.24.3)**: `deep-research`, `sr-screener`, `academic-paper`, `academic-paper-reviewer`, `academic-pipeline`.
  - **Laporan Generator v4.0 (`muadzhdz/laporan-generator`) & MenulisCep4t (`FRCHN-GSTN/MenulisCep4t`) & Naskah-ID (`nothinx/naskah-id`)**: Penyunting EYD V/KBBI, cek sitasi OpenAlex/Crossref (`periksa.py` & `openalex.py`), serta native MCP `laporan` untuk kompilasi PDF (Typst) & DOCX (Pandoc/OpenXML) 14 preset kampus.
  - **Humanizer v4.0 (`blader/humanizer`)**: Eliminasi 26+ pola kalimat AI di seluruh bahasa.
  - **Modern Web Guidance (`GoogleChrome/modern-web-guidance-src`) & Chrome DevTools MCP (`ChromeDevTools/chrome-devtools-mcp`)**: 262 fitur Web Platform Baseline, `chrome-extensions`, `web-baseline`, serta 8 skill live debugging Chrome DevTools.
  - **Always-On Auto-Persona Router**: `config/rules/auto-persona-skills.md`, `config/rules/always-on-skills.md`, `config/AGENTS.md`, dan `config/GEMINI.md` memanggil skill otomatis sesuai konteks tanpa perlu diketik manual.
- **Triad Persona Terkunci Permanen**:
  - **Ponytail (FULL)**: *Lazy Senior Dev Mindset* (YAGNI, codebase reuse, standard library first, diff minimal).
  - **Caveman Voice (FULL)**: *Token Killer Voice* (`[Objek] [Tindakan] [Alasan]. [Langkah berikutnya].`).
  - **RTK Engine (FULL)**: *Rust Token Killer & Bash Compression Proxy* (pemangkasan output shell hingga 90%, pengawasan kuota konteks via `rtk gain`, dan orkestrasi 13 modular skills RTK).
- **Protokol Inti Aktif**:
  - **Universal Zero-Prompting Mutlak**: Seluruh domain (Frontend, Backend, Database, Security, Academic, Gamedev, 3D Blender, DevOps, Office, Scraping, Mobile Testing, Browser Automation) aktif otomatis tanpa mendikte pemanggilan skill.
  - **Real-Browser Automation & Cloud Workspace**: FastMCP Browser suite (`fastmcp-browser`, `using-fastmcp-browser`, `automating-google-docs`, `automating-google-sheets`) untuk kendali peramban nyata (Chrome/Firefox) via loopback WebSocket, mitigasi canvas Docs/Sheets, dan semantik digest snapshots.
  - **Modern UI/UX, Craft & Smart Skeletons**: Suite lengkap UI/UX modern dipadukan dengan `unslop` (redesain UI vibecoded, quiet chrome, deliberate spacing) dan `skullet` (smart measured skeletons lintas React/Vue/Svelte/Vanilla JS anti-CLS dari Lochie Axon).
  - **Autonomous Mobile QA & Pentest Remediation**: Artemis suite (build APK, auto-deploy ADB, eksplorasi fitur menyeluruh ala Senior QA, audit OWASP Mobile Top 10, dan pembuatan DEFECT_LEDGER untuk auto-fix surgical-patch Antigravity).
  - **Epistemic Integrity & Security Supremacy**: SANITY v3.0 Protocol (anti-halusinasi militer, 10 pilar integritas epistemik, eliminasi phantom functions & ghost files, sitasi sebelum asersi).
  - **3D Modeling & Blender Pipeline**: 95 skills lengkap (Character Artist, Environment Artist, Hard Surface, Sculpting, Retopology, UV, Shaders, Rigging, Animation, dan Game Exporters ke Godot, Unity, Unreal).
  - **Game Development 12 Engine**: 78 skills (Godot, Unity, Unreal Engine 5, Phaser, Three.js, Bevy, Love2D, Pygame, Roblox, Defold, Mechanics, AI, Level Design).
  - **Application Re-engineering & Replication**: Replica suite (11 skills), Clone Website, Huashu Design (84 gaya visual), Scrapling, dan Android Reverse Engineering (JADX).
  - **Security Guardian & OWASP 2025**: Cloudflare Vulnerability Discovery Harness, Strix Pentesting (9 skills), RTK Security Guardian.
  - **Video & Multimedia Engineering**: FFmpeg Suite (cut, join, 9:16 reframe, captions, LUFS, HDR/SDR) dan Playwright Video Demo.
  - **Universal Anti-Slop Suite & Humanizer-Indonesia**: Unrestricted natural phrasing, Turnitin-safe (< 20%), tagging `[PERLU DATA]`/`[PERLU RUJUKAN]`.
- **Isolasi 3 Bundle Distribusi (~21 MB Bersih)**:
  - `antigravity-hp-bundle.zip`: Dikhususkan untuk Android Termux (`/sdcard/Antigravity/` dan `~/.gemini/`).
  - `antigravity-laptop-bundle.zip`: Bersih total dari path `/sdcard/`, workspace dinamis `./`, installer native multi-OS (`.bat`, `.ps1`, `.sh`).
  - `antigravity-hermes-bundle.zip`: Bersih total dari `/sdcard/`, standard `agentskills.io` dan identitas global `SOUL.md`.

### B. Proyek LMS WordPress Mahasiswa PTIK (Tersimpan & Siap Pakai)
- **Lokasi Proyek**: `/sdcard/Antigravity/lms-wordpress-ptik/`
- **Paket Distribusi**: `/sdcard/Antigravity/lms-wordpress-ptik.zip` (51 MB)
- **Kondisi**: Selesai 100%, Core WordPress + Tutor LMS + Astra + Database SQL + Panduan Dosen.

---

## 3. Langkah Setup Cepat di Laptop / PC Baru

Untuk mengaktifkan lingkungan kerja yang identik di laptop Anda:

### Langkah A: Unduh & Ekstrak Bundle Laptop
1. Ambil berkas `antigravity-laptop-bundle.zip` dari repositori GitHub `ucuk048/persona` (atau via flashdisk/LocalSend dari HP).
2. Ekstrak isi ZIP tersebut ke sebuah folder lokal di laptop Anda.

### Langkah B: Jalankan Installer Otomatis
- **Jika Menggunakan Windows:**
  - Buka PowerShell (Run as Administrator), arahkan ke folder ekstraksi, dan jalankan:
    ```powershell
    .\install.ps1
    ```
    *(Atau klik kanan pada berkas `install.bat` dan pilih **Run as administrator**).*
- **Jika Menggunakan Linux atau macOS:**
  - Buka Terminal dan jalankan:
    ```bash
    chmod +x install.sh
    ./install.sh
    ```
- *Hasil instalasi*: Seluruh **776 skills**, aturan `GEMINI.md`, dan izin *always-allow* otomatis terpasang di direktori konfigurasi laptop (`%USERPROFILE%\.gemini\` di Windows atau `~/.gemini/` di Mac/Linux).

---

## 4. Berkas Kritis & Referensi Kunci

| Nama Berkas | Lokasi di Repositori / Sistem | Fungsi |
| :--- | :--- | :--- |
| `antigravity-laptop-bundle.zip` | Root repo `ucuk048/persona` | Paket instalasi lengkap untuk PC/Laptop (~35.2 MB) |
| `antigravity-hp-bundle.zip` | Root repo `ucuk048/persona` | Paket instalasi lengkap untuk Android Termux (~35.2 MB) |
| `antigravity-hermes-bundle.zip` | Root repo `ucuk048/persona` | Paket instalasi Hermes Agent standard agentskills.io (~35.2 MB) |
| `README.md` | Root repo `ucuk048/persona` | Dokumentasi arsitektur 776 skills & 17 kluster |
| `AGY_COMMANDS.md` | Di dalam bundle laptop / HP | Buku panduan perintah cepat CLI & skill |
| `GEMINI.md` | `laptop_bundle/config/GEMINI.md` | Aturan sistem desktop (bebas path HP) |

---

## 5. Blok Prompt Sambung Sesi di Laptop (Laptop Kickstart Prompt)

> **Petunjuk**: Setelah membuka terminal/CLI di laptop Anda (Gemini CLI / Antigravity / Claude / Cursor), salin seluruh isi teks di dalam kotak kode di bawah ini dan tempelkan sebagai prompt pertama:

```text
Halo! Saya melanjutkan sesi kerja dari HP (Android Termux) ke Laptop.
Seluruh konfigurasi sistem, 776 skills (17 kluster), dan histori pengerjaan telah tercatat pada dokumen `SESSION_HANDOFF.md`.

Instruksi Onboarding Instan di Laptop:
1. Konfirmasi bahwa Anda telah mengenali persona inti yang terkunci permanen:
   - Ponytail (Lazy Senior Dev Mindset / YAGNI / Codebase Reuse / Minimal Patch).
   - Caveman Voice (Terse & High-Signal: [Objek] [Tindakan] [Alasan]. [Langkah berikutnya].).
   - RTK Engine (Token Efficiency & Bash Filter hingga 90%).
2. Terapkan standar kerja Universal Zero-Prompting pada seluruh domain (Frontend, Backend, Database, Security, Blender 3D, Gamedev, Office, Academic).
3. Beroperasi pada direktori kerja proyek desktop (Current Working Directory `./`).
4. Laporkan kesiapan Anda dalam format ringkas Caveman Voice dan tanyakan instruksi tugas berikutnya yang ingin dikerjakan di laptop.
```
