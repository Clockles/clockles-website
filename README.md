# Clockles Technology website

The public website is a static site in [`site/`](site/). It uses plain HTML, CSS, and JavaScript, with no build step, database, or server-side application. The GitHub Pages workflow uploads only the `site/` directory, so project documents kept at the repository root are not included in the published site artifact.

## Preview locally

From the repository root, run:

```sh
python3 -m http.server 8000 --directory site
```

Then open `http://localhost:8000` in a browser.

## Update content

- Edit the relevant page under `site/`.
- Shared styles and the small mobile navigation script are in `site/assets/`.
- Update `site/sitemap.xml` when adding or removing public pages.
- Update each page's canonical URL, page title, description, and Open Graph metadata when its URL or positioning changes.
- The `site/CNAME` file reserves `www.clockles.com` for GitHub Pages publishing.

## GitHub Pages publishing

The workflow at `.github/workflows/pages.yml` deploys the contents of `site/` on pushes to `main` that change the website or workflow. In the GitHub repository, select **Settings → Pages → Build and deployment → GitHub Actions**. Configure `www.clockles.com` as the Pages custom domain and configure DNS at the domain provider before enabling HTTPS.

The workflow and `CNAME` file do not change DNS or publish the site until this repository is connected to GitHub and Pages is enabled.
