# savannaboothenoch.com

Personal website and resume, built with [Jekyll](https://jekyllrb.com/) and
hosted on [GitHub Pages](https://pages.github.com/).

## Editing your content

Almost everything you'll want to change lives in one file:

- **`_data/resume.yml`** — your name, title, experience, education, skills, and
  projects. Edit this and the whole page updates. The file has comments
  explaining each section.

Other things you might touch:

| What | Where |
|------|-------|
| Page colors / fonts | `assets/css/style.css` (change `--accent` near the top to re-theme) |
| Downloadable resume | add `assets/resume.pdf` (see `assets/README.md`) |
| Site title / SEO description | `_config.yml` |
| Custom domain | `CNAME` |
| Page structure | `index.html`, `_layouts/default.html` |

## Publishing

This repo is already set up for GitHub Pages. To turn it on:

1. Push to GitHub (the `main` branch).
2. On GitHub: **Settings → Pages → Build and deployment**.
   - **Source:** *Deploy from a branch*
   - **Branch:** `main` / `/ (root)`
3. GitHub builds the site and publishes it within a minute or two.

### Custom domain

The `CNAME` file points the site at **savannaboothenoch.com**. For that to
work you also need DNS records at your domain registrar:

- Four `A` records for the apex domain pointing to GitHub's IPs:
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- (Optional) a `CNAME` record for `www` pointing to `savenoch.github.io`.

Until DNS is configured, you can preview at
`https://savenoch.github.io/savannaboothenoch.com/`. If you use that URL
instead of a custom domain, delete the `CNAME` file and set
`baseurl: "/savannaboothenoch.com"` in `_config.yml`.

## Running locally (optional)

You don't need to build locally — GitHub builds it for you. But if you want a
live preview while editing:

```sh
bundle install
bundle exec jekyll serve --livereload
```

Then open http://localhost:4000. (Requires Ruby + Bundler.)
