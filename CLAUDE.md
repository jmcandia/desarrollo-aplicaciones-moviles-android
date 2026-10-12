# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains the source content for an online educational book on **Kotlin and modern Android development**, authored in Markdown and rendered via **MkDocs** with the **Material for MkDocs** theme.

### Editorial Boundary & Scope (Strict)
- **The deliverable is educational content**: Markdown chapters, conceptual walkthroughs, diagrams (Mermaid), code snippets, exercises, and written tutorials.
- **Do NOT build or implement the ParkFlow application**: ParkFlow is strictly a fictional/didactic case study providing continuity across examples. Do not implement a runnable production application, create deployable standalone projects, configure live Firebase/backend infrastructure, or register real developer credentials.
- See `AGENTS.md` for the complete editorial charter, pedagogical standards, and chapter templates.

## Architecture & Structure

The repository follows standard MkDocs conventions with an educational curriculum structure:

- `mkdocs.yml`: Configuration file and canonical editorial contract. The `nav` defines the authoritative table of contents and reading sequence. Unit order and chapter titles in `nav` must not be altered or omitted.
- `AGENTS.md`: Full editorial specification and pedagogical requirements for every chapter, tutorial, and acceptance criteria.
- `CHANGELOG.md`: Project change log following [Keep a Changelog 1.1.0](https://keepachangelog.com/es-ES/1.1.0/) and Semantic Versioning. Relevant milestones must be recorded under `[Sin publicar]`.
- `requirements.txt`: Python package dependencies (`mkdocs==1.6.1`, `mkdocs-material==9.7.7`).
- `.github/workflows/deploy-docs.yaml`: GitHub Actions pipeline deploying to GitHub Pages on pushes to `main`.
- `docs/`: Root folder for documentation and chapters.
  - `index.md`, `como-usar-el-libro.md`, `convenciones-y-laboratorios.md`: Landing page, usage guide, and lab conventions.
  - `unidad-1-kotlin/`: Unit 1 — Autonomous Kotlin fundamentals (console/JVM only; strictly no Android Studio, Compose, Activity, or Android APIs).
  - `unidad-2-android/`: Unit 2 — Android development (Compose, Material 3, Room, DataStore, MVVM, Chilean license plate validation with mandatory photo, offline-first).
  - `unidad-3-integracion-y-distribucion/`: Unit 3 — Integration, quality, and distribution (managed services / Firebase evaluation, offline sync, idempotency, Keystore, testing strategy, signing, and distribution).
  - `apendices/`: Dedicated conceptual appendices strictly limited to OOP pillars (`pilares-poo.md`), SOLID (`solid.md`), and KISS/DRY (`kiss-y-dry.md`).
  - `referencias.md`: Final item in `nav`, compiling verified primary sources (official Kotlin, AndroidX, LeyChile/BCN, etc.).
  - `assets/`: Styling (`assets/css/custom.css`), navigation accordion script (`assets/js/custom.js`), and images.

## Development Commands

A Python virtual environment is set up in `venv/`.

### Virtual Environment Setup & Dependencies
```powershell
# Windows (PowerShell)
.\venv\Scripts\python.exe -m pip install -r requirements.txt
```

### Local Development Server (Live Reload)
```powershell
.\venv\Scripts\python.exe -m mkdocs serve
# Default URL: http://127.0.0.1:8000
```

### Build Documentation
```powershell
# Standard build (outputs static site to site/)
.\venv\Scripts\python.exe -m mkdocs build

# Strict build (matches CI workflow; fails on broken links or missing nav pages)
.\venv\Scripts\python.exe -m mkdocs build --strict
```

### Deployment
Deployment is automated via GitHub Actions on push to `main`. To manually deploy to GitHub Pages:
```powershell
.\venv\Scripts\python.exe -m mkdocs gh-deploy --force
```

## Writing & Content Rules

- **Language & Style**: Text must be in clear, grammatically correct Spanish with full orthographic accuracy (diacritics and accents). Official technical terms, APIs, tools, and types remain in English (defined on first appearance).
- **Page Structure**: Exactly one H1 per Markdown page, matching the corresponding label in `mkdocs.yml` `nav`. Headings must follow strict hierarchical order (do not skip levels).
- **Domain Accuracy**:
  - Chilean currency (CLP): Represent with integer or appropriate decimal units, never raw `Float`/`Double` for financial arithmetic.
  - Chilean license plates (PPU): Validate formats explicitly against official Chilean regulations (LeyChile/BCN); clarify that regex validation does not verify official vehicle registration status.
  - Dates & Timezones: Use explicit date, time, and timezone handling for session calculations and tariff periods.
- **Code Snippets**: Always specify language syntax. Never present pseudocode as compilable Kotlin; label incomplete fragments or pseudocode explicitly. In Unit 1, all code must be runnable Kotlin/JVM without Android dependencies.
- **Diagrams**: Use accessible Mermaid syntax within fenced code blocks (````mermaid ... ````) supported by `pymdownx.superfences`, accompanied by textual explanations.

## Editorial Structure & Templates (from AGENTS.md)

### Conceptual Chapter Structure
Every conceptual chapter must adhere to the 10-part structure defined in `AGENTS.md`:
1. Title matching `nav` (single H1).
2. Concrete learning objectives.
3. Prerequisites and internal links to prior pages.
4. Progressive explanation with concepts and defined vocabulary.
5. Developed examples with expected outcomes.
6. Edge cases, common errors, and decision criteria.
7. Application to ParkFlow only where pedagogically natural.
8. Progressive exercises and self-evaluation with verifiable criteria.
9. Concise summary of key takeaways.
10. In-context citations and links to `referencias.md`.

### Progressive Tutorial Requirements
Tutorials modify the cumulative state of ParkFlow in orderly milestones:
- State what is built and what is excluded.
- Explicit prerequisites and previous tutorials.
- Verifiable starting point and expected final outcome.
- Numbered steps with objective, design decision, and observable result.
- Sufficient, exact code (no gaps preventing execution).
- Predictable errors and diagnostic steps.
- Verification checkpoint activity at the end of each milestone.
- Links to the conceptual chapters explaining the theory.

### Source Hierarchy & Citations
1. Official platform/language/vendor documentation (Kotlin, Android Developers, AndroidX, Gradle, Firebase, Google Play).
2. Official Chilean legislation and registries (LeyChile/BCN).
3. Primary technical specifications and standards.
4. Secondary sources only for context (never as the sole backing source).
- Every claim must link its source in context and be documented in `docs/referencias.md`.

## Changelog & Versioning (from CHANGELOG.md)

- Keep `CHANGELOG.md` updated following [Keep a Changelog 1.1.0](https://keepachangelog.com/es-ES/1.1.0/) and Semantic Versioning.
- Log any new chapters, completed units, architectural adjustments, or configuration changes under `## [Sin publicar]`.
- Categories to use: `Añadido`, `Modificado`, `Deprecado`, `Eliminado`, `Corregido`, `Seguridad`.
