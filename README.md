# chartstyler.com

Source of the ChartStyler website, built with Jekyll and served by GitHub Pages at
https://chartstyler.com.

| Path | What |
|---|---|
| `index.html` | Homepage (stand-alone page, not the docs theme) |
| `assets/` | Images for the homepage |
| `docs/` | User documentation ([just-the-docs](https://just-the-docs.com/) theme), structured like the panel's tabs; its images are in `docs/assets/images/` |
| `_includes/`, `_sass/` | Customisations of the docs theme |
| `.github/workflows/pages.yml` | Builds and deploys the site in the public repo |
| `CNAME` | Custom domain |

## Local preview

```bash
bundle install
bundle exec jekyll serve --livereload --destination /tmp/chartstyler-site
```

Then open http://localhost:4000 (documentation: http://localhost:4000/docs/).

## Publishing

The ChartStyler project is private; the site is published from the public repo
[ChartStyler/chartstyler](https://github.com/ChartStyler/chartstyler). From the project root:

```bash
npm run publish:site -- --dry-run   # show what would change (account settings: scripts/build-config/site.json)
npm run publish:site                # copy website/ to the public repo, commit and push
```

GitHub Actions in the public repo then builds the site (Settings → Pages → Source must be
"GitHub Actions").
