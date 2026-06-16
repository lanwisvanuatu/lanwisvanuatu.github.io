# SIL Vanuatu — app store site

A minimal, dependency-free static site that hosts the organisation's apps and a single shared
privacy policy. Designed for **GitHub Pages**. Add more apps by duplicating one app-card block.

## Files
- `index.html` — landing page with an app-card grid + "Get it on Google Play" buttons.
- `privacy.html` — **shared org-wide privacy policy** (children-aware, no-PII). This is the URL every
  app's Play Console listing should use as its Privacy Policy URL.
- `styles.css` — styling (no external dependencies).
- `assets/` — app icon, screenshots.

## Placeholders — all filled in
Org name (SIL Vanuatu), contact email (apps_vanuatu@groups.sil.org), privacy effective date, and the Google
Play package name (`org.sil.vanuatu.motalava.sab`) are all set. Nothing left to replace before deploying.

## Optional: official Google Play badge
The page uses a simple CSS button. To use Google's official badge instead, download it from
<https://play.google.com/intl/en_us/badges/> and replace the `<a class="play-button">…</a>` block in
`index.html` with an `<img>` of the badge wrapped in the same link. Follow Google's brand guidelines.

## Deploy to GitHub Pages (org: `lanwisvanuatu`)

This folder is already a local git repo with one commit, ready to push.

Recommended repo name: **`lanwisvanuatu.github.io`** — it serves the site from the root:
- Site: `https://lanwisvanuatu.github.io/`
- **Privacy policy: `https://lanwisvanuatu.github.io/privacy.html`**  ← use this URL in every app's Play listing

### Steps
1. On github.com, in the **lanwisvanuatu** organization, create a new **empty** repository named
   `lanwisvanuatu.github.io` (public; do NOT add a README, .gitignore, or licence — keep it empty).
2. From this folder, add the remote and push:
   ```
   git remote add origin https://github.com/lanwisvanuatu/lanwisvanuatu.github.io.git
   git push -u origin main
   ```
   (Authenticate as a member of the org; over HTTPS use a GitHub Personal Access Token when prompted.)
3. For a `*.github.io` repo, Pages publishes the default branch automatically. Confirm under
   **Settings → Pages**: Source = "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Wait ~1 minute, then open `https://lanwisvanuatu.github.io/` and `.../privacy.html`.

### Alternative (no command line)
Create the `lanwisvanuatu.github.io` repo, then use **Add file → Upload files** in the GitHub web UI to
drag in the contents of this folder (index.html, privacy.html, styles.css, assets/), and commit.

### Later (optional)
Add a custom domain under Settings → Pages if the org gets one.

## Notes
- The Google Play link returns "not found" until the app is published — this is expected.
- Keep one privacy policy for all apps; point every app's Play listing at the same `privacy.html` URL.
