# DECISIONS — Laporan Kemajuan Mingguan

> Keputusan seni bina/teknikal penting sahaja. Tambah di hujung; jangan
> tulis semula sejarah.

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

## 2026-08-24 — Discipline system gantikan classification berasaskan nama

Decision:
Setiap trade dalam Section 5 Manpower kini mempunyai medan eksplisit
`discipline` (Architecture / Infrastructure / Mechanical / Electrical
& ICT / Others) yang dipilih melalui dropdown. `computeTradeActuals()`
mengira berdasarkan `discipline`, bukan berdasarkan sama ada nama
mengandungi kata kunci tertentu. Fail lama tanpa `discipline`
menggunakan kata kunci sebagai fallback (persis peraturan lama, lalu
ditulis semula sebagai backfill). `others` ditambah sebagai catch-all
dalam Trade Summary supaya tiada tenaga kerja tercicir daripada jumlah
dalam apa jua keadaan.

Reason:
Pepijat semula jadi: menaip "INFRASTRUCTURE" sebagai nama level tidak
dikenali oleh `isInfraText()`, jadi tenaga kerja tercicir dari Total
tanpa amaran. Lebih luas, sebarang senarai kata kunci tetap (hardcoded)
adalah berisiko kerana ia tidak meramalkan cara pengguna akan menamakan
trade baharu — dropdown eksplisit lebih kukuh dan boleh ditambah
senarai discipline tanpa mengedit kod. Medan `key` stabil pada Trade
Summary rows (Fix 3) mengelakkan menukar nama baris Section 3 daripada
memutuskan pautan auto.

Rejected:
- Meluaskan `INFRA_KEYWORDS` sahaja tanpa dropdown — memindahkan
  masalah ke kata kunci lain yang mungkin tertinggal (contoh:
  "Piling", "Landscape").
- Membuat auto-match lemah ("Architecture + sesuatu") — terlalu
  automatik tanpa kawalan jelas pengguna.

Rejected:
- (Tiada alternatif praktikal diperlukan untuk medan stabil key —
  ia merupakan penyelesaian standard untuk nama yang boleh di-edit
  tetapi identiti tidak boleh berubah.)
