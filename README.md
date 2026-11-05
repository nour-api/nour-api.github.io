# Nour-API documentation site

This repository contains generated Docusaurus output on `gh-pages`. The original Docusaurus source/build configuration is not present in the five project checkouts.

`guide/index.html` is an exact local mirror of the maintained engineering guide in the sibling `docs` repository. Edit `docs/guide/source.json` or `docs/examples/application.php`, then run from that checkout:

```sh
python3 tools/render-guide.py --mirror ../nour-api.github.io
python3 tools/render-guide.py --mirror ../nour-api.github.io --check
php tools/test-examples.php
```

Do not independently edit the mirrored HTML. Historical generated pages remain pending recovery of their original source. These instructions only generate local files; they do not publish a website.
