# Laporan Kemajuan Mingguan — Hospital Petra Jaya (300 Katil)

Single-file HTML generator for the **Weekly Progress Report** of the Hospital Petra Jaya completion project (BLACKFOX ENGINEERING SDN. BHD.).

## What it is

`Laporan_Kemajuan_Mingguan.html` is a self-contained report (no backend, no build step) that:

- Loads in any browser, editable in place via **Edit Mode**
- Exports a saved copy with all data embedded (`Simpan / Save`)
- Exports a clean **client/published** version (`Published`)
- Imports data from an older saved report (`Muat Naik Data Lama`)
- Refreshes sections from Google Sheets via "Publish to web" CSV URLs
- Prints / exports to PDF (`Print / PDF`)

## Sections

1. Maklumat Laporan (info)
2. Ringkasan Kemajuan Fizikal & Kewangan (Trend Mingguan)
3. Ringkasan Mengikut Disiplin (Trade Summary, with auto-totals from Manpower)
4. Work Programme (derived from WBS data, look-ahead per group)
5. Kerja Yang Disiapkan Mingguan (WBS — edit mode only)
6. Baki Kerja Semasa & Tenaga Pekerja (Manpower Per Task, donut charts)
7. Progress Mengikut Susun Atur Lantai (Drawing Layout gallery + lightbox)
8. Isu & Tindakan (Issues & Actions Register)
9. Prestasi Kewangan — Interim Payment (IPC)
10. Equipment Delivery / Installation
11. Gambar Kemajuan Mingguan (photos gallery + lightbox)
12. Pengesahan dan Tandatangan

## Usage

1. Open the HTML file in a browser.
2. Click **Edit Mode** to edit any cell/section/row in place.
3. **Simpan / Save** downloads a new copy with your changes embedded.
4. Next week, use **Muat Naik Data Lama** to import the previous saved report.

> The Google Sheets refresh is optional — leave the CSV URLs blank if you edit data manually.

## License / visibility

This repository is **public**. Do not commit sensitive client/financial data that should not be public. Prefer editing locally and keep sensitive copies off GitHub.
