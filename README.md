# Open Source Secure Document Redaction Engine

**Verifiable, irreversible redaction infrastructure for digital documents**

## Overview

This project provides an open-source, security-focused document redaction engine that performs **true data-level redaction** instead of visual masking.

Many existing redaction tools only hide sensitive content visually, while the underlying data remains present in the document and can often be recovered through text extraction, metadata inspection, or OCR techniques. This creates serious security risks and a false sense of safety.

This project treats redaction as **verified data destruction**, ensuring that redacted information is completely removed from the document structure and cannot be recovered by any known extraction method.

## Key Principles

- **Data-level redaction** (not visual masking)
- **Irreversible removal** of sensitive content
- **Deterministic and verifiable outcomes**
- **Open-source and auditable by design**
- **Infrastructure-first** (engine, library, CLI — not a SaaS)

## What the Engine Does

For supported document formats, the engine:

- Removes redacted text and objects directly from document structures
- Cleans metadata, hidden layers, unused objects, fonts, and glyph mappings
- Rewrites internal references safely (e.g. PDF cross-reference tables)
- Applies pixel-level overwrite for image-based documents
- Produces machine-readable verification reports

## Verification Layer

A core feature of this project is **verification**.

After redaction, the system automatically attempts to recover removed content using:
- Text extraction
- Structured parsing
- Optional OCR-based methods

The results are compared against pre-redaction data to confirm that sensitive information is **unrecoverable**.  
Verification outputs are provided as machine-readable reports that can be independently inspected.

## Intended Usage

The project is designed as a reusable infrastructure component:

- Command-line interface (CLI) for batch or scripted use
- Library/API for integration into document workflows
- Suitable for offline and self-hosted environments

No web interface or SaaS deployment is required.

## Target Use Cases

- Public institutions handling sensitive documents
- Courts and legal professionals
- Journalists and investigative reporters
- Researchers and archivists
- Developers building document processing pipelines

## Project Scope

This project is **not**:
- A commercial SaaS product
- A UI-focused end-user application
- A proprietary or vendor-locked solution

It is an open-source building block intended to improve the correctness and safety of existing redaction workflows.

## Technology Stack (Planned)

- Core language: Python
- PDF processing: pikepdf (qpdf), PyMuPDF, pdfminer.six
- Image processing: Pillow, OpenCV
- Optional OCR verification: Tesseract
- Testing: pytest, reproducible test corpus
- CI: GitHub Actions

All components are open-source and vendor-independent.

## Project Status

This repository is under active development.  
Initial focus is on architecture, secure redaction primitives, and verification methodology.

## License

This project is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

## Team

- **Ragıp Günay** – Project Lead (Computer Engineer)
- **Duygu Kamalak** – Computer Engineer
- **Senem Ürkmez** – Computer Engineer
- **Emir Sercan Korkmazgil** – Computer Engineer
