# The Fitness Initiative — Website

A fast, accessible, SEO-optimized static website for **The Fitness Initiative (TFI)**, a Rochester, NY nonprofit. Built as plain HTML/CSS/JS — **no build step, no dependencies** — so it can be hosted for free on GitHub Pages, Netlify, or any static host.

## Structure

```
tfi-website/
├── index.html              Home
├── about.html              About & founders
├── programs.html           Programs overview (+ Fitness 101)
├── cooking-with-exercise.html   Flagship program (with Rochester Parkinson's Network)
├── renew-me.html           ReNewMe chronic-disease program (the pyramid)
├── partner.html            Partner With Us (nonprofits, healthcare, funders) + form
├── support.html            Support / Donate
├── contact.html            Contact + map + form
├── 404.html                Not-found page
├── robots.txt, sitemap.xml, site.webmanifest, CNAME
├── favicon.ico + favicon/app-icon PNGs
└── assets/
    ├── css/styles.css      All styles (navy + teal, Helvetica)
    ├── js/main.js          Mobile nav + scroll reveal
    └── img/                Photos, logo, and full pyramid logo
```

## Branding
- **Colors:** deep navy `#0f2c52` + health teal `#16a3a3` (matches the pyramid logo), warm gold `#f2b134` for donate CTAs.
- **Type:** Helvetica / Helvetica Neue.
- **Logo:** `assets/img/tfi-logo.png` (icon) and `assets/img/tfi-logo-full.png` (full pyramid). Favicons generated from the same mark.

## Preview locally
Open `index.html` in a browser, or run a tiny local server so root-relative links work:
```bash
cd tfi-website
python3 -m http.server 8080     # then visit http://localhost:8080
```

## Publish free on GitHub Pages
1. Create a new GitHub repo (e.g. `tfi-website`) and push these files.
2. Repo **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/root`.
3. Under **Custom domain**, enter `www.thefitnessinitiative.org` (the included `CNAME` file already sets this).
4. At your domain registrar (Wix, where the domain lives), add a **CNAME** DNS record: `www` → `<your-github-username>.github.io`. Keep the domain at Wix; only the DNS points to GitHub.
5. Enable **Enforce HTTPS** once the certificate provisions.

> Alternative: drag the `tfi-website` folder into Netlify (netlify.com/drop) for instant hosting, then connect the domain there.

## Contact forms (one-time setup)
`contact.html` and `partner.html` are wired for [Formspree](https://formspree.io) with spam protection, a subject line, and a redirect to `contact-thanks.html`. To activate:

1. Sign up free at [formspree.io](https://formspree.io) using **info@thefitnessinitiative.org**.
2. Create a new form; Formspree gives you an endpoint like `https://formspree.io/f/abcdwxyz`.
3. In **both** `contact.html` and `partner.html`, replace `YOUR_FORMSPREE_ID` in the `action="https://formspree.io/f/YOUR_FORMSPREE_ID"` line with your ID.
4. Submit the form once to confirm the address (Formspree emails you to verify). Done — submissions now arrive in your inbox and users land on the thank-you page.

The free plan covers 50 submissions/month. Netlify Forms is an alternative if you host on Netlify (add `data-netlify="true"` to the form).

## Donation button (one-time setup)
`support.html` has a **Give Online** button ready to point at your donation page. Pick a platform, create a donation page, then replace `https://YOUR-DONATION-LINK` in `support.html` with its URL.

- **Zeffy** — 100% free for nonprofits (no platform fees). Recommended.
- **PayPal Giving / PayPal.me**, **Givebutter**, or **Donorbox** also work — any of them give you a shareable donation-page link.

## Before go-live checklist
- [x] Formspree active: endpoint `mjgnzogr` wired into `contact.html` and `partner.html`.
- [x] Donation button live: Zeffy form wired into `support.html` (Donate Now + Give Online).
- [ ] Confirm the EIN / 501(c)(3) status line in the footer if you want it stated explicitly.
- [ ] Point DNS and verify `www.thefitnessinitiative.org` before cancelling Wix hosting.
