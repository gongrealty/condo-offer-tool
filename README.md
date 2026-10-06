# NYC Condo Offer Tool — fillable Submit Offer Form with live PDF preview

A single-page web tool that lets a buyer fill out a condo **Submit Offer Form & financial
statement** on screen and watch the **real PDF form** fill in live as they type — with
automatic income/asset/liability totals and a print-ready PDF at the end.

Everything runs **in the browser** — no backend, no database, nothing uploaded. What the
buyer types is drawn live on top of the **real PDF form**, so the preview is exactly what
prints. Totals add themselves up. Built by Ian Gong (Gong Realty) and free to adapt (MIT).

## What's inside
- **index.html** — the condo offer checklist (landing page)
- **step-1.html** — the fillable Submit Offer Form (the star: live preview on the real PDF)
- **favicon.svg**

## Run it locally
No build step and no server required. Either:
- **Double-click `index.html`**, or
- Serve the folder with any static server: `npx serve` or `python -m http.server`

## Deploy it (all free, pick one)
It's just static files, so host the folder anywhere:
- **Vercel** — drop the folder on [vercel.com/new](https://vercel.com/new), or run `vercel` in this folder
- **Netlify** — drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop)
- **GitHub Pages** — push to a repo and turn on Pages (Settings → Pages)
- **Cloudflare Pages**, or any static web host

## ⚠️ Customize before you publish
This repo ships with Gong Realty's details as a working example. Replace them with your own
(a quick find-and-replace, or hand this repo to Claude and ask it to rebrand):
1. **Contact email** — search for `i.gong@casa-blanca.com`
2. **Phone** — search for `914-331-8881` and `9143318881`
3. **Name & brokerage** — search for `Ian Gong`, `Gong Realty`, `Lizhi Gong`, `Casa Blanca`
4. **License numbers** in the footer
5. **Preferred lenders** — `index.html` ships with clearly-marked **placeholder** lender cards (highlighted in amber). Swap in your own lenders, or delete the whole lender section.
6. **Brand colors** — the CSS `:root` variables at the top of each file


## How it works (the interesting part)
The form draws your typed values at exact coordinates on top of the real PDF **template**
(embedded in `step-1.html` as base64) using [pdf-lib](https://pdf-lib.js.org/), then renders
the finished PDF to a canvas with [pdf.js](https://mozilla.github.io/pdf.js/) for the live
preview. Numbers are totaled in JavaScript. Your answers are saved only in your own browser
(localStorage); **Save a copy** downloads a file you can reopen later, and **Download PDF**
gives you the finished, print-ready form to email.


## License
MIT — see [LICENSE](LICENSE). Use it, change it, ship it.
