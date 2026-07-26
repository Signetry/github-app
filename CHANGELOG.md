# Changelog — umbra-github-app

Follows [Keep a Changelog](https://keepachangelog.com/) / [SemVer](https://semver.org/).

## [0.1.0] — 2026-07-26

### Added

- Public home for the Umbra GitHub App: `app-manifest.json` (one-click App
  creation with correct permissions/events/URLs), `README.md`, and `SETUP.md`
  (operator secrets + Cloud Run provisioning). The App itself is served by the
  hosted `umbra` service and governed by `umbra-core` — this repo carries no
  policy logic.
