# jarvis-data

Public data bundles for the **Jarvis — Boss the Mentor** Android app
(`com.abdulahadlawfirm.jarvis`).

This repository contains ONLY public court documents and data derived from
them: published judgements of the Khipro courts, learning judgements,
court-scene audio, and Sindh High Court / district cause lists. No secrets,
no credentials, no client data.

## How the app updates

- `manifest.json` (on the `main` branch) describes the current bundle:
  version, date, file name, SHA-256, and counts.
- The moving release tag **`data-latest`** carries the bundle zip
  `jarvis-data-bundle-<date>.zip` and a copy of `manifest.json`.
- The app checks the manifest on launch and once a day in the background,
  downloads the bundle, verifies the SHA-256, and imports it atomically
  (the old data is kept if anything fails).

Bundles are rebuilt by the standing twice-daily cause-list job and the
weekly judgement/learning jobs.
