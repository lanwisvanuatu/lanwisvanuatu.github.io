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

## Deploy to GitHub Pages (under the org's GitHub account)
1. Create a new repository in the org's GitHub account, e.g. `apps` (public).
2. Upload the contents of this `org-store-site/` folder to the repo root
   (either drag-and-drop in the GitHub web UI, or `git push`).
3. In the repo: **Settings → Pages → Build and deployment → Source: "Deploy from a branch"**,
   branch `main`, folder `/ (root)`, then **Save**.
4. After a minute, the site is live at:
   - Landing page: `https://<org-github-user>.github.io/<repo>/`
   - **Privacy policy: `https://<org-github-user>.github.io/<repo>/privacy.html`**  ← use this in Play Console
5. (Later, optional) add a custom domain under Settings → Pages if the org has one.

## Notes
- The Google Play link returns "not found" until the app is published — this is expected.
- Keep one privacy policy for all apps; point every app's Play listing at the same `privacy.html` URL.
