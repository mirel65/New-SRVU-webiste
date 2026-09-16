# SRVU website



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


**Do not touch the MX records.** They point at Google Workspace. Changing them, or moving
the nameservers away from STRATO, stops SRVU email from arriving.

To test without risk, add `CNAME new → <your-site>.netlify.app` first. That gives you
`new.srvu.org` while the live site stays exactly as it is.

Note there is currently a **separate WordPress site** live at `srvu.org`. Pointing the
domain here replaces it. That's a board decision, not a technical one.

---

## If you're inheriting this (not you Daniel)

Everything you need is in this repo. The person who set it up is probably gone (Hopefully I'm employed)

Worst case scenario ask around. Good luck !
