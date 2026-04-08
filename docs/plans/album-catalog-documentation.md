# Album Catalog Documentation Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Generate three documentation files for each of the 371 album directories: "专辑基本信息.md", "Booklet 完整原文.md", and "Booklet 完整中文翻译.md"

**Architecture:** Process albums alphabetically, one at a time. For each album: (1) read cover/back cover images for metadata, (2) OCR all booklet images for original text, (3) translate to Chinese, (4) validate with subagents for barcode accuracy and content completeness.

**Tech Stack:** Markdown documentation, OCR via multimodal AI, subagent validation

---

## Processing Workflow Per Album

Each album requires these steps in order:

1. Enter album directory
2. Read cover/back cover images to extract metadata (title, artist, label, release date, tracks, barcode)
3. Search for album on MusicBrainz/Discogs for verification URL
4. Generate "专辑基本信息.md"
5. Subagent validates barcode/EAN matches back cover
6. OCR all images in scans/ subdirectory (or root if no scans subdir)
7. Generate "Booklet 完整原文.md"
8. Subagent re-OCRs to verify completeness
9. Subagent checks accuracy, completeness, grammar
10. Generate "Booklet 完整中文翻译.md"
11. Subagent checks translation accuracy, completeness, grammar

---

## Task List

### Task 1: Process First Album Directory

**Files:**
- Target: First alphabetically sorted album directory
- Create: `<album-dir>/专辑基本信息.md`
- Create: `<album-dir>/Booklet 完整原文.md`
- Create: `<album-dir>/Booklet 完整中文翻译.md`

- [ ] **Step 1: Identify first album directory alphabetically**

Run: `ls -1 | sort | head -1`
Expected: First directory name in alphabetical order

- [ ] **Step 2: Enter directory and list contents**

Navigate to the first album directory and run: `ls -la`
Expected: List of files including images (jpg, png) and possibly a scans/ subdirectory

- [ ] **Step 3: Identify cover images for metadata extraction**

Look for files named: cover.jpg, front.jpg, back.jpg, folder.jpg, or similar
Expected: At least one front cover and one back cover image identified

- [ ] **Step 4: Extract metadata from cover images**

Use multimodal AI to read front and back cover images:
- Album title
- Artist/performer names
- Record label
- Release/catalog year
- Track listing
- Barcode/EAN

- [ ] **Step 5: Search for album verification URL**

Search MusicBrainz, Discogs, Presto Music for this album
Expected: At least one valid URL confirming album existence

- [ ] **Step 6: Generate "专辑基本信息.md"**

Create file with all extracted metadata in structured format

- [ ] **Step 7: Validate barcode with subagent**

Subagent re-reads back cover image and confirms barcode matches document
If mismatch: correct the document

- [ ] **Step 8: Locate and OCR booklet images**

If scans/ subdirectory exists: OCR all images inside
Otherwise: OCR all images in album directory
Expected: Complete booklet text extracted

- [ ] **Step 9: Generate "Booklet 完整原文.md"**

Create file with complete OCR text, preserving formatting

- [ ] **Step 10: Validate OCR completeness with subagent**

Subagent re-scans all images and compares against generated document
If gaps found: update document

- [ ] **Step 11: Validate accuracy and grammar with subagent**

Subagent reviews document for OCR errors, grammar issues
If issues found: correct document

- [ ] **Step 12: Generate "Booklet 完整中文翻译.md"**

Translate complete original text to Chinese, preserving structure

- [ ] **Step 13: Validate translation with subagent**

Subagent checks translation accuracy, completeness, grammar
If issues found: correct document

- [ ] **Step 14: Commit changes**

```bash
git add "<album-dir>/专辑基本信息.md" "<album-dir>/Booklet 完整原文.md" "<album-dir>/Booklet 完整中文翻译.md"
git commit -m "docs: add album documentation for <album-name>"
```

---

## Continuation Protocol

After completing Task 1:

1. Run `TaskList` to verify completion
2. Move to next alphabetically sorted album
3. Repeat Task 1 steps for each subsequent album
4. Continue until all 371 albums are processed

**Note:** This plan intentionally defines the workflow for ONE album in detail. The same pattern repeats for all 371 albums. Use subagent-driven-development to process multiple albums in parallel where possible.

---

## Validation Commands

After processing each album, verify:
- All 3 files exist in album directory
- Files are non-empty
- Git status shows expected changes

```bash
ls "<album-dir>/专辑基本信息.md" "<album-dir>/Booklet 完整原文.md" "<album-dir>/Booklet 完整中文翻译.md"
wc -l "<album-dir>/专辑基本信息.md" "<album-dir>/Booklet 完整原文.md" "<album-dir>/Booklet 完整中文翻译.md"
```
