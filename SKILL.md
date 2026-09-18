---
name: docx-delivery-qa
description: Use when creating, editing, integrating, reviewing, or delivering Word DOCX documents. Preserve originals, place additions in the correct body context, validate package structure and content, and perform rendering-level QA before claiming delivery readiness.
---

# DOCX Delivery and Quality Assurance

## Purpose

Produce a usable Word deliverable from supplied material while preserving provenance, editable structure, and visual integrity. Treat the document package, extracted text, and rendered pages as three separate evidence layers.

This skill does not invent identity, attendance, grades, awards, approvals, deadlines, or other personal or institutional facts that are not supported by the supplied material.

## Activate when

- The user asks to create, revise, merge, format, cover, redline, inspect, or deliver a `.docx` file.
- A report, proposal, resume, manual, application, or official template must be produced.
- A document must be checked for page layout, images, tables, headings, references, or placeholders.
- The user says to add content directly into the正文/body, preserve the original, or add an independent cover page.

## Delivery principles

1. Preserve the original. Work on a copy or create a clearly named new output.
2. Keep additions in the matching chapter or正文 location unless the user explicitly requests an appendix.
3. Treat an independent cover as a separate first page; body content should begin on page two when that is the requested layout.
4. Separate supported facts, user-verification placeholders, editorial suggestions, and unsupported claims.
5. Do not call a document ready from package parsing alone. Render it and inspect the pages.

## Operating procedure

### 1. Inventory the source material

Record the input path, output path, file hash when useful, page/section expectations, authoritative template, and factual constraints. Inspect the current document before editing:

- paragraph and heading structure;
- tables and merged cells;
- sections, margins, headers, footers, page breaks, and numbering;
- embedded images and relationships;
- fields, hyperlinks, comments, tracked changes, and placeholders.

If an exact paragraph match fails, locate the surrounding stable heading or a distinctive substring rather than rewriting unrelated content.

### 2. Establish the content ledger

For each proposed addition, label it as one of:

- `SUPPORTED`: directly present in the source materials;
- `USER_VERIFY`: plausible but requires the user's confirmation;
- `EDITORIAL`: wording, structure, or formatting guidance;
- `UNSUPPORTED`: do not include as fact.

Keep names, dates, institutions, roles, awards, attendance, results, and accomplishments in `USER_VERIFY` unless authoritative evidence is present.

### 3. Edit with structural preservation

Use the document's existing styles and numbering when possible. Make the smallest focused edit that satisfies the request. Keep tables, captions, cross-references, hyperlinks, equations, and images intact. Do not flatten an editable document into screenshots or a PDF when a DOCX is requested.

When adding a cover:

- create a new output or backup first;
- insert a real section/page break, not a large stack of blank paragraphs;
- keep the cover content on the first page;
- verify that the original body starts on page two;
- preserve the body sections and embedded images.

### 4. Run structural QA

At minimum, compare before and after:

- paragraph and table counts;
- section count and section breaks;
- embedded image count and relationship targets;
- heading sequence and required chapters;
- hyperlinks, fields, and obvious placeholders;
- file opening/ZIP integrity;
- output hash recorded for the final artifact.

Structural checks prove package consistency, not visual correctness.

### 5. Render and inspect

Render the DOCX with an available Word-compatible renderer. Inspect every page or a representative page set that includes the cover, first body page, dense tables, figures, equations, headers/footers, and final page. Check for:

- clipped or overlapping text;
- blank or unexpectedly sparse pages;
- broken fonts, symbols, equations, or image aspect ratios;
- orphaned headings and bad page breaks;
- table overflow and footer/header collisions;
- cover/body separation;
- readable captions and references.

If a renderer is unavailable, report `STRUCTURAL_ONLY` and do not claim rendering-level readiness.

### 6. Deliver with a QA report

Return the output path, preservation/backup path, factual caveats, structural results, rendering results, known limitations, and the exact verification command or procedure used.

## Response contract

Use this order:

1. plain-language delivery status;
2. output and backup paths;
3. what was changed and where;
4. factual evidence boundary;
5. structural QA result;
6. rendering QA result;
7. remaining user checks.

Use calibrated labels such as `DRAFT`, `STRUCTURAL_QA_PASS`, `RENDER_QA_PASS`, `USER_CONFIRMATION_REQUIRED`, and `NOT_VERIFIED`.

## Stop conditions

Stop or downgrade the claim when:

- the original would be overwritten without a recoverable copy;
- the authoritative template or source facts are missing;
- the output opens but page rendering has not been inspected;
- the requested cover image, identity, date, or result is unconfirmed;
- Word-compatible rendering fails or differs materially from the expected layout.

