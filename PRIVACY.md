# Privacy Policy

_Last updated: 2026-08-12_

This policy explains what data the Signetry GitHub App accesses, what it does with
that data, and what it does not do. It is written to be honest and specific to how
this app actually works: it performs comment-only admission review on pull requests
and never merges them.

## What the app accesses

The app operates only on the accounts, organizations, and repositories where an
owner has explicitly installed it, and only within the permissions granted at
install time:

- **Pull requests (read and write):** pull request metadata (title, author,
  branch, state) and the ability to post advisory review comments.
- **Contents (read-only):** the file contents and diff of a pull request under
  review, so the admission review can reason about the proposed change.
- **Metadata (read-only):** basic repository metadata GitHub exposes to all apps.

The app subscribes to `pull_request`, `installation`, `installation_repositories`,
and `marketplace_purchase` events. Installation events tell the app which
repositories it covers. Marketplace events tell the app about purchases,
cancellations, and plan changes for billing.

## What the app does with it

When a reviewable pull request is opened or updated, the app mints a short-lived
installation token, reads the diff, runs an admission review, and posts **one
advisory comment** containing a verdict, the reasons for it, and a link to a signed
receipt. The comment restates the receipt and claims nothing beyond it.

The app is **comment-only**. It never merges, never enables auto-merge, and never
pushes code. A human always decides whether to merge.

## What the app does not do

- It does **not** store your code beyond the duration of a review. Diffs are read
  to produce the review and are not retained as a durable copy afterward.
- It does **not** sell, rent, or share your data with third parties for marketing
  or advertising.
- It does **not** pass its installation token to any coding-agent child process.

## Model calls and bring-your-own-key

Any calls to a language model use a **bring-your-own-key** model: the operator
supplies their own model provider credentials. The app does not send your code to a
model provider using Signetry-owned keys, and it does not use your data to train
models.

## Data retention

The app retains only what it needs to operate the service: installation records
(which repositories are covered), billing state derived from Marketplace events,
and the signed receipts it issues. Pull request diffs are processed transiently for
each review and are not kept as a durable copy.

## Contact

For privacy questions or concerns, or to report a data-handling issue, open a
private security advisory on the [Signetry/github-app](https://github.com/Signetry/github-app/security/advisories)
repository, or contact the Signetry organization through its GitHub profile.
