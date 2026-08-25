# STATUS — Laporan Kemajuan Mingguan

> Snapshot of CURRENT VERIFIED state. Updated at the end of every
> meaningful session. Last verified: 2026-08-24.

## Overall completion state

**v1.1.0** — Discipline system + Others catch-all + stable Trade
Summary keys. `feat(manpower):` commit pushed to main.

## Verified facts (2026-08-24, browser-verified)

- Fresh open of Laporan_Kemajuan_Mingguan.html: Total 191, all 4
  discipline buckets correct, 0 Others (no regression from v1.0.0).
- Add manpower at INFRASTRUCTURE level → Infra row auto-updates.
- Discipline dropdown moves manpower between buckets live.
- "Lain-lain (Others)" row appears in Section 3 when Others > 0.
- Rename Section 3 row ("Infrastructure"→"Infra Works") → still
  auto; key is stable, not name-based.
- Delete + re-add Section 3 row → new row is manual by default.
- Level/trade rename inputs trigger render() → totals update.
- No console errors.

## Completed components

- Same as v1.0.0, plus:
- Explicit discipline per trade (dropdown: Architecture / Infrastructure /
  Mechanical / Electrical & ICT / Others) — seeded by name fallback
  for old files; new trades default to Others.
- `INFRASTRUCTURE` added to `INFRA_KEYWORDS` (so bare "INFRASTRUCTURE"
  level name now classified as infra, not silently dropped).
- Trade Summary rows keyed by stable `key` + `auto` flag — renaming
  rows or levels never breaks the auto-link.
- "Lain-lain (Others)" catch-all row in Section 3 — visible, tallied
  into Total.
- Level and trade rename handlers include `;render()`.

## Currently in development

- None — fix complete.

## Known bugs / limitations

- Trade % in Trade Summary (Schedule) still filled manually.
- No automated tests (browser-verified only).

## Known risks

- Single-file app now ~2760 lines — manual Chrome/Edge testing
  remains mandatory after any change.

## Current branch / last meaningful commit

- Branch: `main` (tracks `origin/main`)
- Last commit: `feat(manpower):` — discipline + Others + stable keys
- Remote: `https://github.com/mohdlukman-maker/laporan-kemajuan-mingguan.git`
  (private), in sync
