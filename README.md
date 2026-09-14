# SRVU website

The website for **SRVU — Studentenbond Vrije Universiteit Amsterdam**.

This is a plain static site: HTML, CSS and JavaScript. There is **no build step**, no
framework, no `npm install`. What is in this folder is exactly what gets served.

---

## Quick facts

| | |
|---|---|
| Total size | ~700 KB |
| Pages | one (`index.html`, nine sections) |
| Built with | Claude Design (exported as static HTML) |
| Host | Netlify |

---

## How to edit it

**Small text changes** (dates, office hours, committee names):

1. Open `index.html` in any text editor — [VS Code](https://code.visualstudio.com) is free
   and makes it much easier to read.
2. Find the text you want to change. It sits between HTML tags, e.g.
   `<h2 ...>Three pillars, one union</h2>`.
3. Change the words *between* the tags. Leave everything inside `< >` alone.
4. Save.

**Bigger changes** (new sections, layout): easier in the original Claude Design canvas,
then re-export and replace these files.

**In the browser, no install:** drag this folder onto [stackblitz.com](https://stackblitz.com)
for an editor with live preview.

---

## How to publish

**If this repo is connected to Netlify** (recommended): push to `main`. Netlify rebuilds
automatically. Nothing else to do.

**Manual:** open the site in Netlify → **Deploys** → drag this folder into the drop zone.

**Brand new site:** drag the folder onto [app.netlify.com/drop](https://app.netlify.com/drop).

---

## What the files are

```
index.html      the entire page
support.js      Claude Design runtime — do not edit
image-slot.js   image placeholder component — do not edit
_ds/            design system (fonts, colours, component styles) — do not edit
assets/         logos, favicon, background pattern
_redirects      sends unknown URLs to index.html instead of a 404
netlify.toml    caching and security headers
```

Only `index.html` and `assets/` are meant to be edited by hand.

### ⚠️ About `assets/pattern.jpg`

This was originally **7015 × 7000 px and 12.1 MB** — a print-resolution image used to draw
an 86-pixel-tall decorative stripe. It made the site take 30+ seconds to load on phone data.

It is now 1240 px and 351 KB, which looks identical on screen.

**If you ever replace it, resize it first.** Anything over ~500 KB for a background is a
mistake. The same goes for any photo added to the site.

---

## The domain — read this before it bites someone

SRVU owns **`srvu.org`**. Registered **30 September 2003**, held continuously since.

| | |
|---|---|
| Registrar | Cronon GmbH (**STRATO**) |
| DNS managed at | STRATO (`docks16.rzone.de`, `shades12.rzone.de`) |
| Renews | **30 September**, every year |
| Email | Google Workspace (`MX → smtp.google.com`) |

**Someone on the board must keep access to the STRATO account.** A domain held since 2003
is not recoverable if it lapses and a squatter takes it. Check every September that
auto-renew is on and that the renewal notice goes to an address the *current* board reads —
not a graduated member's personal inbox.

### Pointing `srvu.org` at this site

At STRATO, change these records:

```
Type: A      Name: @      Value: 75.2.60.5
Type: CNAME  Name: www    Value: <your-site>.netlify.app
```

If STRATO offers **ALIAS** or **ANAME**, use `apex-loadbalancer.netlify.com` for the root
instead of the A record — it's better.

**Do not touch the MX records.** They point at Google Workspace. Changing them, or moving
the nameservers away from STRATO, stops SRVU email from arriving.

To test without risk, add `CNAME new → <your-site>.netlify.app` first. That gives you
`new.srvu.org` while the live site stays exactly as it is.

Note there is currently a **separate WordPress site** live at `srvu.org`. Pointing the
domain here replaces it. That's a board decision, not a technical one.

---

## If you're inheriting this

Everything you need is in this repo. The person who set it up is probably gone — that's
normal for a student union, and it's why this file exists.

Start by deploying a copy to a new Netlify site. It costs nothing, breaks nothing, and
proves you can publish before you need to.
