# HelmTV website

Static site for https://helmtv.app: home page, privacy policy (`/privacy.html`), 404 page.
Plain HTML and CSS, no build step, no JavaScript, no third-party requests.

Images are WebP in `images/` (artwork from the invented demo catalog in the app repo's `marketing/`); the Figtree font (SIL OFL) is self-hosted in `fonts/`, so the site makes no third-party requests.

Files: `index.html`, `privacy.html`, `404.html`, `style.css`, `images/`, `fonts/`, `favicon.svg`, `robots.txt`,
`CNAME` (contains `helmtv.app`), `.nojekyll` (tells GitHub Pages to skip Jekyll).

## Before publishing

- In `index.html`, replace the "Coming soon to Google Play" span in the hero with a link to
  `https://play.google.com/store/apps/details?id=com.helmtv.app` and the official badge (see the TODO comment).
- Replace the illustrated hero and catalog strips with real TV screenshots once they exist, and update the Languages chips when more languages ship.
- Make sure the `support@helmtv.app` mailbox exists and is read.

## Deploy on GitHub Pages

1. Create a repository under your own GitHub account and push this folder to its default branch.
2. Repository Settings, Pages: Source "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Under "Custom domain" enter `helmtv.app` (the `CNAME` file already says so), wait for the
   DNS check to pass, then tick "Enforce HTTPS".

## DNS records for helmtv.app

| Type  | Host  | Value                      |
|-------|-------|----------------------------|
| A     | @     | 185.199.108.153            |
| A     | @     | 185.199.109.153            |
| A     | @     | 185.199.110.153            |
| A     | @     | 185.199.111.153            |
| CNAME | www   | `<github-user>.github.io`  |

Replace `<github-user>` with the account or organisation that owns the repository. Optionally
add AAAA records from GitHub's documentation for IPv6. Changes can take a while to propagate.

## Google Play

Use `https://helmtv.app` as the website and `https://helmtv.app/privacy.html` as the privacy
policy URL. If the app's behaviour changes (new SDKs, new network calls), update `privacy.html`
and its "Last updated" date.
