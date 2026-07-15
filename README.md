# savannaboothenoch.com

Personal website and resume, built with [Jekyll](https://jekyllrb.com/) and
hosted on [GitHub Pages](https://pages.github.com/)..

## Editing 

The site has four pages, all sharing one layout (`_layouts/default.html`) and
nav (About · Work · Contact):

- **`index.html`** — homepage: photo + intro blurb.
- **`about.html`** — placeholder, ready for real content.
- **`work.html`** — intro + résumé (Experience / Education / Skills), driven by
  `_data/resume.yml`, plus the Download-résumé (PDF) link.
- **`contact.html`** — contact details, pulled from `_data/resume.yml`.

Most résumé content lives in one file:

- **`_data/resume.yml`** — name, title, experience, education, skills, profiles.
  Edit this and the Work + Contact pages update. The file has comments
  explaining each section. (The homepage blurb and the Work/About intro
  paragraphs are prose written directly in their `.html` files.)

Other things you might touch:

| What | Where |
|------|-------|
| Colors (warm palette + dark mode) | `assets/css/style.css` (edit the `:root` variables; `--accent` is the clay accent) |
| Typeface | Switzer, self-hosted in `assets/fonts/` (variable 100–900); `@font-face` is at the top of `style.css` |
| Photo | `assets/img/savanna.png` (cropped to a circle in CSS) |
| Downloadable resume | `assets/resume.pdf` (see `assets/README.md`) |
| Site title / SEO description | `_config.yml` |
| Layout / nav | `_layouts/default.html` |

## Publishing

This repo is already set up for GitHub Pages. To turn it on:

1. Push to GitHub (the `main` branch).
2. On GitHub: **Settings → Pages → Build and deployment**.
   - **Source:** *Deploy from a branch*
   - **Branch:** `main` / `/ (root)`
3. GitHub builds the site and publishes it within a minute or two at
   **https://savenoch.github.io/savannaboothenoch.com/**

Because this is a *project* site served from a `/savannaboothenoch.com/`
subpath, `_config.yml` sets `baseurl: "/savannaboothenoch.com"`. That's what
keeps the CSS and links working — they're generated through Jekyll's
`relative_url` filter, so don't hard-code paths like `/assets/...` in
templates; use `{{ '/assets/...' | relative_url }}` instead.

### Using a custom domain later

If you point **savannaboothenoch.com** at this repo:

1. Add a file named `CNAME` (no extension) containing `savannaboothenoch.com`.
2. In `_config.yml` set `baseurl: ""` and `url: "https://savannaboothenoch.com"`.
3. Add DNS records at your registrar — four `A` records for the apex domain
   pointing to GitHub's IPs (`185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153`), and optionally a `CNAME` record for
   `www` → `savenoch.github.io`.

## Running locally (optional)

You don't need to build locally — GitHub builds it for you. But if you want a
live preview while editing:

```sh
bundle install
bundle exec jekyll serve --livereload
```

Then open http://localhost:4000. (Requires Ruby + Bundler.)
