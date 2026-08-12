# Marketplace listing copy kit

Ready-to-paste copy for the GitHub Marketplace listing. Sections map to the fields
in the Marketplace listing editor. Copy follows GitHub's style rules: sentence
case, active voice, serial commas, and no trailing punctuation on titles.

## Listing name

```
Signetry Admission
```

## Very short description

Sentence case, describes functionality, no trailing punctuation, no call to action,
does not repeat the app name. (66 characters.)

```
Governs coding-agent pull requests with a signed admission receipt
```

## Categories

- **Primary:** Code review
- **Secondary:** Code quality

## Introductory description

Begins with the app name, active voice, 150-250 characters. (160 characters.)

```
Signetry Admission reviews every coding-agent pull request and posts one advisory verdict with reasons and a signed receipt, so a human still decides the merge.
```

## Detailed description

Under 1000 characters. Each value proposition is a level-3 header followed by a
short paragraph. Sentence case, periods, no exclamation marks.

```markdown
### Earned authority, not blanket access

Signetry Admission acts through a short-lived, read-only installation token scoped
to the pull request under review. It posts one advisory comment and nothing more.

### Injection-resistant by construction

The review is comment-only and the app never runs your diff as an instruction. It
reasons about the change, then reports, so prompt injection in a PR cannot escalate
into an action.

### Proof you can verify

Every verdict links to a signed receipt. The comment restates the receipt and
claims nothing beyond it, so anyone can check what was decided and why.

### A human always merges

Signetry Admission never merges and never enables auto-merge. It advises, and a
person makes the final call on every pull request.
```

## Required URLs

- **Customer support URL:** `https://github.com/Signetry/github-app/blob/main/SUPPORT.md`
- **Privacy policy URL:** `https://github.com/Signetry/github-app/blob/main/PRIVACY.md`
- **Homepage URL:** `https://signetry.github.io`
- **Documentation URL:** `https://github.com/Signetry/signetry`

## Pricing

Use a **Free plan**. A free plan satisfies the Marketplace pricing requirement and
keeps onboarding frictionless. The app already handles `marketplace_purchase`
webhook events, so it is ready to react to purchases, cancellations, and plan
changes if paid plans are added later.

## Logo and feature card

Both assets are prepared to GitHub's specs:

- **Logo:** 200x200 px, transparent background.
- **Feature card:** 965x482 px.

Upload the logo under the app's settings (Developer settings → GitHub Apps → your
app → Display information), and upload the feature card in the Marketplace listing
editor under the listing's branding section.
