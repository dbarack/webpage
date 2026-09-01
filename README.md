# dbarack.com

Double-click `index.html` to preview locally.

## Before publishing

Search `index.html` for `[CHECK]` — thirteen markers, all small:

- **Your email**, three places. A `mailto:` beats a contact form: forms are spam magnets and fail silently.
- **A photo.** Save it as `portrait.jpg` next to `index.html`. If the file isn't there the figure removes itself, so it's safe to leave undone — but do it. There is no photo of you anywhere online right now.
- **One live sentence** in About: the book, the fall course, anything in press.
- **The two Finland talk titles** — I seeded them from what you told me. Verify.
- **The five selected papers** and their glosses. These are my picks. They're the first thing a search committee reads, so they should be yours.
- Optional: ORCID / Bluesky / GitHub links, mailing address, portrait caption.

Drop `david-barack-cv.pdf` in the same folder.

## Adding a paper

Find `PUBS` near the bottom. Copy a line:

```js
{g:"Journal articles", y:"2026", ch:["p","n"], st:"Reviewed",
 a:"Barack DL, Coauthor X", t:"Title",
 v:"Journal Name", d:"12(3), 45–67",
 u:"https://doi.org/..."},
```

`g` must match one of the strings in `ORDER`. `ch` is `["p"]`, `["n"]`, or both — it drives the tags and the filter. `d` (volume/pages) and `u` (link) are optional; add `u`, since a third of your list currently has none.

`TALKS` works the same way, newest first.

## Hosting

Hover is your **registrar**, not your host — you're not migrating anything, just repointing DNS.

**GitHub Pages**, free, keeps dbarack.com:

1. New public repo. Upload `index.html`, `portrait.jpg`, the CV PDF.
2. Settings → Pages → Source: `main`, `/root`.
3. Settings → Pages → Custom domain: `dbarack.com`. Tick **Enforce HTTPS**.
4. In Hover's DNS panel, four A records on `@`:
   `185.199.108.153` · `185.199.109.153` · `185.199.110.153` · `185.199.111.153`
   Plus a CNAME on `www` → `<username>.github.io`.
5. Delete Hover's parking/forwarding records if any exist. Certificate issues within the hour.

**Netlify** if you'd rather drag a folder onto a page. Slightly easier, one more account.

Keep WordPress running until the new site resolves over HTTPS. Then cancel it.

## First: salvage the old bio

Check `web.archive.org/web/*/dbarack.com` for a capture from 2017–2023 — your original About text is probably there. Also look in WordPress admin under Pages for a draft or trashed "About". The nav item points at `/` rather than at a page, which fits a page that got unpublished or deleted.

## Later

- Abstracts, as a `<details>` toggle per paper.
- Teaching, once the fall course is running.
- A short "News" line under the masthead for anything just accepted.
