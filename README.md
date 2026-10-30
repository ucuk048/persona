# Antigravity Persona & Ecosystem Bundles

Repositori resmi distribusi bundle persona, konfigurasi sistem, dan 505 production-grade AI agent skills untuk ekosistem **Antigravity CLI (AGY)** dan **Hermes Agent**.

Repositori ini menyediakan paket siap pasang (*turnkey bundles*) untuk lingkungan **Android (Termux)**, **Desktop/Laptop (Windows, macOS, Linux)**, dan **Hermes Agent (Nous Research)** dengan konfigurasi *always-allow*, persona terkalibrasi, engine optimasi token **RTK**, serta protokol **Universal Zero-Prompting**.

---

## Ringkasan Fitur Inti

- **505 Agent Skills Siap Pakai**: Mencakup seluruh siklus rekayasa perangkat lunak—mulai dari arsitektur backend, modern UI/UX & motion physics, game development 12 engine (Godot, Unity, Unreal, Phaser, Three.js, dll.), manipulasi video & audio deterministik via FFmpeg Suite, perekaman demo via Playwright, audit keamanan kerentanan Cloudflare, engine optimasi token RTK, manipulasi dokumen Office via GenOffice, hingga penulisan naskah akademik berbahasa Indonesia.
- **RTK (Rust Token Killer) Suite**: Mesin reduksi token agnostik-agen berbasis proxy Rust berkinerja tinggi (<10ms overhead). Memangkas volume keluaran terminal/bash hingga 90% melalui deduplikasi cerdas, pemfilteran log verbose, dan pelacakan metrik token (`rtk gain`). Didukung 13 modul spesialisasi teknis (TDD, audit keamanan shell, simplifikasi kode, audit PR).
- **Universal Zero-Prompting**: Agen secara proaktif mendeteksi kebutuhan konteks tugas dan langsung mengaktifkan modul skill relevan tanpa mengharuskan pengguna mendikte pemanggilan skill satu per satu.
- **Automated Security Audit (Cloudflare Harness & RTK Guardian)**: Penerapan 20 attack classes, validator, dan checklist OWASP Top 10 langsung dari `cloudflare/security-audit-skill` serta RTK security guardian pada setiap penulisan backend, query database, dan formulir.
- **Universal Anti-Slop Suite & Humanizer-Indonesia**: Penyaringan 6 dimensi (Core, Code, Copywriting, Human, LayoutMobile, UI) untuk mengeliminasi kode generik khas AI dan menghasilkan teks bahasa Indonesia alami berkategori *Turnitin-safe* (< 20%).
- **Izin Global Always-Proceed**: Mode eksekusi alat (`toolPermission`) berstatus *always-proceed* dengan `permissions: ["*"]` untuk eksekusi perintah shell, manipulasi berkas, dan subagent tanpa interupsi konfirmasi berulang.
- **Persona Terkunci Permanen**:
  - **Ponytail (FULL)**: *Lazy Senior Dev Mindset* (YAGNI, pemanfaatan ulang basis kode, standard library first, minimal blast radius diff).
  - **Caveman Voice & RTK (FULL)**: *Token Killer Mode* (`[Objek] [Tindakan] [Alasan]. [Langkah berikutnya].`) guna menjaga context window tetap efisien dan bebas fluff.

---

## RTK (Rust Token Killer) & Token Optimization Engine

Ekosistem Antigravity mengintegrasikan **RTK (`rtk-ai/rtk`)** secara mendalam sebagai pilar efisiensi token. RTK bekerja menyaring keluaran perintah sebelum masuk ke konteks LLM dan menyediakan alur kerja rekayasa terstruktur:

### 1. Kapabilitas Proxy & Bash Compression
- **Pemangkasan Hingga 90%**: Menghapus progres bar, log build berulang, dan tumpukan trace tak perlu dari perintah seperti `git`, `cargo`, `npm`, `pytest`, `docker`, dan 100+ utilitas CLI lainnya.
- **Pelacakan Metrik Nyata (`rtk gain`)**: Mengukur penghematan byte keluaran terminal secara transparan (`bytes / 4`) tanpa menambah latensi eksekusi (<10ms).
- **Pemulihan Cepat (`rtk recall`)**: Menyediakan akses kembali ke keluaran mentah tanpa kompresi jika diperlukan investigasi mendalam.

