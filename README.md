# Nour-API documentation site

This repository contains generated Docusaurus output on `gh-pages`. The original Docusaurus source/build configuration is not present in the five project checkouts.

`guide/index.html` is an exact local mirror of the maintained engineering guide in the sibling `docs` repository. Edit `docs/guide/source.json` or `docs/examples/application.php`, then run from that checkout:

```sh
python3 tools/render-guide.py --mirror ../nour-api.github.io
python3 tools/render-guide.py --mirror ../nour-api.github.io --check
php tools/test-examples.php
```

Do not independently edit the mirrored HTML. Historical generated pages remain pending recovery of their original source. These instructions only generate local files; they do not publish a website.

## Development CI

The mirror workflow compares this checkout with the canonical source from `nour-api/docs` on `dev`, then executes the canonical HTTP examples against `nour-api/framework` on `dev` using PHP 8.2 and 8.5. It checks PHP syntax and audits runtime dependencies. Repository permissions are read-only and the workflow has no deployment steps.

A guide update must be rendered and committed in both documentation repositories. Push both development branches, then rerun any drift check that started before the second push arrived. Rerun documentation checks after framework-only changes as well; cross-repository pushes do not automatically trigger this workflow. Each result applies to the commits checked out in that run.
