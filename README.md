# Small Business Digital Playbook

> 40 real-world digital setups for small businesses — each with a copy-ready Prompt for [whacka](https://whacka.app) and a live app example.

**Live preview**: https://smb-digital-playbook.vercel.app (replace with your custom domain once connected)

---

## What this is

A showcase site dedicated to SMB digital solutions:

- Covers 10 industries: Food & Beverage, Retail, Fitness, Beauty, Education, Healthcare, Services, Pet Care, Home Services, and Creative.
- Each case includes: **scenario description**, **core pain point**, **copy-ready Prompt**, and a **live app** to try.
- No code required — copy the Prompt into whacka to generate your own version.

## Repository structure

```
.
├── index.html          # Site entry point (generated from smb-cases.html)
├── assets/             # App screenshots
└── README.md           # This file
```

## Local preview

```bash
cd smb-digital-playbook
python3 -m http.server 8000
# Open http://localhost:8000
```

## Deploy to Vercel + custom domain

1. Push this repo to GitHub (already done).
2. Import it on [Vercel](https://vercel.com/new).
3. Framework Preset: **Other**. Leave Build Command and Output Directory empty.
4. Go to **Settings → Domains** and add your domain.
5. Add the DNS records your registrar prompts for:
   - `@` → A record `76.76.21.21`
   - `www` → CNAME `cname.vercel-dns.com`
6. Wait for DNS propagation; Vercel will issue HTTPS automatically.

## Updating content

The site content is synced from the Notion database `ideas_for_SMB`. To update:

1. Edit or add SMB cases in Notion.
2. Run the sync script in the main project:
   ```bash
   python3 .agents/skills/sync-pages/scripts/sync_pages.py smb
   ```
3. Copy the updated `smb-cases.html` into this repo as `index.html`:
   ```bash
   cp /Users/Lovegood/Desktop/app_prompt_lib/smb-cases.html \
      /Users/Lovegood/Desktop/app_prompt_lib/smb-digital-playbook/index.html
   ```
4. Commit and push; Vercel will redeploy automatically.

---

Small Business Playbook · Digital setups grown from real shop floors
