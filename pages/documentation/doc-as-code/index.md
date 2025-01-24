---
title: Documentation-as-code
parent: Documentation
nav_order: 4
layout: default
---

<!-- markdownlint-disable-next-line blanks-around-headings -->
# Documentation-as-code (ADF) <!-- omit in toc -->
{: .no_toc }

<!-- markdownlint-disable-next-line blanks-around-headings -->
## Content <!-- omit in toc -->
{: .no_toc }

- TOC
{:toc}

## What is documentation-as-code?

*Documentation-as-code* means to

1. put your documentation (usually, the architecture documentation) as close as possible to the source code and make sure that it is under version control,
2. choose a format that any developer can edit with low effort, and
3. make up-to-date documentation accessible to everyone (including non-tech-people) in an easily consumable format.

## Why documentation-as-code?

Most developers prefer implementing new features over documenting their architecture. If they are additionally forced to leave their familiar development environment to deal with stubborn Word templates and documents on VPN-protected network drives, the chances of the documentation matching the current state of development are relatively slim. To have an up-to-date, easily accessible documentation, we need something else than this.

## Documentation-as-code, generic implementation

Usually, the three points from above are addressed in this way.

Step 1: Just create a folder for the documentation in the project repository (e.g. Git repository) which also contains the corresponding source code. If you have multiple repositories for different parts of the software and need to document more than one part at once, an extra repository can be necessary - but be aware that this creates an additional indirection (a mono-repo approach can help here).

Step 2: Choose a plaintext format (with mark up possibilities) like Markdown, AsciiDoc, LaTeX or HTML. Decide which format to use for graphics. Options include vector graphics formats with IDE plugin support like Diagrams.net/Draw.io or Diagram-from-plaintext formats like PlantUML.

Step 3: With every commit, generate a human-friendly rich-text version of the documentation. This can be as simple as the Git server rendering an HTML page from Markdown or Asciidoc, or a more sophisticated process run by the build server that runs LaTeX and publishes PDFs to a shared file system.

## Documentation-as-code, the ADF realization

In this section, we describe our choice of tools and technologies to realize Steps 1 to 3. There are many other possibilities available with more flexible and advanced functions, but we choose one of the most simple solution on purpose, in order to to keep the entry barrier as low as possible.

This tool chain has been successfully used in different student projects even with unexperienced developers after not more than 60 minutes of introduction.

### Step 1 and Step 3

We assume that the source code is in one repository on a Git server that supports Markdown-to-HTML rendering, e.g. GitHub or GitLab. We just create a folder `documentation` with an file `architecture-documentation.md` and the content of the [ADF architecture documentation template](https://github.com/architecture-decomposition-framework/adf-documentation-template), see also section [Documentation](../).

As soon as we commit the changes and push to the server, we get an HTML page with the rendered documentation and can easily distribute it via the link to the repository. Even non-devs can be given roles with limited access (as the Reporter role in GitLab) such that they can browse the documentation.

This also works well with different (feature) branches with a (preliminary) updated version of the docs that can be reviewed by other people.

### Step 2

As the previous section already suggests, we use [Markdown](https://en.wikipedia.org/wiki/Markdown) as plaintext format. We do so since it is the simplest format for generating rich text documents and is widely used in other context (e.g. wikis). It has almost no learning curve and there there is excellent tool support - almost every IDE supports syntax highlighting and some autocompletion and autoformat functions.

As for diagrams, there are two options:

- [Using Diagrams.net (formerly known as draw.io)](../../views/tooling/diagrams-net-elements.html), an open source diagram creation tool that can embed the diagrams code directly into the output file (SVG or PNG).
- [Using PlantUML](../../views/tooling/plantuml-elements.html), where diagrams are specified as code and rendered by the IDE, a command line tool or during the build process.

Click on one of the links above to learn more about how to set up the tools to work in combination with Markdown and read more in the [Views-Section](../../views/) about how to create architecture diagrams "the ADF way".

### Examples

[This example documentation](https://github.com/neshanjo/what2eat/blob/with-cache/doc/architecture-documentation.md) is written in Markdown and directly embeds figures made with Diagrams.net. The same documentation, but all figures are created with PlantUML, can be found [following this link](https://github.com/neshanjo/what2eat/blob/with-cache/doc-plantuml/architecture-documentation-plantuml.md).

### Generate PDF documents from Markdown

It is sometimes necessary to archive certain versions of the documentation or send it by mail. Therefore, [PDF generation from Markdown](./generate-pdf-from-markdown.html) can be helpful.

## Presentation-as-code

Thanks to [Marp](https://marp.app/), the Markdown Presentation Ecosystem, simple and effective presentations can be easily generated by reusing Markdown code and figures from the documentation. The plugin [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) integrates Marp into VS Code.

The What2Eat example project also contains a [Marp example](https://raw.githubusercontent.com/neshanjo/what2eat/with-cache/doc/architecture-presentation.md) that illustrates some of the features in Marp. Note that the [version rendered by GitHub](https://github.com/neshanjo/what2eat/blob/with-cache/doc/architecture-presentation.md) is *not* the resulting presentation. The final presentation is demoed in [this PDF file](https://raw.githubusercontent.com/neshanjo/what2eat/with-cache/doc/architecture-presentation.pdf).
