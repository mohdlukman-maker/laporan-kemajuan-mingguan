# NEXT TASK — Laporan Kemajuan Mingguan

> Tugas seterusnya yang paling wajar. Backlog lebih besar (jika ada)
  kekal dalam GitHub Issues. Status: tiada tugas pembangunan aktif —
  projek stabil v1.0.0; tugas di bawah adalah calon apabila diperlukan.

## Objective

**Tugas default: tiada perubahan kod diperlukan.** Jika pengguna
meminta perubahan, ikut aliran kerja AGENTS.md. Calon tugas pertama
yang paling bernilai:

**Semakan tahunan / versi — pastikan model Manpower laporan selari
dengan Hospital_Petra_Planner.**

## Why it is needed

Model task-level Manpower dalam laporan diambil dari
`Hospital_Petra_Planner` (commit `873d1bb`). Jika planner berkembang,
struktur data export/import laporan mungkin tercicir. Semakan berkala
mengelakkan perpecahan senyap antara dua alat yang berkongsi model.

## Relevant files

- `Laporan_Kemajuan_Mingguan.html` — seksyen 5 (Manpower), struktur
  data export/import
- `C:\Users\mohdl\Desktop\Hospital_Petra_Planner.html` (planner —
  sumber model; alat berasingan, jangan edit melainkan diminta)

## Requirements (jika semakan dijalankan)

1. Bandingkan struktur data Manpower planner vs laporan (kunci JSON,
   nama task, per-trade fields).
2. Jika berpecah: tambah sokongan baca struktur baharu dalam laporan
   secara **backwards-compatible** (data lama masih boleh dibuka).
3. Ujian manual dalam Chrome/Edge: import data sampel lama + baharu.
4. Kekalkan BM untuk semua teks UI.

## Acceptance criteria

- [ ] Laporan boleh membuka export planner semasa tanpa ralat.
- [ ] Export laporan lama (v1.0.0) masih boleh dibuka.
- [ ] Tiada CDN/kenalan internet ditambah (offline kekal).
- [ ] `git status` clean selepas commit.

## Constraints

- Jangan tukar app kepada multi-file/framework — single-file adalah
  tunjang projek.
- Offline-only; BM UI; `.bat` CRLF.

## Things that must NOT be changed unnecessarily

- Struktur 12 seksyen dan aliran staf (WBS/Gambar berasingan).
- localStorage sebagai simpanan utama.
- Nama fail `.bat`/HTML (pengguna sudah ada shortcut).
