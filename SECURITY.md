# Security policy

The Umbra GitHub App is served by the hosted [`umbra`](https://github.com/bkd-dotcom/umbra)
service and governed by [umbra-core](https://github.com/Signetry/core).
This repo holds the App's manifest and setup docs only.

## Reporting

Open a private security advisory on the relevant repository (`umbra` for the hosted
webhook/token handling, `umbra-core` for governance), or use the umbrella contact:
<https://github.com/Signetry/signetry>. Do not open a public issue for an
unpatched vulnerability.

## Guarantees

- Webhook deliveries are HMAC-verified against the App's webhook secret.
- The installation token is short-lived, read-only for the diff, and comment-only
  to post — never passed to a coding-agent child process.
- The App is **comment-only**; it never merges. `auto_merge` is always false.
