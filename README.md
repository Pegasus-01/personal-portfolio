# Deploying to GitHub Pages

This is a single self-contained file (`index.html` — HTML, CSS, and JS all in one). No build step needed.

## Option A — New repo dedicated to the site (recommended)

1. **Create a new repo** on GitHub named exactly `<your-username>.github.io` (e.g. `Pegasus-01.github.io`).
   This naming gives you a clean root URL: `https://pegasus-01.github.io`
2. Clone it locally:
   ```bash
   git clone https://github.com/<your-username>/<your-username>.github.io.git
   cd <your-username>.github.io
   ```
3. Copy `index.html` into the repo root.
4. Commit and push:
   ```bash
   git add index.html
   git commit -m "Add portfolio site"
   git push origin main
   ```
5. Go to **Settings → Pages** in the repo. Under "Build and deployment," set:
   - Source: **Deploy from a branch**
   - Branch: **main**, folder: **/ (root)**
6. Save. GitHub will publish the site within a minute or two at `https://<your-username>.github.io`.

## Option B — Project page on an existing repo (e.g. `personal-portfolio`)

1. Add `index.html` to the root of that repo (or to a `/docs` folder).
2. Push the change.
3. Go to **Settings → Pages**, set Source to **Deploy from a branch**, pick the branch, and folder **/ (root)** or **/docs** depending on where you placed the file.
4. Save. The site publishes at `https://<your-username>.github.io/<repo-name>/`.

## Custom domain (optional)

If you own a domain and want to use it instead of the `github.io` URL:
1. In **Settings → Pages → Custom domain**, enter your domain and save (this creates a `CNAME` file in the repo automatically).
2. At your domain registrar, add a `CNAME` record pointing to `<your-username>.github.io` (for a subdomain like `www`), or `A` records pointing to GitHub's IPs (for the root domain) — GitHub's Pages docs list the current IPs to use.
3. Wait for DNS to propagate (can take up to 24 hours), then enable "Enforce HTTPS" in the same settings panel once available.

## Updating the site later

Just edit `index.html`, then:
```bash
git add index.html
git commit -m "Update site"
git push
```
GitHub Pages redeploys automatically on every push to the configured branch.

## Notes

- The site uses Google Fonts via a CDN link, so an internet connection is needed to load fonts (this is standard and works fine on GitHub Pages).
- All animations respect `prefers-reduced-motion`, so visitors with that OS setting enabled will see a static, motion-free version.
- The phone number from your resume is **not included** on this site — only email and social links. Worth keeping it that way for a public-facing page to avoid scraping/spam.
