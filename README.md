# portfolio-assets
Data repository for yuli-ferna/portfolio.

The portfolio reads these JSON files in production via `raw.githubusercontent.com`.

## Structure
* **locale/**
  * `en.json`       ← English translations
  * `es.json`       ← Spanish translations
* **assets.json** ← image and icon paths
* **.github/**
  * **workflows/**
    * `trigger-deploy.yml`  ← automatic redeploy on push

## Automatic redeploy setup
1. Copy the deploy hook from your hosting (Vercel or Netlify).
2. In this repo: **Settings** → **Secrets** → **Actions**.
3. Add the secret:
   * **Vercel**: `VERCEL_DEPLOY_HOOK` → `https://api.vercel.com/v1/integrations/deploy/...`
   * **Netlify**: `NETLIFY_DEPLOY_HOOK` → `https://api.netlify.com/build_hooks/...`

> The workflow triggers only when `.json` files change in `main`.

## How to update the portfolio
# Edit whatever you need
`vim locale/es.json`

# Push — the portfolio redeploys automatically in ~1 min
`git add . && git commit -m "update experience" && git push`
