---
title: "Multimodal Family Letter Archive"
collection: portfolio
permalink: /portfolio/family-archive/
excerpt: "AI-assisted multimodal archive pipeline for scanned family letters: vision-language segmentation, handwritten transcription, translation, provenance tracking, generated reader outputs, and Cloudflare Zero Trust deployment."
date: 2026-05-11
---

Family Archive is an AI-assisted multimodal document pipeline for scanned
family letters. It turns long, mixed-quality PDF scans into a structured archive
by combining page extraction, vision-language page understanding, handwritten
transcription, translation, provenance tracking, and generated reader outputs.

The core technical problem is multimodal: a single source PDF can contain many
letters across uneven scans, cursive handwriting, faded ink, Hungarian and
English text, date evidence, marginalia, and page-order ambiguity. The pipeline
uses vision-capable models to classify pages and propose letter boundaries, then
sends each confirmed letter as an ordered multi-image transcription task. The
transcription output stays in the original language; translation into English is
a separate downstream stage.

The system is designed for reviewable AI work rather than one-shot OCR. Every
stage writes artifacts to disk, records model and prompt metadata, skips
completed work unless explicitly forced, and keeps generated text traceable back
to source PDFs, page images, letter IDs, and review status. That makes the
archive rerunnable as vision models, prompts, and human corrections improve.

## Result

The current archive pass covers 12 source PDF sets, 1,048 extracted page images,
339 reviewed letter manifests, 988 linked facsimile pages, 339 original-language
transcriptions, and 339 completed English translations.

The generated reader and export layers are derivative views over the structured
archive, not replacements for the underlying evidence. They make the material
searchable and readable while preserving the chain from source scan to AI output
to reviewed archival record.

The private reader is deployed as a Cloudflare Pages site behind Cloudflare
Access / Zero Trust. Access is restricted to an allowlist of family email
addresses using one-time PIN login, and the generated `pages.dev` hostname is
redirected to the protected custom domain so static letter pages and direct
facsimile image URLs do not become a public back door.

Because the materials are private family records, the public website describes
the pipeline and results rather than publishing the letters themselves.
