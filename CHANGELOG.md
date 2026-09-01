# Changelog — signetry-github-app

Follows [Keep a Changelog](https://keepachangelog.com/) / [SemVer](https://semver.org/).

## [Unreleased]

### Changed — Signetry is now open core; this repo is Apache-2.0

- An [Apache-2.0](LICENSE) **LICENSE** file is now present, replacing the previous
  "All Rights Reserved" terms, as part of Signetry's
  [open-core model](https://github.com/Signetry/signetry/blob/main/LICENSING.md). The
  integration surface is Apache-2.0 — fork the App, run your own instance, ship it
  commercially — while the engine
  ([`Signetry/core`](https://github.com/Signetry/core)) is source-available under
  BUSL-1.1 and converts to Apache-2.0 on 2030-08-31.
- The all-rights-reserved framing is gone from `README.md`, `CONTRIBUTING.md`,
  `CLA.md`, `CONTRIBUTORS.md`, and the CLA workflow's PR comment.
- `CONTRIBUTING.md` now states the two properties any change here must preserve: the
  App is **comment-only**, and its comment never claims more than the signed receipt
  does.
- **The CLA is kept**, and its fallback licence grant is now **non-exclusive** so a
  contributor never loses the right to use their own contribution. See
  [CLA.md](CLA.md) §2–3.

### Added — community health files

- `CODE_OF_CONDUCT.md` (Contributor Covenant v2.1) and GitHub issue templates.

### Changed

- Signetry naming across docs, the app manifest display fields, and the reviewer
  workflow: CLI/package `signetry`/`signetry-core`, env vars `SIGNETRY_*`, config
  `.signetry/`, and siblings `signetry-action` / `signetry-reviewer`. Install pins
  are `signetry-core @ git+https://github.com/Signetry/core@v0.6.0` and
  `signetry-reviewer @ git+https://github.com/Signetry/reviewer@v0.1.2`.

## [0.1.0] — 2026-07-26

### Added

- Public home for the Signetry GitHub App: `app-manifest.json` (one-click App
  creation with correct permissions/events/URLs), `README.md`, and `SETUP.md`
  (operator secrets + Cloud Run provisioning). The App itself is served by the
  hosted `signetry` service and governed by `signetry-core` — this repo carries no
  policy logic.
