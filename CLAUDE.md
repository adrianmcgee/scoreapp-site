# CLAUDE.md — scoreapp-site

Static HTML marketing + legal site for ScoreAU. Deployed via GitHub Pages. No build step.

## Related repos (sibling absolute paths)

- **iOS app** (Swift, XcodeGen, Fastlane): `/Users/adrianmcgee/Developer/ScoreAU`
- **Backend** (Node/Express, Railway): `/Users/adrianmcgee/Developer/scoreapp-server`

The app and backend link to pages here (privacy, terms, support, password-reset). If you change a path or filename, search both sibling repos for the URL before merging.

## Contents

- `index.html` — landing page.
- `password-reset.html` — token-driven password reset form. Posts to `scoreapp-server` `/auth/password-reset`.
- `privacy/index.html` — privacy policy (referenced from App Store listing).
- `terms/index.html` — terms of service.
- `support/index.html` — support landing page (`mailto:` + FAQ).

## Edits

Edit HTML directly — no framework, no build. Commit + push to `main` and GitHub Pages publishes within ~1 minute.

## Cross-repo gotchas

- App Store metadata references the privacy + terms URLs verbatim. Don't rename `privacy/` or `terms/` without updating App Store Connect.
- `password-reset.html` reads a `token` query param and POSTs to the server. The endpoint URL is hardcoded — keep it in sync with `scoreapp-server/src/routes/auth.js`.
