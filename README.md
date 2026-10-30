# Antigravity Persona & Ecosystem Bundles

Repositori resmi distribusi bundle persona, konfigurasi sistem, dan 415 production-grade AI agent skills untuk ekosistem **Antigravity CLI (AGY)** dan **Hermes Agent**.

Repositori ini menyediakan paket siap pasang (*turnkey bundles*) untuk lingkungan **Android (Termux)**, **Desktop/Laptop (Windows, macOS, Linux)**, dan **Hermes Agent (Nous Research)** dengan konfigurasi *always-allow*, persona terkalibrasi, serta protokol **Universal Zero-Prompting**.

---

## Ringkasan Fitur Inti

- **415 Agent Skills Siap Pakai**: Mencakup seluruh siklus rekayasa perangkat lunak—mulai dari arsitektur backend, modern UI/UX & motion physics, audit keamanan kerentanan Cloudflare, manipulasi dokumen Office via GenOffice, hingga penulisan naskah akademik berbahasa Indonesia.
- **Universal Zero-Prompting**: Agen secara proaktif mendeteksi kebutuhan konteks tugas dan langsung mengaktifkan modul skill relevan tanpa mengharuskan pengguna mendikte pemanggilan skill satu per satu.
- **Automated Security Audit (Cloudflare Harness)**: Penerapan 20 attack classes, validator, dan checklist OWASP Top 10 langsung dari `cloudflare/security-audit-skill` serta RTK security guardian pada setiap penulisan backend, query database, dan formulir.
- **Universal Anti-Slop Suite & Humanizer-Indonesia**: Penyaringan 6 dimensi (Core, Code, Copywriting, Human, LayoutMobile, UI) untuk mengeliminasi kode generik khas AI dan menghasilkan teks bahasa Indonesia alami berkategori *Turnitin-safe* (< 20%).
- **Izin Global Always-Proceed**: Mode eksekusi alat (`toolPermission`) berstatus *always-proceed* dengan `permissions: ["*"]` untuk eksekusi perintah shell, manipulasi berkas, dan subagent tanpa interupsi konfirmasi berulang.
- **Persona Terkunci Permanen**:
  - **Ponytail (FULL)**: *Lazy Senior Dev Mindset* (YAGNI, pemanfaatan ulang basis kode, standar library first, minimal blast radius diff).
  - **Caveman Voice (FULL)**: *Token Killer Mode* (`[Objek] [Tindakan] [Alasan]. [Langkah berikutnya].`) guna menjaga context window tetap efisien.

---

## Daftar Paket Bundle

Berkas arsip distribusi berada langsung di root repositori:

| Berkas Bundle | Target Lingkungan | Jalur Instalasi Default | Deskripsi Singkat |
| :--- | :--- | :--- | :--- |
| `antigravity-hp-bundle.zip` | Android (Termux) | `~/.gemini/` & `/sdcard/Antigravity/` | Konfigurasi Termux lengkap, 415 skills, GEMINI.md, settings.json, installer shell. |
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
4. Konfigurasi dan 415 skills otomatis terpasang pada direktori `C:\Users\<Username>\.gemini\`.

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

## Taksonomi 415 Agent Skills Terpasang

Seluruh 415 skills terindeks dan dikelompokkan ke dalam 11 kluster kapabilitas rekayasa:

```
415 Skills
├── 1. Modern UI/UX, Design & Motion Suite (PatternCraft, Transitions.dev, Uiverse, Neat, FeralUI, CodedVisuals, Beautiful UI)
├── 2. Security Guardian & Cloudflare Vulnerability Discovery (Cloudflare Security Audit, OWASP Top 10, RTK Guardian)
├── 3. Backend Architecture, REST/GraphQL & Systems (FastAPI, NestJS, Laravel, Django, Go, Spring Boot, Nakama)
├── 4. Database Engineering, Migrations & Analytics (PostgreSQL, MySQL, Prisma, JPA, ClickHouse)
├── 5. Academic Suite, Indonesian NLP & Naskah (Humanizer-Indonesia, Bahasa Peneliti, Naskah-ID, Zotero, Pencari-Skripsi)
├── 6. DevOps, Docker Patterns & Git Governance (Docker Multi-Stage, Git Workflow, Conventional Commits)
├── 7. Multi-Agent Systems, Harness & DevFleet (ECC Orchestration, Claude DevFleet, DMux, Continuous Agent Loops)
├── 8. Engineering Rigor, Debugging & Refactoring (Investigate First, Systematic Debugging, Surgical Patch, Safe Refactor)
├── 9. Testing Strategies & TDD (RTK TDD, E2E Playwright, Browser QA, Go/Python/Rust/Kotlin Testing)
├── 10. Office Automation & Document Engineering (GenOffice: Word .docx, Excel .xlsx, PowerPoint .pptx, PDF)
└── 11. Efficiency, Persona & Anti-Slop Discipline (Ponytail, Caveman Voice, Token Killer, Code Simplifier, Anti-Slop Suite)
```

### Rincian Modul UI & Motion Terbaru
- **`patterncraft`**: Generator 150+ CSS/Tailwind background patterns zero-asset (dot grid, architectural line, radial mesh).
- **`transitions-dev`**: 32+ CSS micro-interactions berbasis token produksi (`t-*` classes, origin dropdown, hover feedback).
- **`transitions-polish`**: Skrip audit otomatis token transisi, kurva easing, dan guard aksesibilitas `prefers-reduced-motion`.
- **`firecms-neat`**: Fluid canvas WebGL dinamis berkinerja tinggi untuk hero sections interaktif.
- **`feralui-gradients`**: Mesh gradient dinamis bernuansa organik retro terkalibrasi spring physics.
- **`uiverse-ui`**: Komponen taktil teruji (glow buttons, animated checkboxes, floating inputs, loaders).
- **`codedvisuals`**: Komposisi visual bento grid, skema data visual, dan grafik interaktif.
- **`beautiful-ui`**: Primitif antarmuka AI-native (thinking accordion, tool chips, streaming text, approval cards).

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
Pastikan seluruh 415 skills terdeteksi aktif dengan status permission `always-proceed`.

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
- [Cloudflare Security Audit Skill](https://github.com/cloudflare/security-audit-skill)
- [RTK by rtk-ai](https://github.com/rtk-ai/rtk)
- [Superpowers by Obra](https://github.com/obra/superpowers)
- [Caveman by Julius Brussee](https://github.com/JuliusBrussee/caveman)
- [Transitions.dev by Jakub Antalík](https://github.com/Jakubantalik/transitions.dev)
- [PatternCraft by Megh Bari](https://github.com/megh-bari/pattern-craft)
- [FireCMS Neat](https://github.com/firecms/neat)
- [Uiverse IO](https://uiverse.io)
- [Beautiful UI](https://github.com/slev12397/beautiful-ui)

Dikelola dan dikurasi oleh **[@ucuk048](https://github.com/ucuk048)**.
