# Laporan Kemajuan Mingguan — Hospital Petra Jaya (300 Katil)

Aplikasi laporan kemajuan mingguan untuk **Hospital Petra Jaya (300 Katil)** — BLACKFOX ENGINEERING SDN. BHD.
Single-file HTML app, tiada install, tiada internet diperlukan. Semua data disimpan dalam browser.

> 🔒 **Repo ini PRIVATE** — mengandungi data projek sebenar.

## 📥 Download / Install

1. Pergi ke **[Releases](https://github.com/mohdlukman-maker/laporan-kemajuan-mingguan/releases)**
2. Download `LaporanKemajuanMingguan_v1.0.0.zip`
3. Extract zip ke folder (klik kanan → Extract All)
4. Double-click salah satu fail `.bat`:
   - **`Laporan.bat`** — laporan penuh (penyelaras)
   - **`Editor_WBS.bat`** — editor WBS (staf Work Programme)
   - **`Editor_Gambar.bat`** — editor gambar (staf foto)

Fail `.bat` buka aplikasi dalam Chrome/Edge **app mode** — tiada address bar, nampak seperti aplikasi desktop.

📱 **Telefon**: salin fail `.html` ke telefon, buka dalam Chrome/Safari, menu → *Add to Home screen*.

## 📁 Fail dalam aplikasi

| Fail | Fungsi |
|---|---|
| `Laporan_Kemajuan_Mingguan.html` | Laporan penuh 12 seksyen — untuk penyelaras |
| `Editor_WBS.html` | Editor standalone untuk WBS (Kerja Yang Disiapkan Mingguan) |
| `Editor_Photos.html` | Editor standalone untuk Gambar Kemajuan Mingguan |
| `Laporan.bat`, `Editor_WBS.bat`, `Editor_Gambar.bat` | Launcher mod aplikasi |
| `MULA_SINI.txt` | Arahan guna dalam Bahasa Melayu |

## 👥 Aliran kerja berbilang staf

```
PENYELARAS                    STAF
──────────                    ────
[Simpan Bahagian] ──json──►  [Buka Fail]
                              (kemaskini)
[Muat Naik Bahagian] ◄─json── [Simpan]
```

1. Penyelaras klik **Simpan Bahagian** → pilih `wbs` atau `photos` → dapat fail `.json`
2. Hantar fail `.json` + fail editor HTML kepada staf
3. Staf buka editor, klik **Buka Fail**, kemaskini, klik **Simpan** → dapat fail `.json` baharu
4. Staf hantar fail `.json` balik
5. Penyelaras klik **Muat Naik Bahagian** → pilih fail staf → hanya seksyen tersebut berubah
6. Klik **Simpan / Save** untuk kekal

## ✨ Ciri-ciri

- **12 seksyen laporan** — maklumat, trend, trade summary, work programme, WBS, manpower per task, drawing layout, issues, IPC, equipment, gambar, tanda tangan
- **Donut manual per-trade** — % dimasukkan manual, bukan auto-calc
- **Per-trade column controls** — setiap trade boleh tambah/hapus lajur sendiri
- **Dual donut** (minggu lepas + semasa) dengan butang salin
- **Partial save/import** — seksyen boleh diedit oleh staf berlainan secara berasingan
- **Backward compatible** — fail simpan lama (.html) masih boleh dimuat naik
- **Google Sheets import** — data trend/WBS/manpower/issues/financial/equipment dari CSV
- **Publish** — jana versi pelanggan (edit controls dibuang)
- **Print/PDF** — cetak terus atau simpan sebagai PDF

## 🔧 Teknikal

- Single-file HTML — semua CSS/JS inline, tiada dependencies
- Data disimpan dalam `localStorage` + boleh simpan sebagai fail `.html` (data embedded dalam `<script id="seed-data">`)
- Editor staf simpan sebagai fail `.json` partial (`_partialSection` tag)
- Semua berjalan offline — fail:// protocol, tiada server diperlukan

## 📝 Versi

- **v1.0.0** — awal: task-level manpower, manual donut %, per-trade columns, section separation (Editor WBS + Editor Gambar), app launchers
