# PROJECT — Laporan Kemajuan Mingguan (Hospital Petra Jaya)

> Stable project reference. Change this file rarely.
> Current state: `STATUS.md`; immediate task: `NEXT_TASK.md`.

## Purpose

Aplikasi **laporan kemajuan mingguan** (weekly progress report) untuk
**Hospital Petra Jaya (300 Katil)** — BLACKFOX ENGINEERING SDN. BHD.
Single-file HTML application; tiada install, tiada internet; semua data
disimpan dalam browser (localStorage) dan dieksport sebagai fail.

## Main objective

Penyelaras projek dan staf boleh mengisi dan melihat laporan kemajuan
mingguan 12-seksyen tanpa sebarang pemasangan — hanya buka fail HTML —
dengan aliran kerja berbilang staf (koordinasi seksyen berasingan).

## Major requirements

- **Single-file HTML**, tiada build step, tiada internet/CDN — mesti
  berfungsi offline sepenuhnya.
- 12 seksyen laporan (termasuk WBS "Kerja Yang Disiapkan Mingguan",
  Gambar Kemajuan, Manpower).
- Aliran kerja berbilang staf: editor standalone (`Editor_WBS.html`,
  `Editor_Photos.html`) untuk staf bahagian tertentu; laporan penuh
  untuk penyelaras; seksyen berasingan supaya staf tak berlanggar
  (feat `ea764bc`).
- Manpower: model task-level (diambil dari Hospital_Petra_Planner),
  donut minggu semasa + minggu lepas, per-trade column manager,
  manual donut %.
- Launcher `.bat` buka Chrome/Edge mod "app" (tiada address bar).
- Telefon: fail HTML boleh dibuka terus, "Add to Home screen".
- Data: import/export melalui fail; simpan dalam browser.

## Technology stack

- **HTML + CSS + vanilla JavaScript sahaja** (single-file apps)
- Tiada framework, tiada build, tiada dependencies, tiada CDN
- Launchers: `.bat` (Windows, Chrome/Edge app mode)
- Bahasa antara muka: Bahasa Melayu

## Architecture

    Laporan_Kemajuan_Mingguan.html   (2691 baris) — app utama: 12 seksyen,
                                     semua logik + UI + storage (localStorage)
                                     + import/export fail
    Editor_WBS.html      (241 baris) — editor standalone WBS untuk staf
    Editor_Photos.html   (275 baris) — editor standalone gambar
    Laporan.bat / Editor_WBS.bat / Editor_Gambar.bat — launcher mod app
    MULA_SINI.txt — arahan guna dalam BM
    README.md — dokumentasi (BM) + pautan Releases

Semua app adalah fail tunggal yang tidak bergantung antara satu sama
lain secara runtime; mereka berkongsi struktur data eksport/import.

## Important constraints

- **Repo PRIVATE — mengandungi data projek sebenar** (nama projek,
  kontraktor, struktur organisasi HPJ). Jangan buat public.
- **Offline-only**: jangan tambah CDN, font luar, API call — app mesti
  terus berfungsi tanpa internet.
- Bahasa antara muka: Bahasa Melayu (kekalkan).
- `.bat` mesti kekal CRLF (konvensyen Windows; lihat juga pengalaman
  bug LF di projek lain).
- Data pengguna tinggal dalam browser pengguna (localStorage) —
  tiada data peribadi disimpan dalam repo.
- Perubahan UI mesti diuji dalam Chrome/Edge sebenar (tiada test
  automatik).

## Supported platforms

- Windows (launcher .bat; sasaran utama) — Chrome/Edge
- Telefon mudah alih (fail HTML terus / Add to Home screen)
- Mana-mana browser moden (fail HTML tunggal)

## Key external dependencies

- Tiada langsung (itu tunjang projek).

## Repository

- GitHub: `mohdlukman-maker/laporan-kemajuan-mingguan` (private)
- Default branch: `main`; tag `v1.0.0` (release zip diedarkan via
  GitHub Releases)
