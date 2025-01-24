---
title: Tooling
parent: Modeling/Visualization
nav_order: 4
layout: default
---

{: .translation }
This page has been machine-translated and has not yet been reviewed. Parts of its content may be incomplete or incorrect.

# ADF Elements, Tool Support

The ADF elements are based on typical UML elements such as *Node*, *Component*, and *Class*. We provide these for two popular tools that fundamentally differ.

With **Diagrams.net (formerly draw.io)**, a powerful, open diagram tool is available, which can also run as a plugin in many development environments and embed the diagram code directly into the target format (PNG or SVG).

[ADF Views with Diagrams.net](diagrams-net-elements.html){: .btn .btn-primary }

**PlantUML** takes a different approach: Here, diagrams are specified as code (*Diagrams-as-code*) and converted into graphics (e.g., PNG or SVG) via command-line tools or the build process. PlantUML can be excellently embedded in Markdown and minimizes the media break in diagram creation. LLMs like GitHub Copilot can support not only syntactically but also semantically. However, the initial learning curve is higher - and the layout is not always exactly as desired.

[ADF Views with PlantUML](plantuml-elements.html){: .btn .btn-primary }
