# Pawse website (privacy + support)

Static pages that satisfy the App Store / Google Play requirements for a public
**Privacy Policy URL** and **Support URL**. Plain HTML + one CSS file, no build step.

Files: `index.html` (landing), `privacy.html`, `support.html`, `styles.css`.

## Before publishing — replace these placeholders

1. **Support email** — currently `support@pawse.app` (a placeholder). Replace it in:
   - `privacy.html`, `support.html` (both `mailto:` links + visible text)
   - `src/constants/links.ts` in the app (`SUPPORT_EMAIL`)
2. **`[DATE]`** in `privacy.html` → the date you publish (e.g. `June 4, 2026`).
   Also update `PRIVACY_POLICY.md` to match.
3. After the site is live, put the real URLs in `src/constants/links.ts`
   (`PRIVACY_URL`, `SUPPORT_URL`) so the in-app Settings links work.

## Host on GitHub Pages (free)

GitHub Pages serves **public** repos for free. Easiest setup:

**Option A — dedicated site repo (simplest):**
1. Create a new public repo, e.g. `pawse-site`.
2. Copy the contents of this `website/` folder to the repo root.
3. Repo **Settings -> Pages -> Source: Deploy from a branch -> `main` / root**.
4. Your URLs become:
   - `https://<your-username>.github.io/pawse-site/privacy.html`
   - `https://<your-username>.github.io/pawse-site/support.html`

**Option B — serve from this app repo:**
1. Move these files into a top-level `docs/` folder in a **public** repo.
2. Settings -> Pages -> Source: `main` / `docs`.
   (Note: Pages is free only on public repos; private repos need a paid plan.)

## Use the URLs

- App Store Connect: Privacy Policy URL + Support URL fields.
- Google Play Console: Privacy Policy URL (Store listing) + support email.
- In-app: paste the URLs into `src/constants/links.ts`.

Preview locally by opening `index.html` in a browser, or run
`npx serve website` from the project root.
