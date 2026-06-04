# AI-Assisted Documentation

## Purpose

This repository tracks AI-assisted documentation tasks for updating, revising, and translating online help (OLH) manuals, starting from existing FrameMaker source files.

The workflow leverages AI tools to analyse, revise, improve, and translate documentation content while maintaining consistency with the original FrameMaker structure and ECO3 documentation standards.

---

## Background

Online help manuals for ECO3 products (Apogee, ProductionCenter, PrintSphere) are authored in Adobe FrameMaker. This project establishes a structured AI-assisted workflow to:

- Review and update existing OLH content
- Identify gaps, inconsistencies, and outdated information
- Improve RAG-readiness of documentation for AI-powered search tools
- Maintain alignment with current product versions
- Translate OLH content into target languages using AI assistance
- Review and improve existing translated content for accuracy and consistency

---

## Reference Documents

| File | Description |
|---|---|
| `Starter_kit_FrameMaker.docx` | Chat session export — initial setup and approach for working with FrameMaker files using AI assistance |
| `Updating_FrameMaker_files.docx` | Chat session export — workflow and methodology for updating FrameMaker-based OLH content |

---

## Scope

| Dimension | Count | Notes |
|---|---|---|
| English FM books | 15 | Processed one book at a time |
| Pages per book | 100–1000 | Larger books split by chapter for AI processing |
| Translation languages | 10 | All in FM format — same MIF workflow as English |
| Translation FM files | ~45 *(to be confirmed)* | Not every book exists in every language |
| **Total FM files in scope** | **~60** | Exact translation count to be updated |

---

## Workflow

Each FM book is processed through three sequential phases. **Phase 3 (translations) only starts after the English version is signed off.**

### Phase 1 — Proofread English

```
.fm (English) → export to MIF
→ OpenCode: correct spelling, grammar, terminology, punctuation
→ review and approve
→ re-import into FrameMaker → save .fm
```

### Phase 2 — Technical update (English)

```
Spec / tech note (PDF or Word) + Phase 1 output MIF
→ OpenCode: compare spec against OLH content
→ update outdated sections, add new features
→ review and approve → re-import into FrameMaker
→ ✓ English signed off — gate before Phase 3
```

### Phase 3 — Update translations (~45 FM files, 10 languages)

```
English OLD MIF vs. English NEW MIF → WinMerge diff → changed segments only
For each language FM file:
  → export to MIF → locate segments matching English changes
  → DeepL first-pass translation → OpenCode review and refinement
  → re-import into FrameMaker → save .fm
```

> **Starting point:** always the current English version for Phase 1 and 2; current language version for Phase 3.



## Tools

### Currently installed

| Tool | Version | Purpose |
|---|---|---|
| Adobe FrameMaker | 2015 | Authoring and publishing OLH manuals (`.book`, `.fm`, MIF export) |
| WebWorks Publisher | 2019.2 | Publishing FrameMaker content to online help output formats |
| OpenCode | — | AI-assisted content rewriting, revision, and translation |
| Node.js | v24 | Runtime for the Playwright screenshot tool |
| Playwright | — | Automated browser-based UI screenshots |
| Snagit | — | Manual one-off screenshots |
| Git | — | Version control |
| GitHub / GitHub Pages | — | Repository hosting and live documentation page |

### Planned

| Tool | Purpose |
|---|---|
| WinMerge | Diff MIF files between versions to isolate changed segments |
| DeepL (desktop app) | First-pass machine translation of changed segments across 10 languages — free to install |

---

## Related Projects

| Repository | Purpose |
|---|---|
| `Apogee_Essentials_Edition` | AI-assisted HTML product page creation and SEO |
| `APAI_Chat` | Document tracking and RAG-readiness scoring for APAI Chat knowledge base |
| `PrintSphere` | OLH review, implementation guides, and automated UI screenshots |

---

## Screenshots

UI screenshots for OLH documentation are captured with a **Playwright** automation tool.  
The tool is launched from a desktop shortcut and runs in two steps: select the application, then select the page.

**Launcher:** `D:\Users\AQCWT\OpenCode_Doc\PrintSphere\playwright\take_screenshot.bat`  
**Screenshots saved to:** `D:\Users\AQCWT\OpenCode_Doc\PrintSphere\screenshots\`

Currently supported application: **PrintSphere** (`www.printsphere.com`)

> For one-off screenshots, **Snagit** is preferred. The Playwright tool is best for automated or repeated captures.

---

## Labels

`documentation` `ai-assisted` `framemaker` `online-help` `olh` `apogee` `eco3` `translation`
