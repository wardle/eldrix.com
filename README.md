# eldrix.com

Company website for Eldrix Ltd. Built with [Hugo](https://gohugo.io), with no
theme: the layouts and one stylesheet are in this repository.

## Run locally

```
brew install hugo
hugo server
```

Then open http://localhost:1313. Pages reload as you save.

## Publish

Push to `main`. GitHub Actions (`.github/workflows/deploy.yml`) builds the site
and deploys it to GitHub Pages. Check progress with `gh run watch`.

The workflow pins the Hugo version (`HUGO_VERSION`). Keep it in step with the
local version (`hugo version`).

## Where things are

| Path | What |
|---|---|
| `hugo.toml` | Site settings: contact email, company details, menu |
| `content/_index.md` | Home page headline and introduction |
| `content/software/` | Software section; one Markdown file per application |
| `content/about.md` | About page |
| `data/opensource.yaml` | Open-source projects (first six shown on the home page) |
| `layouts/` | Templates (`_partials/` for shared pieces) |
| `assets/css/main.css` | The stylesheet; colours are tokens at the top |

## Adding an application

Create `content/software/<name>.md` with front matter `title`, `tagline`,
`description`, `weight` (order), `featured: true` to show it on the home page.
Optional:

- `highlights`: short points, each with `title` and `text`
- `steps` (each with `title` and `text`) and `outcome`: a numbered workflow
- `badge`: a short text label under the tagline
- `part_of`: path of the parent product, e.g. `/software/patientcare`
- `cta_title`: heading of the "Get in touch" box

The body is Markdown.

## Domain

eldrix.com is registered at Gandi. Its DNS is at Cloudflare (free plan), which
proxies the site and provides the HTTPS certificate. GitHub never issued its own
Pages certificate for the domain: it stayed at `authorization_created` for over
24 hours in November 2026.

Cloudflare records:

| Name | Type | Value | Proxy |
|---|---|---|---|
| `@` | A | 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 | on |
| `@` | AAAA | 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153 | on |
| `www` | CNAME | wardle.github.io | on |
| `@` | TXT | `OSSRH-81090` (Maven Central verification) | |
| `@` | TXT | `clojars wardle` (Clojars verification) | |
| `_github-pages-challenge-wardle` | TXT | GitHub Pages domain verification | |
| `@` | TXT | `v=spf1 -all` (no mail is sent from eldrix.com) | |
| `_dmarc` | TXT | `v=DMARC1; p=reject` | |

Cloudflare settings: SSL/TLS mode **Full** (not strict, because GitHub presents
its `*.github.io` certificate) and **Always Use HTTPS** on.

The repository's Settings → Pages has the custom domain `eldrix.com`, with
"Enforce HTTPS" off. Cloudflare does the redirect to HTTPS.
