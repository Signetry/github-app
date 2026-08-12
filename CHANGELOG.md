# Changelog — umbra-github-app

Follows [Keep a Changelog](https://keepachangelog.com/) / [SemVer](https://semver.org/).

## [Unreleased]

### Changed

- Rebranded the platform from **Umbra** to **Signetry** across docs, the app
  manifest display fields, and the reviewer workflow. CLI/package renamed
  `umbra`/`umbra-core` → `signetry`/`signetry-core`, env vars `UMBRA_*` →
  `SIGNETRY_*`, config `.umbra/` → `.signetry/`, and siblings `umbra-action` /
  `umbra-reviewer` → `signetry-action` / `signetry-reviewer`. Install pins updated
  to `signetry-core @ git+https://github.com/Signetry/core@v0.6.0` and
  `signetry-reviewer @ git+https://github.com/Signetry/reviewer@v0.1.2`.

## [0.1.0] — 2026-07-26

### Added

- Public home for the Umbra GitHub App: `app-manifest.json` (one-click App
  creation with correct permissions/events/URLs), `README.md`, and `SETUP.md`
  (operator secrets + Cloud Run provisioning). The App itself is served by the
  hosted `umbra` service and governed by `umbra-core` — this repo carries no
  policy logic.
