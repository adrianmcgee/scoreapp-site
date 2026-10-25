# scoreapp-site

Static HTML marketing, legal, and support website for ScoreAU. Hosted on GitHub Pages.

---

## Quick Links
- **[Connecting & Deploying](CONNECTING.md)**: Password reset API connection and GitHub Pages deployment.
- **[CLAUDE.md](CLAUDE.md)**: AI agent instructions.
- **[Backend Server](../scoreapp-server/README.md)**: Documentation for the Railway API server.
- **[iOS App](../ScoreAU/README.md)**: Main iOS application.

---

## Pages
- `index.html` — Landing page
- `password-reset.html` — User-facing password reset form (POSTs to `scoreapp-server`)
- `privacy/index.html` — Privacy policy (linked from App Store Connect)
- `terms/index.html` — Terms of Service
- `support/index.html` — Support contact page and FAQ

---

## Deployment
Any commit pushed to `main` is published directly to GitHub Pages within 60 seconds:
```bash
git add .
git commit -m "Update site"
git push origin main
```
