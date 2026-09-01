# Contributing to the Signetry GitHub App

Contributions are welcome — the App manifest, the setup docs, and the comment
rendering are all fair game.

## Licensing

This repository is **[Apache-2.0](LICENSE)**. You may use, copy, modify, distribute,
and commercialize it, including in closed-source and commercial products, subject to
the licence's attribution and notice terms. There is no separate permission to ask for.

It is part of Signetry's
[open-core model](https://github.com/Signetry/signetry/blob/main/LICENSING.md): the
integration surface (this repo and the other adapters) is Apache-2.0 so anyone can add
an agent, an editor, or a CI adapter, while the engine
([`Signetry/core`](https://github.com/Signetry/core)) is source-available under
BUSL-1.1 and converts to Apache-2.0 on 2030-08-31.

### The CLA still applies

Contributions are accepted under the [Contributor License Agreement](CLA.md), and the
CLA check gates every pull request. Open core is exactly why it is kept: code sometimes
moves across the line, and the CLA is what lets that happen without going back to every
past contributor. Note that it assigns copyright in a merged contribution to the
maintainer — see [LICENSING.md](https://github.com/Signetry/signetry/blob/main/LICENSING.md#contributions)
for what that does and does not mean. It does not take your Apache-2.0 rights away.

## What this repo is

The App itself is a **thin comment surface**. It carries no policy logic: every verdict
comes from `signetry-core`, and the comment never claims more than the signed receipt
does. A change that would let the App decide something on its own is out of scope — put
it in the engine instead.

Two properties must survive any change here:

- **Comment-only.** The App never merges, never approves, and never gates a PR.
- **The comment restates the receipt.** If the receipt says a gate is `unproven`, the
  comment says `unproven` — never "passed".

## Signing the CLA (required before merge)

This is enforced by a bot. When you open a pull request, the **CLA Assistant** check
will ask you to sign the [Contributor License Agreement](CLA.md). Reply on the PR
with exactly:

```
I have read the CLA Document and I hereby sign the CLA
```

Your acceptance is recorded in `signatures/cla.json`. A PR **cannot be merged** until
the CLA is signed.

## Credit

Contributors are **acknowledged** in [CONTRIBUTORS.md](CONTRIBUTORS.md), the Git
history, and release notes. Attribution is separate from trademark: you may freely say
you contributed, but please don't use the Signetry name to endorse or promote your own
product. See the "Recognition of Contributors" clause in [CLA.md](CLA.md).

## Conduct and security

By participating you agree to the [Code of Conduct](CODE_OF_CONDUCT.md). Please report
vulnerabilities privately — see [SECURITY.md](SECURITY.md).
