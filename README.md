# mattbrowning.marketing

Static site. No framework, no build step. Edit HTML, commit, Cloudflare Pages deploys.

## Adding a new role page

1. `cp _template.html <company>.html`
2. Fill in the placeholders: `COMPANY`, `ROLE TITLE`, the title/description, the hero, the sections.
3. Add the path to `_headers` so it gets the noindex header too.
4. Commit. It's live in about a minute at `mattbrowning.marketing/<company>`.

**Never remove** `<meta name="robots" content="noindex, nofollow">` from a role page.
**Never add** a `Disallow:` line for a role path to `robots.txt` — robots.txt is public, so a Disallow advertises the path.

## Retiring a page

Delete the folder and its `_headers` block. Note that the content stays in git history forever —
if that matters, don't commit it in the first place.

## Structure

```
index.html           home
cv.pdf               drop your CV here; CTAs point at it
<company>.html       one file per role page — flat, no folders
/assets/site.css     the entire design system — change it here, changes everywhere
/_template.html      copy this to start a new page
/_headers            Cloudflare Pages: noindex backstop per role path
/robots.txt          allow-all + sitemap. Does not mention role paths.
/sitemap.xml         home only. Role pages are never listed.
/404.html
```

## Components available in site.css

`.bar` instrument bar · `.hero` + `.deck` · `.sec-head` section headers ·
`.now` + `.tiles` current-role panel · `.metrics` / `.strip` stat blocks ·
`.range` two-column table · `.apply` numbered list · `.story` headed panel ·
`.prose` body copy · `.callout` · `.cta` + `.btn` · `.foot`

## Placeholders to replace before shipping

- `BOOKING_LINK` — Google Calendar appointment schedule or Cal.com
- `PR_LINK` — the Devin pull request, once it exists
