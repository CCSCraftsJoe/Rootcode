# Rootcode

**Rootcode** is an open visual writing system created by Joe Culver / Culver Sculpture for *Roots & Signals*. This repository is the public, canonical technical definition of the alphabet.

Rootcode maps the Latin alphabet **A–Z** to 26 geometric glyphs designed for physical fabrication and machine vision. Words are vertical stacks read **bottom-to-top**. Adjacent characters share hollow terminal circles; interior nodes are filled.

## Rootcode 1.0

- 26 canonical glyphs, A–Z
- exact vector geometry in `data/rootcode-1.0.json`
- formal construction and composition rules in `SPECIFICATION.md`
- labeled alphabet reference in `glyphs/rootcode-1.0-alphabet.svg`
- JSON Schema in `data/rootcode-1.0.schema.json`
- machine-vision dataset conventions in `DATASET.md`
- minimal MIT-licensed renderer in `reference/rootcode.js`

The 1.0 release documents geometry already used by the working Rootcode generator/decoder. Publishing this repository does **not** change those deployed tools.

## Licensing

Reference code is **MIT**. The Rootcode specification, glyph geometry, documentation, images, and project-produced datasets are **CC BY 4.0**.

Suggested attribution: **Rootcode — Joe Culver / Culver Sculpture, CC BY 4.0.**

## Canonical status

`1.0.0` is the canonical public baseline. Implementations should identify the version they target and should not silently alter canonical glyph geometry.


## Canonical web reference

The canonical public web reference is: https://www.culversculpture.com/rootcode

This page is intentionally omitted from the exhibition site's normal navigation while remaining public and crawlable.
