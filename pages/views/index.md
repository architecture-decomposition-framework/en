---
title: Modeling/Visualization
nav_order: 6
layout: default
---

{: .translation }
This page has been machine-translated and has not yet been reviewed. Parts of its content may be incomplete or incorrect.

<!-- markdownlint-disable-next-line blanks-around-headings -->
# Architecture Modeling/Visualization with the ADF
{: .no_toc }

{: .highlight }
It makes sense not to describe a complex system in a single diagram but to create multiple diagrams for different aspects. 
**The ADF framework defines different view types along with associated elements and relations.** For example, in a diagram of the view type "Functions at Runtime," one can immediately recognize the functional areas, their division, and their interaction. Unlike building architecture (keyword "floor plan" or "blueprint"), no unified notation has been established in software engineering, and often many different aspects are mixed in one diagram.

<!-- markdownlint-disable-next-line blanks-around-headings -->
## Using ADF Views
{: .no_toc }

First, one should understand the dimensions by which a system can be decomposed and the different view types.

[Explanation of Dimensions](dimensions/){: .btn .btn-primary }

For an architectural view of a specific type, there are suitable elements and relations.

[Overview of Elements](elements/){: .btn .btn-primary }

It is best to look at a few examples of views of different types.

[Examples](examples/){: .btn .btn-primary }

<!-- markdownlint-disable-next-line blanks-around-headings -->
## Tooling
{: .no_toc }

Architecture modeling/visualization with the ADF is a method that can be used independently of tools and technologies. ADF views can be drawn with any diagram tools or directly on the whiteboard. For the tools Diagrams.net and PlantUML, we have created pre-made elements and relations that can be used directly.

[To Tooling](tooling/){: .btn }

Other topics in this document:

- TOC
{:toc}

## Why Different Views?

<!-- English We use to breakdown complex matters into manageable chunks all the time. To understand how the human body works, a medical student uses many different figures illustrating the skeleton, the muscle apparatus, the vascular system, ... - and even different diagrams for different body parts. The house building architect makes a site plan as an overview, floor plans for each story, different perspectives of outer walls and the roof construction and dedicated diagrams showing power lines and outlets. So what about software?

> “It is not possible to capture the functional features and quality properties of a complex system in a single comprehensible model that is understandable by and of value to all stakeholders.” [Rozanski, Woods, 2005]

While it is tempting to describe a software system in its full detail within one big diagram (and people try and fail doing so again and again), a much more feasible approach is to describe a system from different views.
-->
We constantly break down complex matters into manageable parts. To understand how the human body works, a medical student uses many different illustrations showing the skeleton, the muscle system, the vascular system, etc. - and different diagrams for different body parts. The building architect creates a floor plan as an overview, floor plans for each floor, different views of the outer walls and the roof structure, and special diagrams showing power lines and outlets. And what about software?

> “It is not possible to capture the functional features and quality properties of a complex system in a single comprehensible model that is understandable by and of value to all stakeholders.” [Rozanski, Woods, 2005]

While it is tempting to describe a software system in all its details in one big diagram (many people try and fail regularly), a much more feasible approach is to describe a system from different perspectives.

## No Standard for Architectural Views

UML class, package, and sequence diagrams, which represent the code structure, are well known and widespread but have two disadvantages:

1. They describe many implementation details that may not be so relevant for an overall view and also quickly become outdated. (Some people therefore recommend using them sparingly and generating them automatically from the code.)
2. They can only be created when source code already exists or at least when it is known where code needs to be written (frontend versus backend, module in monolith versus separate microservice, ...). For new developments, it is more sensible to start from the running system, break it down into parts, and then consider how these parts can be implemented as code.

For **architecture work**, you need views that

- visualize larger contexts, such as the interaction of multiple systems,
- describe systems and components at runtime,
- show the deployment of the system in the infrastructure,
- map development and deployment processes,
- and much more.

Although there are various architectural view frameworks, such as the 4+1 model by Philippe Kruchten or the C4 model by Simon Brown, none of them has established itself as a general standard. The former has a steep learning curve due to the multitude of different diagram types and elements, while the latter is very restrictive with the four fixed "zoom levels." Most importantly, most models do not distinguish between views of a system **at runtime** and views of a system **at development time**.

With the **ADF view framework**, we provide a model for visualizing and modeling software systems that

- is **freely usable**,
- is **suitable for all types of systems**,
- makes it **very clear which aspect of the system is being described** through an explicit type system along the dimensions of runtime/development time and data/functions/deployment/activities, thus helping to avoid mixing too many different aspects of a system,
- can be used **immediately without software installation** [with a single click](https://app.diagrams.net/?splash=0&libs=general&clibs=Uhttps%3A%2F%2Fraw.githubusercontent.com%2Farchitecture-decomposition-framework%2Fadf-diagramsnet%2Fmain%2Flibraries%2FADF_SW%40RT.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Farchitecture-decomposition-framework%2Fadf-diagramsnet%2Fmain%2Flibraries%2FADF_Env%40RT.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Farchitecture-decomposition-framework%2Fadf-diagramsnet%2Fmain%2Flibraries%2FADF_SW%40DT.xml;Uhttps%3A%2F%2Fraw.githubusercontent.com%2Farchitecture-decomposition-framework%2Fadf-diagramsnet%2Fmain%2Flibraries%2FADF_Env%40DT.xml),
- has tool support through [diagrams.net (draw.io)](tooling/diagrams-net-elements.html) and [PlantUML](tooling/plantuml-elements.html) and is thus fully compatible with the [Documentation-as-code](../documentation/doc-as-code/) approach,
- is **extensively documented with examples** on this page.

The [ADF documentation template](../documentation/) complements the ADF view framework by creating a structure in which the views can be embedded.

The [ADF Design Guide](../design/) shows in which iterations one approaches a system decomposition and which views of which type are created.
