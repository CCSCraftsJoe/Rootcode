# Rootcode Specification 1.0

**Status:** Canonical public baseline  
**Version:** 1.0.0  
**Date:** 2026-10-03  
**Creator:** Joe Culver / Culver Sculpture

## Scope

Rootcode is a 26-character visual writing system mapping directly to Latin A–Z. Version 1.0 standardizes glyph geometry, node treatment, terminal behavior, word composition, and reading direction.

This release formalizes the geometry used by `rootcode-generator-v1.4` and the P27.3.4 decoder reference library. It documents working behavior; it does not redesign the live generator or decoder.

## Character repertoire

`ABCDEFGHIJKLMNOPQRSTUVWXYZ`

Version 1.0 does not define numerals, punctuation, diacritics, lowercase variants, or spaces inside a Rootcode word stack.

## Reading and composition

A Rootcode word is a **vertical stack read from bottom to top**.

For plaintext `ROOTCODE`, the bottom glyph represents **R**, and reading upward yields `R-O-O-T-C-O-D-E`.

Each character occupies one construction unit. Adjacent characters share the terminal at their boundary: a word of *n* characters contains *n + 1* hollow terminal rings.

## Node grammar

- **Terminal nodes:** hollow circular rings on the centerline at character boundaries.
- **Internal nodes:** filled circular nodes belonging to character-specific geometry.

Internal nodes must remain filled in a canonical rendering. Terminal rings must remain hollow.

## Canonical construction metrics

Uniform scaling is conforming. Non-uniform scaling changes canonical proportions.

| Metric | Value |
| --- | ---: |
| Character unit height | 62.74 |
| Character cell width | 50.20 |
| Source top Y | 45.26 |
| Primary stroke width | 3.911811066 |
| Terminal ring radius | 4.705 |
| Terminal ring stroke width | 3.9123 |

## Canonical geometry

`data/rootcode-1.0.json` is the machine-readable source of truth for Rootcode 1.0. It records each glyph's source center, construction height, stroke-count metadata, normalized node topology, and SVG body geometry excluding shared terminal rings.

The generator glyph library establishing this release is identified by SHA-256:

`26d015a0f32519c4a027b054c05b305f88b6477a0e8169cb6f2cb2d1d3a1a5bb`

## Word rendering algorithm

1. Normalize input to uppercase A–Z.
2. Place glyph bodies on a shared vertical centerline.
3. Stack characters so plaintext is read bottom-to-top.
4. Draw one hollow terminal ring at every word boundary, including endpoints.
5. Share one terminal ring between adjacent glyph bodies.
6. Preserve canonical proportions under uniform scaling.

## Recognition

Recognition may use raster, vector, topological, or learned methods. Confidence scores and recognition strategy are implementation-specific, not part of the language definition.

Machine-vision labels should identify Rootcode version and plaintext ground truth. See `DATASET.md`.

## Versioning

Rootcode uses semantic versioning for the public specification. Intentional geometry changes to an existing glyph require a version change and must not silently replace the 1.0 definition.

## Licensing

Specification text, glyph geometry, documentation, images, and project-produced datasets are **CC BY 4.0**. Reference code is **MIT**.
