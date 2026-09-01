# signetry-github-app

[![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](LICENSE)

**The Signetry GitHub App — install-once PR admission review, posted as the App.**

Install once on an account or org (pick repos in GitHub's own UI) and every new
pull request gets one advisory **Admission Decision** comment — verdict, reasons,
and a link to the signed receipt. **Comment-only; Signetry never merges.**

Part of the [Signetry platform](https://github.com/Signetry/signetry).
Governance logic lives in [signetry-core](https://github.com/Signetry/core);
the App is served by the hosted [`signetry`](https://github.com/Signetry/core)
service. This repository is the App's **public home**: its manifest, setup docs,
and configuration — not a second copy of the governance pipeline.

## How it works

1. A single app-level webhook (`POST /api/github/app/webhook`, hosted by `signetry`)
   receives PR events for every installation; each delivery is HMAC-verified.
2. On a reviewable PR, Signetry mints a **short-lived installation token** from the
   App's private key, reads the diff, runs the admission review (comment-only), and
   posts one comment.
3. The installation token is read-only for the diff and comment-only to post — it
   is **never** passed to a coding-agent child process.

There are no per-repo webhooks and no stored user token.

## Create the App (one click)

Use the manifest flow: GitHub can create the App from
[`app-manifest.json`](app-manifest.json) with the correct permissions
(Pull requests: write · Contents: read · Metadata: read), events (`pull_request`,
`installation`, `installation_repositories`), and the hosted webhook/setup URLs
pre-filled. Then generate a private key and provision the secrets.

Full operator setup (secrets, Cloud Run): [SETUP.md](SETUP.md).

## Guarantees

- **Never merges.** `auto_merge` is always false — a human merges.
- The comment restates the signed receipt; it never claims more than the receipt.
- Governance is `signetry-core`; this repo carries no policy logic.

See [SECURITY.md](SECURITY.md) ·
[umbrella overview](https://github.com/Signetry/signetry).

## License

[Apache-2.0](LICENSE). Use it, fork it, ship it commercially — no strings.

This repository is part of Signetry's [open-core model](https://github.com/Signetry/signetry/blob/main/LICENSING.md):
the **integration surface is Apache-2.0** so anyone can add an agent, an editor, or a
CI adapter, while the engine ([`Signetry/core`](https://github.com/Signetry/core)) is
source-available under BUSL-1.1 and converts to Apache-2.0 on 2030-08-31.

Contributions are accepted under the [CLA](CLA.md) — it lets us move a well-built
adapter into the engine later without asking every contributor for permission again.
