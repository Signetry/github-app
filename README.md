# umbra-github-app

> **Copyright (c) 2026 Binay Dalai. All rights reserved.**
> This repository is strictly for viewing and contributing to the original project. You may not use, copy, modify, distribute, or commercialize this code for your own personal or commercial projects without explicit written permission. Only the original author retains the right to use and monetize this project.


**The Umbra GitHub App — install-once PR admission review, posted as the App.**

Install once on an account or org (pick repos in GitHub's own UI) and every new
pull request gets one advisory **Admission Decision** comment — verdict, reasons,
and a link to the signed receipt. **Comment-only; Umbra never merges.**

Part of the [Umbra platform](https://github.com/Signetry/signetry).
Governance logic lives in [umbra-core](https://github.com/Signetry/core);
the App is served by the hosted [`umbra`](https://github.com/bkd-dotcom/umbra)
service. This repository is the App's **public home**: its manifest, setup docs,
and configuration — not a second copy of the governance pipeline.

## How it works

1. A single app-level webhook (`POST /api/github/app/webhook`, hosted by `umbra`)
   receives PR events for every installation; each delivery is HMAC-verified.
2. On a reviewable PR, Umbra mints a **short-lived installation token** from the
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
- Governance is `umbra-core`; this repo carries no policy logic.

See [SECURITY.md](SECURITY.md) ·
[umbrella overview](https://github.com/Signetry/signetry).

## License

**Copyright (c) 2026 Binay Dalai. All rights reserved.** This code is not open source. You may not use, copy, modify, distribute, or commercialize it for your own personal or commercial purposes without explicit written permission from the author, who alone retains the right to use and monetize this project. See [CONTRIBUTING.md](CONTRIBUTING.md).
