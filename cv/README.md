# CV & site data

The YAML in `data/` is the single source for my CV PDF and https://jonasweinert.github.io/. The build code lives in the [cv-site-template](https://github.com/JonasWeinert/cv-site-template) submodule at `../cv-template`.

```bash
git submodule update --init
cd cv-template && npm ci
CV_DATA=../cv/data CV_OUT=../cv/out npm run build:all   # → cv/out/Weinert_CV.pdf, cv/out/site
```

On push to `main`, `.github/workflows/site.yml` builds both and publishes the site to `JonasWeinert/jonasweinert.github.io` (needs the `SITE_DEPLOY_TOKEN` secret). The site is locked to the `campus` theme in `data/site.yaml`.

To pick up template changes: `git submodule update --remote cv-template`, then commit.
