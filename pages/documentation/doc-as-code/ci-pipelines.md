---
title: CI Pipelines
parent: Documentation-as-code
nav_order: 3
layout: default
---

# CI für Documentation-as-code

There are some useful steps we can integrate in our build process every time the documentation has changed.

## Markdown linting

To unify the markdown style and prevent broken links, a markdown linter like [markdownlint](https://github.com/DavidAnson/markdownlint) is highly recommended. We can configure in the markdown file itself or in a project configuration file which rules should be used. These rules are then respected both by the [command line tool](https://github.com/igorshubovych/markdownlint-cli) and the [VS Code extension](https://github.com/DavidAnson/markdownlint).

Have a look at [this GitHub action](https://github.com/neshanjo/what2eat/blob/with-cache/.github/workflows/lint-markdown.yml) which runs markdownlint in order to check for errors. The project configuration can be found in [this file](https://github.com/neshanjo/what2eat/blob/with-cache/.markdownlint.jsonc).

## PDF generation

As pointed out in [this article](generate-pdf-from-markdown.md), an up-to-date PDF version of the documentation can be handy.

[This GitHub action](https://github.com/neshanjo/what2eat/blob/with-cache/.github/workflows/markdown-to-pdf.yml) uses pandoc and weasyprint[^1] to generate a PDF documentation and publishes it as a release. Hence, the most recent version can be downloaded from the (permanent) link <https://github.com/neshanjo/what2eat/releases/latest/download/architecture-documentation.pdf>.

[^1]: This action does not use pagedjs-cli since weasyprint can be installed much faster on the GitHub runner than pagedjs-cli.
