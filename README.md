# Matin Darwish — personal page (Mikepedia)

A Wikipedia-styled personal bio. Files:
- `index.html` — the whole page (self-contained)
- `sitemap.xml`, `robots.txt` — help Google find and index it

**Target home:** https://matindarwish.is-a.dev  (free domain) on free hosting.

---

## Preview it locally
Double-click `index.html`, or run `xdg-open index.html`.

---

## Go live — 4 stages

> Recommended host: **GitHub Pages** (you already have a GitHub account — `Matinthereal`),
> which pairs cleanly with an `is-a.dev` domain. Cloudflare Pages also works and is equally free.

### Stage A — Put the files on GitHub  (~5 min)
1. Create a new **public** repo, e.g. `matindarwish-site`.
2. Upload `index.html`, `sitemap.xml`, `robots.txt` (drag them into GitHub's web uploader,
   or `git push`).

### Stage B — Turn on free hosting (GitHub Pages)  (~2 min)
1. Repo → **Settings → Pages**.
2. **Source:** Deploy from a branch → **Branch:** `main` → **Folder:** `/ (root)` → **Save**.
3. After ~1 min it's live at `https://matinthereal.github.io/matindarwish-site/`.

### Stage C — Get the free domain `matindarwish.is-a.dev`  (live usually < 24h)
1. Open **https://github.com/is-a-dev/register** and skim its README/docs.
2. **Fork** it, then add a file `domains/matindarwish.json`:
   ```json
   {
     "owner": {
       "username": "Matinthereal",
       "email": "DarwishEnterprises@protonmail.com"
     },
     "records": {
       "CNAME": "matinthereal.github.io"
     }
   }
   ```
3. Open a **Pull Request**. When a maintainer merges it, the subdomain starts working.
4. Back in your site repo → **Settings → Pages → Custom domain** → enter
   `matindarwish.is-a.dev` → **Save**. Tick **Enforce HTTPS** once it appears.

🎉 Your page is now live at **https://matindarwish.is-a.dev**

### Stage D — Get into Google (Search Console)  (do this AFTER it's live)
1. Go to **https://search.google.com/search-console** and sign in.
2. **Add property → URL prefix →** `https://matindarwish.is-a.dev`
3. **Verify ownership** — choose the **HTML tag** method. Google shows a line like
   `<meta name="google-site-verification" content="xxxx">`.
   **Send that line to Claude and it'll paste it into `index.html`'s `<head>` for you** —
   then re-upload and click **Verify**.
4. Once verified: **Sitemaps** → submit `sitemap.xml`.
5. **URL Inspection** (top bar) → paste your URL → **Request indexing**.
6. Wait a few days to a couple of weeks, then search "Matin Darwish".

---

## Add a real photo later
Put `photo.jpg` in the repo, then in `index.html` replace the TikTok card
(`<a class="tiktok-card">…</a>`) with:
```html
<img src="photo.jpg" alt="Matin Darwish">
```
