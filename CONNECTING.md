# Connecting & Deploying — scoreapp-site

Marketing and legal website for ScoreAU. Deployed via GitHub Pages without any build step.

---

## 1. How It Connects to `scoreapp-server`

`password-reset.html` provides the web form for users who request a password reset via email:
1. The user receives an email containing a link with a token:
   `https://scoreapp-site.pages.dev/password-reset.html?token=XYZ` (or custom domain).
2. The page extracts `token` from the URL parameters.
3. Upon submitting the new password, the JavaScript code directly sends an HTTP POST request:
   - **Target**: `https://scoreapp-server-production.up.railway.app/auth/password-reset`
   - **Payload**: `{"token": "XYZ", "newPassword": "..."}`
4. The server validates the token against Supabase and updates the user's password hash.

---

## 2. Local Testing

To test the password reset flow locally:
```bash
# Terminal 1: Serve this site locally
cd /Users/adrianmcgee/Developer/scoreapp-site
python3 -m http.server 8000

# Open in browser:
# http://localhost:8000/password-reset.html?token=test
```

---

## 3. Deployment

This site has no compilation or build step:
```bash
cd /Users/adrianmcgee/Developer/scoreapp-site
git add .
git commit -m "Update legal / marketing pages"
git push origin main
```
GitHub Pages automatically deploys the updated static files within ~60 seconds.
