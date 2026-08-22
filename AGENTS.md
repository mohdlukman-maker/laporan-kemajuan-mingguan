# AGENTS.md — Laporan Kemajuan Mingguan (Hospital Petra Jaya)

Fail ini menentukan cara agent AI (Hermes, Claude, Codex, …) bekerja
dalam repositori ini. **Baca sebelum menyentuh apa-apa.**

## Projek dalam satu perenggan

Aplikasi laporan kemajuan mingguan **Hospital Petra Jaya (300 Katil)**
(BLACKFOX ENGINEERING) — tiga app HTML single-file (laporan penuh 12
seksyen + editor WBS + editor gambar), launcher `.bat` mod app, semua
offline, data dalam browser (localStorage), antara muka Bahasa Melayu.
**Repo PRIVATE — mengandungi data projek sebenar.**

## Before Starting Work

Sentiasa, ikut tertib:

1. Baca `AGENTS.md` (fail ini).
2. Baca `.ai/PROJECT.md`.
3. Baca `.ai/STATUS.md`.
4. Baca `.ai/NEXT_TASK.md`.
5. Baca `.ai/DECISIONS.md`.
6. Semak `git status`.
7. Semak commit terkini (`git log --oneline -10`).
8. Semak GitHub Issues/PR berkaitan jika ada.
9. Periksa kod sebenar sebelum membuat andaian.

**Jangan andaikan sesi AI sebelum ini betul.** App ini tiada ujian
automatik — sahkan dengan membuka app dalam Chrome/Edge.

## Environment

Tiada install. Bina tiada. Semakan:
buka fail HTML dalam Chrome/Edge secara terus (atau jalan `.bat`).
Pastikan tiada konsol error (F12 → Console).

## During Development

- Perubahan terkecil yang munasabah; kekalkan fungsi sedia ada.
- **Single-file HTML kekal** — jangan pecah kepada berbilang fail,
  jangan tambah framework, jangan tambah CDN/font/API luar.
  **Offline ialah keperluan keras.**
- Bahasa UI: **Bahasa Melayu** (kekalkan istilah sedia ada:
  penyelaras, staf bahagian, seksyen).
- Data pengguna dalam localStorage — jangan tukar skema storage tanpa
  migrasi backwards-compatible (data staf sedia ada mesti kekal boleh
  dibuka).
- `.bat` mesti kekal CRLF.
- Jangan commit data pengguna sebenar, gambar projek sebenar, atau
  apa-apa rahsia. Hanya fail app/dokumentasi yang di-track.
- Jangan padam fail penting tanpa pengesahan eksplisit.
- Sahkan perubahan: buka app dalam Chrome/Edge, uji seksyen yang
  diubah + import/export fail data.

## Before Ending Work

Sentiasa, ikut tertib:

1. Uji manual dalam Chrome/Edge (konsol tiada error; seksyen berubah
   berfungsi; import/export sah).
2. Kemas kini `.ai/STATUS.md` (fakta tersah sahaja).
3. Kemas kini `.ai/NEXT_TASK.md`.
4. Kemas kini `.ai/SESSION_LOG.md`.
5. Rekod keputusan penting dalam `.ai/DECISIONS.md`.
6. Semak `git status` / `git diff` sepenuhnya.
7. Pastikan tiada rahsia/data sensitif di-commit.
8. Commit dengan mesej bergaya conventional (`feat:`, `fix:`,
   `refactor:`, `docs:` …) — sejarah repo guna `feat(ui):`,
   `feat(manpower):` dsb.; kekalkan.
9. Push ke `origin main` bila kerja disahkan.
10. Pastikan working tree bersih.

## Commit message style

    feat(manpower): per-trade column manager
    fix(ui): fix column overflow in edit mode trade cards
    docs: update MULA_SINI instructions

## Hard rules

- Repo kekal **PRIVATE** (data projek sebenar). Jangan tukar
  visibility tanpa kebenaran eksplisit.
- Operasi memusnahkan (`rm -rf`, `git reset --hard`, `git clean -fd`,
  force push, padam repositori/branch) perlukan kebenaran manusia
  eksplisit untuk operasi tersebut.
- Jangan edit `Hospital_Petra_Planner.html` (alat berasingan di
  Desktop) melainkan diminta — planner ialah sumber model, bukan sebah
  agian repo ini.
