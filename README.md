# GSM Missed Call Dialer — Releases

**Public download and auto-update feed only.** This repository does not contain application source code.

## What this is

- **Windows portable builds** of [GSM Missed Call Dialer](https://github.com/rvignesh123/gsm-missed-call-dialer) are published under [Releases](https://github.com/rvignesh123/gsm-missed-call-dialer-releases/releases).
- The app uses **electron-updater** and reads **`latest.yml`** from the latest GitHub Release to check for updates.
- **License activation** is handled separately (Supabase); this repo only hosts installers and the update manifest.

## Download

Go to **[Releases](https://github.com/rvignesh123/gsm-missed-call-dialer-releases/releases)** and download the latest **`GSM.Missed.Call.Dialer.x.x.x.exe`** (portable).

## For maintainers — publishing a new version

1. Build the portable in the **source** repo: `npm run dist` → `dist/GSM.Missed.Call.Dialer.<version>.exe`.
2. Regenerate **`dist/latest.yml`** (SHA512 base64 + file size must match the `.exe`).
3. On GitHub: **Releases → Draft a new release** → tag **`v<version>`** (e.g. `v1.4.2`).
4. Attach:
   - `GSM.Missed.Call.Dialer.<version>.exe`
   - `latest.yml`  
   Filenames must match the `url` and `version` fields inside `latest.yml` (dots, no spaces — required for `electron-updater` + GitHub).
5. Optionally commit the new **`latest.yml`** in this repo (root) for a public record — **do not** commit `.exe` files (see `.gitignore`).

## Repository layout

| File        | Purpose |
|------------|---------|
| `latest.yml` | Committed copy of the update manifest (optional mirror; **authoritative** copy is the asset on the latest Release). |
| `README.md`  | This page. |

---

**Author:** Vignesh Rajasekar
