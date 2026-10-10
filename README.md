# HelmTV website

Static site for https://helmtv.app: home page, privacy policy (`/privacy.html`), 404 page.
Plain HTML and CSS, no build step, no JavaScript, no third-party requests.

Files: `index.html`, `privacy.html`, `404.html`, `style.css`, `favicon.svg`, `robots.txt`,
`CNAME` (contains `helmtv.app`), `.nojekyll` (tells GitHub Pages to skip Jekyll).

## Before publishing

- In `index.html`, replace the `#` on the "Get it on Google Play" button with
  `https://play.google.com/store/apps/details?id=com.helmtv.app` (see the TODO comment).
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
