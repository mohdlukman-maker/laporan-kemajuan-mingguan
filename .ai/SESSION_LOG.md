# SESSION LOG — Laporan Kemajuan Mingguan

> Satu entri setiap sesi pembangunan bermakna, terbaru di atas.

---

## 2026-08-24 — Fix manpower auto-tallies (discipline + Others + stable keys)

- **Objektif:** Perbaiki pepijat di mana menambah/mengedit tenaga
  kerja di peringkat Infrastructure tidak mengemaskini jumlah dalam
  Trade Summary.
- **Punca sebenar ditemui:** `isInfraText()` tidak mengenali kata
  "INFRASTRUCTURE" sendiri (hanya DRAIN/SEWER/ROADWORK/CARPARK);
  `computeTradeActuals()` menggugurkan sebarang trade yang tidak
  sepadan tanpa amaran.
- **Kerja siap:**
  - Fix 1a: Sistem `disciplineOf()` dengan senarai `TRADE_DISCIPLINES`
    + `INFRA_KEYWORDS` diperluas untuk "INFRASTRUCTURE"/"INFRA ".
  - Fix 1b: Dropdown Disiplin pada setiap trade card (Edit Mode).
  - Fix 2: Bakul "Lain-lain (Others)" + baris auto dalam Section 3;
    hint BM dikemaskini.
  - Fix 3: Trade Summary rows diberi `key` stabil + `auto` flag —
    menukar nama baris tidak memutuskan pautan auto.
  - Fix 5: Level/trade rename `onchange` ditambah `;render()`.
  - `addLevel()` + `addTrade()` menghasilkan trade dengan discipline
    default.
  - `normalizeManpowerData()` mengisi discipline untuk fail lama
    (backfill + migrasi).
- **Ujian dilakukan (browser):**
  - Fresh open → Total 191 (tiada regression, identik v1.0.0).
  - +20 manpower di Drainage → Infra 20, Total 211.
  - Tukar discipline ke Others → Others 20, Total 211.
  - Rename Section 3 row → still auto.
  - Padam + tambah row → row baharu manual (tiada double-count).
  - Level rename → totals kekal stabil.
- **Keputusan:** Lihat DECISIONS.md 2026-08-24 (discipline system;
  unstable-name classification ditinggalkan sepenuhnya).
- **Commit:** `feat(manpower):` — push ke origin/main.
