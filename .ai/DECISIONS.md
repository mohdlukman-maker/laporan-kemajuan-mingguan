# DECISIONS — Laporan Kemajuan Mingguan

> Keputusan seni bina/teknikal penting sahaja. Tambah di hujung; jangan
  tulis semula sejarah.

## 2026-08-22 — Bootstrap sistem keadaan `.ai/` (dokumen BM + English)

Decision:
Tambah sistem keadaan `.ai/` + `AGENTS.md`. Dokumen keadaan ditulis
dalam campuran BM/English — UI/istilah projek dalam BM (ikut bahasa
app), arahan teknikal dalam English (piawaian aliran kerja agent).

Reason:
Aplikasi ini berbahasa Melayu dan penggunanya staf BM; konteks projek
perlu kekal BM supaya semakan masa depan tidak hilang makna. Arahan
kerja agent kekal English supaya konsisten dengan AGENTS.md repositori
lain.

Rejected:
- Semua English — hilang konteks istilah BM (seksyen, penyelaras,
  staf bahagian) yang dipakai dalam app sebenar.
- Semua BM — piawaian aliran kerja agent merentas semua projek user
  adalah English.

## 2026-08-22 — Status quo: single-file, offline, tanpa ujian automatik

Decision:
Rekod status quo sebagai keputusan sedar (bukan keciciran): kekal
single-file HTML tanpa framework/build/test automatik; pengesahan
adalah ujian manual Chrome/Edge selepas setiap perubahan.

Reason:
Sasaran pengguna ialah staf lapangan dengan PC tanpa internet
pasti — single-file + zero-dependency adalah keperluan, bukan pilihan.
Ujian automatik UI single-file besar bernilai rendah berbanding kos
membangunkannya untuk projek saiz ini.

Rejected:
- Migrasi ke framework (React/Vue) — memecah janji "tiada install,
  tiada internet".
- Playwright/Selenium CI — overkill untuk 3 fail HTML; ujian manual
  mencukupi pada skala ini.
