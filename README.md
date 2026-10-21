# Uwerta Apps — Privacy Policies

Static privacy-policy site for Uwerta games, published with GitHub Pages at:

```text
https://apps.uwertaoflegends.com/
```

Current policies:

- Uwerta Crystal Blocks:
  - `https://apps.uwertaoflegends.com/privacy/blocks/`
  - `https://apps.uwertaoflegends.com/privacy/blocks/pl.html`
  - `https://apps.uwertaoflegends.com/privacy/blocks/de.html`
  - `https://apps.uwertaoflegends.com/privacy/blocks/uk.html`
  - `https://apps.uwertaoflegends.com/privacy/blocks/fr.html`

## Repository layout

```text
index.html              landing page with links to each game policy
404.html
robots.txt
sitemap.xml
CNAME                   apps.uwertaoflegends.com
privacy/
  index.html            redirect to the current policy
  blocks/               Uwerta Crystal Blocks policy in five languages
    index.html          English
    pl.html
    de.html
    uk.html
    fr.html
```

Every future game gets its own directory:

```text
privacy/<game-slug>/index.html
privacy/<game-slug>/pl.html
privacy/<game-slug>/de.html
privacy/<game-slug>/uk.html
privacy/<game-slug>/fr.html
```

For example, a future game can use:

```text
https://apps.uwertaoflegends.com/privacy/gra2/pl.html
```

Add its card to `index.html`, add its URLs to `sitemap.xml`, then commit and push.

## GitHub Pages

- Source: `main` branch, repository root.
- Custom domain: `apps.uwertaoflegends.com` (see `CNAME`).
- Enforce HTTPS in **Settings → Pages** once the DNS certificate is ready.

### DNS

At the DNS provider for `uwertaoflegends.com`, create:

```text
Type: CNAME
Name: apps
Target: forzex1337.github.io
```

Use DNS-only mode first if the domain uses Cloudflare; switch proxying on only after GitHub has verified and issued the certificate.

## Policy source

The full policy text is maintained in the app repository at:

```text
assets/i18n/privacy_policy.json
```

The site pages are generated from it with `tools/make_privacy_pages.py` and
copied into this repository's `privacy/blocks/` directory. When a policy
changes, bump its `version`, regenerate the pages, and update this repository.
