---
title: CollectorCheck Receipt Format
description: Receipt ingestion and deterministic verification rules.
---

# Receipt Format and Verification

CollectorCheck uses a deterministic receipt ingestion and verification model designed for clarity, provenance integrity, and audit‑friendly behavior.

## Accepted Formats

CollectorCheck v1 accepts:

- JPEG images
- PNG images
- PDF documents

All formats are processed deterministically.

## Required Fields

A valid receipt must contain:

- seller name
- item description
- purchase date
- price
- unique receipt identifier (if present)

If any field is missing, CollectorCheck will still ingest the receipt but will mark the missing fields in the verification output.

## Verification Logic

CollectorCheck applies deterministic verification steps:

1. Parse receipt fields
2. Normalize text and metadata
3. Validate structure
4. Generate authenticity score
5. Produce continuity record

Each step produces consistent results for identical inputs.

## Provenance Metadata

CollectorCheck attaches metadata to each verification:

- timestamp
- parsing confidence
- authenticity score
- continuity record ID

## Status

This receipt format and verification model defines the foundation for CollectorCheck v1 and will expand as the provenance pipeline matures.