### 2. Rangkaian 13 Modul Spesialisasi RTK
| Modul Skill RTK | Peran & Tanggung Jawab Teknis |
| :--- | :--- |
| `rtk` | **Master Skill**: Orkestrasi token optimization, proxy CLI, pemantauan penghematan via `rtk gain`. |
| `rtk-tdd` | Penegakan TDD (Red-Green-Refactor) idiomatik Rust dengan anyhow/thiserror. |
| `rtk-triage` | Triage mendalam atas isu dan pull request repositori. |
| `security-guardian` | Audit injeksi perintah shell, escaping command line, dan keamanan hook sistem. |
| `code-simplifier` | Penyederhanaan kode verbose menjadi konstruksi idiomatik ringkas tanpa merusak perilaku. |
| `tdd-rust` | Alur TDD Rust terkalibrasi dengan pengujian snapshot Insta dan verifikasi token savings. |
| `design-patterns` | Implementasi pola desain Rust (Newtype, Builder, RAII, Trait Objects, State Machine). |
| `performance` | Benchmarking waktu startup CLI, profiling memori, dan efisiensi konsumsi token. |
| `pr-review` | Review kode terkompresi berformat satu baris per temuan masalah dan rekomendasi solusi. |
| `pr-triage` | Audit pull request terbuka, mitigasi risiko regresi, dan penyusunan draf review. |
| `repo-recap` | Ringkasan padat status cabang, commit terbaru, dan arsitektur repositori. |
| `ship` | Otomasi jalur rilis: pengujian regresi, verifikasi build, commit konvensional, dan bump versi. |
| `issue-triage` | Pembersihan backlog isu, deteksi duplikasi laporan, dan penilaian tingkat keparahan bug. |

---

## Daftar Paket Bundle

Berkas arsip distribusi berada langsung di root repositori:

| Berkas Bundle | Target Lingkungan | Jalur Instalasi Default | Deskripsi Singkat |
| :--- | :--- | :--- | :--- |
| `antigravity-hp-bundle.zip` | Android (Termux) | `~/.gemini/` & `/sdcard/Antigravity/` | Konfigurasi Termux lengkap, 505 skills, GEMINI.md, settings.json, installer shell. |
| `antigravity-laptop-bundle.zip` | PC / Laptop (Win/macOS/Linux) | `~/.gemini/` (Linux/Mac) atau `%USERPROFILE%\.gemini\` (Win) | Paket desktop untuk Gemini CLI / AGY CLI dengan installer multi-OS (`.bat`, `.ps1`, `.sh`). |
| `antigravity-hermes-bundle.zip` | Hermes Agent (Nous Research) | `~/.hermes/skills/` & `~/.hermes/SOUL.md` | Konfigurasi runtime Hermes, standard agentskills.io, SOUL.md, dan AGENTS.md. |

---

## Panduan Instalasi Cepat

### 1. Instalasi di PC / Laptop (Windows)

1. Unduh `antigravity-laptop-bundle.zip` dari repositori ini.
2. Ekstrak arsip ke sebuah folder lokal.
3. Buka PowerShell di folder hasil ekstraksi, lalu jalankan:
   ```powershell
   .\install.ps1
   ```
   *(Atau klik kanan pada berkas `install.bat` dan pilih **Run as administrator**).*
4. Konfigurasi dan 505 skills otomatis terpasang pada direktori `C:\Users\<Username>\.gemini\`.

### 2. Instalasi di PC / Laptop (Linux & macOS)

1. Unduh dan ekstrak `antigravity-laptop-bundle.zip`.
2. Buka terminal di folder hasil ekstraksi:
   ```bash
   chmod +x install.sh
   ./install.sh
   ```
3. Seluruh berkas otomatis terdistribusi ke `~/.gemini/config/skills/` dan `~/.gemini/antigravity-cli/settings.json`.

### 3. Instalasi di Android (Termux)

1. Letakkan berkas `antigravity-hp-bundle.zip` pada penyimpanan `/sdcard/Antigravity/`.
2. Buka Termux, lalu jalankan installer:
   ```bash
   cd /sdcard/Antigravity
   unzip -o antigravity-hp-bundle.zip -d /sdcard/Antigravity/hp_extracted/
   cd /sdcard/Antigravity/hp_extracted
   chmod +x install.sh
   ./install.sh
   ```
3. Konfigurasi otomatis aktif pada `~/.gemini/config/` serta `/sdcard/Antigravity/.agents/skills/`.

### 4. Instalasi pada Hermes Agent (Nous Research)

1. Ekstrak `antigravity-hermes-bundle.zip`.
2. Jalankan skrip pemasangan:
   - **Linux / macOS:** `./install.sh`
   - **Windows:** `.\install.ps1`
3. Skrip otomatis menempatkan seluruh skills di `~/.hermes/skills/` dan mengunci identitas pada `~/.hermes/SOUL.md`.

---

## Taksonomi 505 Agent Skills Terpasang

Seluruh 505 skills terindeks dan dikelompokkan ke dalam 13 kluster kapabilitas rekayasa:

```
505 Skills
├── 1. Modern UI/UX, Design Intelligence & Motion Suite (PatternCraft, Transitions.dev, Uiverse, Neat, FeralUI, CodedVisuals, Beautiful UI, Taste Skill, Hallmark, UUPM, Craftwork, Ryux)
├── 2. Security Guardian & Cloudflare Vulnerability Discovery (Cloudflare Security Audit, OWASP Top 10, RTK Security Guardian)
├── 3. Backend Architecture, REST/GraphQL & Systems (FastAPI, NestJS, Laravel, Django, Go, Spring Boot, Nakama)
├── 4. Database Engineering, Migrations & Analytics (PostgreSQL, MySQL, Prisma, JPA, ClickHouse)
├── 5. Game Development & Multi-Engine Suite (Godot 17 skills, Unity 9 skills, Unreal Engine 5, Web Engines Phaser/Three.js, Ebitengine, Bevy, Love2D, Pygame, Roblox, Defold, Gamedev Router, Game Mechanics, Audio, Level Design, Shaders)
├── 6. Video Engineering, Audio & Demo Walkthrough (FFmpeg Suite: cut, join, 9:16 vertical reframe, captions/karaoke, LUFS loudness, HDR to SDR, multicam sync; Playwright Video Demo)
├── 7. Academic Suite, Indonesian NLP & Naskah (Humanizer-Indonesia, Bahasa Peneliti, Naskah-ID, Zotero, Pencari-Skripsi)
├── 8. DevOps, Docker Patterns & Git Governance (Docker Multi-Stage, Git Workflow, Conventional Commits)
├── 9. Multi-Agent Systems, Harness & DevFleet (ECC Orchestration, Claude DevFleet, DMux, Continuous Agent Loops)
├── 10. Engineering Rigor, Debugging & Refactoring (Investigate First, Systematic Debugging, Surgical Patch, Safe Refactor)
├── 11. Testing Strategies & TDD (RTK TDD, TDD Rust, E2E Playwright, Browser QA, Go/Python/Kotlin Testing)
├── 12. Office Automation & Document Engineering (GenOffice: Word .docx, Excel .xlsx, PowerPoint .pptx, PDF)
└── 13. Efficiency, Token Killer & Anti-Slop (RTK Master, Ponytail, Caveman Voice, Code Simplifier, Performance, Anti-Slop)
```

---

## Verifikasi Instalasi

Setelah menjalankan installer, jalankan perintah CLI:
```bash
agy
```
Lalu ketik perintah bantuan atau status:
```
/skills
```
Pastikan seluruh 505 skills terdeteksi aktif dengan status permission `always-proceed`.

---

## Sinkronisasi & Pembaruan Mandiri

Setiap bundle dilengkapi dengan skrip sinkronisasi otomatis `update_skills.py` (dan wrapper `update_skills.sh` / `update.bat`):
```bash
# Sinkronisasi lokal instan antar-direktori (tanpa memindai ulang git remote)
python3 update_skills.py --sync-only

