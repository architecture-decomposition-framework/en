---
title: Documentation
nav_order: 5
layout: default
---

{: .translation }
This page has been machine-translated and has not yet been reviewed. Parts of its content may be incomplete or incorrect.

<!-- markdownlint-disable-next-line blanks-around-headings -->
# Architecture Documentation with the ADF
{: .no_toc }

{: .highlight }
Software architecture documentation makes design decisions about a software system understandable and helps various stakeholders get an overview of the software system.

<!-- markdownlint-disable-next-line blanks-around-headings -->
## Using the Documentation Template
{: .no_toc }

The documentation template contains many usage tips in the first section. It can be filled out retrospectively or used to support architecture work throughout the project. The template is maintained and versioned in a separate GitHub repository:

[To the template (German)](https://github.com/architecture-decomposition-framework/adf-documentation-template/blob/main/template/architecture-documentation-de.md){: .btn .btn-primary }
[To the template (English)](https://github.com/architecture-decomposition-framework/adf-documentation-template/blob/main/template/architecture-documentation-en.md){: .btn .btn-primary }

To easily edit the documentation and make it available to as many people as possible in the current version, the Documentation-as-Code approach is recommended, which is described in detail at the following link.

[Tooling Notes: Documentation-as-code](doc-as-code/){: .btn }

Other topics in this document:

- TOC
{:toc}

## Why Write Documentation at All?

Contrary to the statement of some developers, **the source code** of the system alone **is not sufficient** as documentation. While it includes the current state of the system more up-to-date than any other documentation, it is too time-consuming to reconstruct the architecture of the system from this high level of detail for further architectural decisions. For this, an **abstract representation of the system** is needed, showing the essential structures and relationships in the system. Additionally, the source code usually does not document **why** certain things were implemented in a specific way and **which alternative approaches** were discarded.

## Typical Content of an Architecture Documentation

When looking at various architecture documentations and templates, one often finds the following information:

- Architecture drivers (i.e., requirements relevant to the system's architecture) in the form of
  - **Business goals**,
  - **Constraints** (technical, organizational, legal, ...),
  - **Quality goals** (usability, scalability, testability, ...) and
  - **Core functions** (important functionality that makes the system usable)
- a description of the **system context** (system versus external systems or services interacting with the system),
- descriptions of the system in **various levels of detail** (coarse functional decomposition, finer representation of individual services, ...)
- descriptions of the system from **different perspectives** (deployment, interaction of system parts, source code structure, ...), as well as
- representations of various **concepts** (logging, backup, scaling, multi-tenancy, ...).

## Goal of the ADF Documentation Template

The ADF documentation template aims to promote the following characteristics of an architecture documentation:

- **"Readable"**: The document can be read from front to back without breaks between chapters and without many jumps through forward references.
- **Quick basic understanding of the system**: There is a manageable number of sections, after reading which one is familiar with the essential business context and the basic architecture of the system.
- **Self-contained chapters**: Given a basic understanding of the system, the main statements of a chapter can be understood without having read other chapters.
- **Traceability of architectural decisions**: It is clear why certain decisions were made and what alternatives existed.

{: .hint }
To what extent these goals are actually achieved depends, of course, significantly on how well the specific documentation is ultimately written.
