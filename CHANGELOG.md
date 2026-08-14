# Changelog — signetry-github-app

Follows [Keep a Changelog](https://keepachangelog.com/) / [SemVer](https://semver.org/).

## [Unreleased]

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
