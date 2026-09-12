# Sethiya Industries — Website

A single-page website for Sethiya Industries (furniture manufacturer). The entire site — HTML, CSS, and JavaScript — is self-contained in one file: `index.html`. There is no build step and no backend required.

## What's inside

```
sethiya-industries/
├── index.html   ← the entire website (structure + styles + scripts)
└── README.md    ← this file
```

## Requirements

- Any modern web browser (Chrome, Firefox, Edge, Safari)
- An internet connection (the page loads Google Fonts, Unsplash stock images, and a Google Maps embed from the web — see "External dependencies" below)
- Optional, for local development: Python 3 or Node.js, to run a simple local server

## How to run it

### Option 1 — Just open it (simplest)
Double-click `index.html`, or right-click → Open With → your browser. This works because the page has no server-side logic.

### Option 2 — Serve it locally (recommended for development)
Opening via `file://` is fine for viewing, but some browsers restrict certain features (like routing via the address bar) under `file://`. A local server avoids that.

**Using Python 3:**
```bash
cd sethiya-industries
python3 -m http.server 8000
```
Then open http://localhost:8000 in your browser.

**Using Node.js:**
```bash
cd sethiya-industries
npx serve .
```
Then open the URL it prints (usually http://localhost:3000).

## Deploying it

Since it's a static single file, you can deploy it anywhere that serves static files, for example:
- **Netlify / Vercel**: drag-and-drop the folder, or connect a Git repo
- **GitHub Pages**: push this folder to a repo and enable Pages on the branch
- **Any web host / shared hosting**: upload `index.html` via FTP to the public/www folder

No build command or environment variables are needed.

## Structure of the page

The site is a single-page app that uses hash-based routing (`#home`, `#catalog`, `#services`, `#about`, `#contact`) handled entirely with JavaScript inside `index.html` — clicking nav links shows/hides sections rather than loading new pages.

## The contact/inquiry form

The "Inquiry" form (`#inquiryForm`) is **UI only** — it does not send data anywhere. On submit, it just shows a success message and resets the form. If you want real submissions (e.g. emailed to you or saved somewhere), you'll need to connect it to a backend or a form service such as:
- [Formspree](https://formspree.io/)
- [Netlify Forms](https://docs.netlify.com/forms/setup/) (if hosting on Netlify)
- A custom backend endpoint (Node/Express, etc.) that the form's `fetch`/`action` posts to

## External dependencies (loaded at runtime, not bundled)

These are fetched live from the internet each time the page loads — they are **not** included in this folder:
- **Google Fonts** — Fraunces, Inter, JetBrains Mono
- **Unsplash** — hero and section images (hotlinked, not downloaded)
- **Google Maps** — embedded map on the contact/about section

If you need the site to work fully offline, you'd need to download the fonts and images locally and update the references in `index.html`.