# Pembaruan komprehensif dari upstream repositori
python3 update_skills.py
```

Skrip ini otomatis memvalidasi integritas `SKILL.md`, menyusun ulang `skills.json`, dan memperbarui seluruh berkas bundle ZIP di direktori distribusi.

---

## Lisensi & Atribusi

Paket konfigurasi dan kumpulan skill ini mengintegrasikan repositori open-source resmi:
- [FFmpeg Skill by kajisho5](https://github.com/kajisho5/ffmpeg-skill) (Deterministic Local FFmpeg Audio & Video Editing Suite)
- [Video Demo by nilbuild](https://github.com/nilbuild/video-demo) (Playwright Web Application Demo & Walkthrough Video Generator)
- [Awesome GameDev Agent Skills](https://github.com/gamedev-skills/awesome-gamedev-agent-skills) (Multi-Engine & Game Development Agent Skills)
- [Design Intelligence by RYUX](https://github.com/ryuxdsgn/design-intelligence)
- [UI UX Pro Max](https://uupm.cc)
- [Hallmark](https://usehallmark.com)
- [Taste Skill](https://tasteskill.dev)
- [Craftwork Design Skills](https://craftwork.design/skills)
- [Impeccable](https://impeccable.style)
- [RTK by rtk-ai](https://github.com/rtk-ai/rtk) (Token Killer CLI, Bash Compression Proxy & Engineering Suite)
- [Cloudflare Security Audit Skill](https://github.com/cloudflare/security-audit-skill)
- [Superpowers by Obra](https://github.com/obra/superpowers)
- [Caveman by Julius Brussee](https://github.com/JuliusBrussee/caveman)
- [Transitions.dev by Jakub Antalík](https://github.com/Jakubantalik/transitions.dev)
- [PatternCraft by Megh Bari](https://github.com/megh-bari/pattern-craft)
- [FireCMS Neat](https://github.com/firecms/neat)
- [Uiverse IO](https://uiverse.io)
- [Beautiful UI](https://github.com/slev12397/beautiful-ui)

Dikelola dan dikurasi oleh **[@ucuk048](https://github.com/ucuk048)**.
