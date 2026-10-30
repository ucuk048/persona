# Antigravity Persona & Ecosystem Bundles

Repositori resmi distribusi bundle persona, konfigurasi sistem, dan 633 production-grade AI agent skills untuk ekosistem **Antigravity CLI (AGY)** dan **Hermes Agent**.

Repositori ini menyediakan paket siap pasang (*turnkey bundles*) untuk lingkungan **Android (Termux)**, **Desktop/Laptop (Windows, macOS, Linux)**, dan **Hermes Agent (Nous Research)** dengan konfigurasi *always-allow*, persona terkalibrasi, engine optimasi token **RTK**, serta protokol **Universal Zero-Prompting**.

---

## Ringkasan Fitur Inti

- **633 Agent Skills Siap Pakai**: Mencakup seluruh siklus rekayasa perangkat lunak—mulai dari arsitektur backend, modern UI/UX & motion physics, game development 12 engine (Godot, Unity, Unreal, Phaser, Three.js, dll.), manipulasi video & audio deterministik via FFmpeg Suite, perekaman demo via Playwright, audit keamanan kerentanan Cloudflare, engine optimasi token RTK, manipulasi dokumen Office via GenOffice, hingga penulisan naskah akademik berbahasa Indonesia.
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
| `antigravity-hp-bundle.zip` | Android (Termux) | `~/.gemini/` & `/sdcard/Antigravity/` | Konfigurasi Termux lengkap, 633 skills, GEMINI.md, settings.json, installer shell. |
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
4. Konfigurasi dan 633 skills otomatis terpasang pada direktori `C:\Users\<Username>\.gemini\`.

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

## Taksonomi 633 Agent Skills Terpasang

Seluruh 633 skills terindeks dan dikelompokkan ke dalam 16 kluster kapabilitas rekayasa:

```
633 Skills
├── 1. Modern UI/UX, Design Intelligence & Motion Suite (89 Skills)
│   ├── PatternCraft, Transitions.dev, Uiverse UI, FireCMS Neat, FeralUI Gradients
│   ├── CodedVisuals, Beautiful UI, Ryux Design Intelligence, Taste Skill
│   ├── Hallmark, UI UX Pro Max (192 palettes, 119 UX rules), Craftwork (114 vetted design skills)
│   └── Impeccable Design Critique & Huashu Design (84 presentation visual styles)
├── 2. 3D Modeling, Blender Pipeline & Assets (95 Skills)
│   ├── Blender Director, Modeler, Character Artist, Creature Artist, Environment Artist
│   ├── Hard Surface, Sculpting, Retopology, UV & Texture Workflows, PBR Materials
│   ├── Rigging, Animation, Hair Groom, Cloth & Physics Simulation, Geometry Nodes
│   └── Multi-Engine Production Exporters (blender-godot-export, unity-export, unreal-export)
├── 3. Game Development & Multi-Engine Suite (78 Skills)
│   ├── Master Gamedev Router & Architecture Patterns
│   ├── Godot Engine (17 skills: 2D/3D, Physics, Shaders, Headless Testing, Signals)
│   ├── Unity Engine (9 skills: C# Scripting, NavMesh, Tilemaps, Physics, Animation)
│   ├── Unreal Engine 5 (Enhanced Input, Blueprints, C++ Gameplay, Niagara VFX)
│   └── Web & Indie Engines (Phaser, Three.js, Bevy ECS, Ebitengine, Love2D, Pygame, Roblox, Defold)
├── 4. Application Re-engineering & Web Replication (13 Skills)
│   ├── Replica Suite (11 skills: Architect, Recon, Reverse, Backend, Frontend, Diff, Test, Launch)
│   ├── Clone Website (Pixel-perfect web page, asset, and motion reverse engineering)
│   └── Huashu Interactive Canvas & High-Fidelity UI Prototyping
├── 5. Video Engineering, Audio & Demo Walkthrough (2 Skills)
│   ├── FFmpeg Suite (Deterministic local editing: cut, join, 9:16 reframe, captions, LUFS, HDR/SDR)
│   └── Video Demo (Playwright browser walkthrough recording with natural pacing & visible cursor)
├── 6. Security Guardian & Advanced Pentesting / OWASP 2025 (28 Skills)
│   ├── Strix Pentesting Suite (9 skills: OWASP Top 10:2025, API & Web App Security Testing, CI Scanning)
│   ├── Cloudflare Vulnerability Discovery Harness (Official Cloudflare 20 attack classes)
│   └── Security Guardian, Security Review & RTK Shell Escaping Hardening
├── 7. Backend Architecture, REST/GraphQL & Systems (17 Skills)
│   ├── Modular Layered Controller-Service-Repository-Interface Architecture
│   ├── Framework Specialists (FastAPI, NestJS, Laravel, Django, Go, Spring Boot, Nakama Real-time)
│   └── API Design, Error Handling, and Redis Caching Patterns
├── 8. Database Engineering, Migrations & Analytics (6 Skills)
│   ├── PostgreSQL, MySQL, Prisma ORM, JPA Patterns
│   └── Reversible Zero-Downtime Migrations & ClickHouse Analytical Optimization
├── 9. Academic Suite, Indonesian NLP & Naskah (14 Skills)
│   ├── Humanizer-Indonesia (Unrestricted natural phrasing) & Bahasa Peneliti
│   ├── Naskah-ID, Pencari-Skripsi, Zotero Reference Integration & APA 7th Edition Tagging
│   └── Turnitin-Safe Structural Paraphrasing (< 20% similarity floor)
├── 10. DevOps, Docker Patterns & Git Governance (24 Skills)
│   ├── Multi-Stage Minimal Alpine/Distroless Dockerfiles & Docker Compose with Healthchecks
│   └── Git Workflow, Branching Strategy & Caveman Conventional Commits
├── 11. Multi-Agent Systems, Harness & DevFleet (43 Skills)
│   ├── Claude DevFleet, DMux Multi-Session Workflows, ECC Orchestration
│   └── Continuous Autonomous Loops, Evaluator Gates & Subagent Decomposition
├── 12. Engineering Rigor, Debugging & Refactoring (27 Skills)
│   ├── Investigate-First, Systematic Debugging & Root-Cause Tracing
│   └── Surgical Patch (narrowest diff blast radius) & Verify-and-Stop Protocols
├── 13. Testing Strategies & TDD (25 Skills)
│   ├── RTK TDD & Rust TDD (Arrange-Act-Assert, snapshot assertions)
│   └── Multi-Stack Unit & Integration Testing (PyTest, Pest, JUnit 5, Go, xUnit, Playwright E2E)
├── 14. Mobile, Android Reverse Engineering & Hardware (7 Skills)
│   ├── Android Reverse Engineering (JADX decompilation, network tracing, endpoint extraction)
│   └── Android TV Detox, React Native & Mobile Layout Ergonomics
├── 15. AI Memory Continuity, Brand Systems & Scrapers (10 Skills)
│   ├── AI Memory Suite (7 skills: durable pages, handoff, cross-session retrieval, maintenance)
│   ├── Brand Design MD (86 world-class brand design system references)
│   ├── Logo Design Skill (Geometric SVG vector generation with 1,400+ curated references)
│   └── Scrapling (Anti-bot stealth HTTP spider & JS rendering scraping engine)
└── 16. Office Automation & Domain Productivity (155 Skills)
    ├── GenOffice (Programmatic Word .docx, Excel .xlsx, PowerPoint .pptx, PDF manipulation)
    └── Enterprise Business, Legal, Logistics & Domain Task Automation Modules
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
Pastikan seluruh 633 skills terdeteksi aktif dengan status permission `always-proceed`.

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
- [Blender Skills by arjun988](https://github.com/arjun988/blender-skills) (Complete 95-Skill 3D Modeling, Shading, Rigging & Engine Export Pipeline)
- [Replica Skill by Jakeschincariol](https://github.com/Jakeschincariol/replica-skill) (Autonomous Full-Stack System Replication & Web App Reverse Engineering)
- [Strix by usestrix](https://github.com/usestrix/strix) (Autonomous Application Security & OWASP Top 10:2025 Testing Harness)
- [Android Reverse Engineering Skill by SimoneAvogadro](https://github.com/SimoneAvogadro/android-reverse-engineering-skill) (APK/AAR Reverse Engineering & UI Network Tracing)
- [Logo Design Skill by kaankiziltug](https://github.com/kaankiziltug/logo-design-skill) (Geometric SVG Logo Design & 1,400+ Curated References)
- [Huashu Design by alchaincyf](https://github.com/alchaincyf/huashu-design) (High-Fidelity HTML Canvas Interfaces & 84 Visual Presentation Styles)
- [AI Website Cloner Template by JCodesMore](https://github.com/JCodesMore/ai-website-cloner-template) (Production Web Page & Interaction Cloning)
- [AI Memory by akitaonrails](https://github.com/akitaonrails/ai-memory) (Long-term Context Retention, Durable Pages & Cross-Session Handoff)
- [Scrapling by D4Vinci](https://github.com/D4Vinci/Scrapling) (Undetectable HTTP/Spider Web Scraping Engine)
- [Awesome Design MD by VoltAgent](https://github.com/VoltAgent/awesome-design-md) (Curated 86 Brand Design Systems)
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
