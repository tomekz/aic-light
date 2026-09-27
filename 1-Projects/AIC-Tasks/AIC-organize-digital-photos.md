# AIC-organize-digital-photos

## Task metadata

- **Status:** done
- **Owner:** Copilot session `Organize digital photos`
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Create a practical, beginner-friendly guide and reusable structure for safely
organizing a personal digital photo collection.

## Background / context

This repository is a PARA second brain whose durable guides and reference
material belong under `3-Resources/`. It contains no application code or test
framework. The root README explicitly uses a beginner guide for organizing
digital photos as an example AIC task, so this work should implement that
repository-native artifact rather than inventing a software feature.

The result must help a beginner consolidate photos from common sources, protect
the originals, remove clutter cautiously, apply a maintainable folder and file
naming system, add useful metadata, verify backups, and establish a lightweight
ongoing routine. It must not require access to a real photo library.

## Scope

- Create a standalone digital photo organization guide under `3-Resources/`.
- Cover preparation, inventory, consolidation, backup, duplicate review,
  folder structure, naming, metadata, selection, privacy, sharing, and upkeep.
- Provide reusable worksheets, conventions, checklists, and a definition of
  done.
- Explain safe handling of originals and destructive operations.
- Keep the process platform-neutral and suitable for beginners.

## Non-goals

- Access, move, rename, edit, delete, upload, or publish any real photos.
- Recommend one mandatory vendor, paid product, operating system, or cloud
  provider.
- Store private photo metadata, account credentials, recovery codes, or
  sensitive personal details in this repository.
- Build an image-processing application, script, or automated classifier.
- Guarantee archival preservation without periodic verification and migration.

## Requirements / acceptance criteria

- [x] A standalone beginner guide exists under `3-Resources/Digital-Photos/`.
- [x] The guide defines a safe workflow from inventory through maintenance.
- [x] It requires verified backups before moving, renaming, deduplicating, or
      deleting originals.
- [x] It includes a reusable folder structure and deterministic file-naming
      convention with collision and unknown-date handling.
- [x] It distinguishes exact duplicates, near-duplicates, and similar images,
      and requires human review before deletion.
- [x] It covers dates, locations, people, events, captions, ratings, keywords,
      privacy, and metadata portability.
- [x] It addresses screenshots, scans, edited exports, RAW files, videos,
      shared albums, and photos received from others.
- [x] It includes collection inventory and progress-tracking templates.
- [x] It defines backup verification, recovery testing, and recurring intake,
      monthly, and annual maintenance routines.
- [x] It includes a clear definition of done and safe rollback guidance.
- [x] Markdown whitespace validation completes without errors.
- [x] The guide and completed task record are committed, published, and
      proposed for review in a pull request.

## Relevant files / links

- [`../../README.md`](../../README.md) - Defines the repository's PARA model
  and identifies digital photo organization as an example AIC task.
- [`README.md`](README.md) - Defines the AIC task workflow.
- [`AIC-TEMPLATE.md`](AIC-TEMPLATE.md) - Required task-record structure.
- [`../../3-Resources/README.md`](../../3-Resources/README.md) - Defines the
  location for reusable reference material.
- `../../3-Resources/Digital-Photos/organizing-digital-photos.md` - Planned
  durable guide delivered by this task.

## Constraints and decisions

- Store the output in `3-Resources/Digital-Photos/` because it is reusable
  reference material, not an ongoing responsibility or software component.
- Keep instructions platform-neutral while naming generic tool capabilities
  a user should look for.
- Prefer reversible operations: copy before move, quarantine before delete,
  preserve originals, and verify results at each stage.
- Treat filenames and folders as the portable baseline; optional catalog
  metadata must not be the only copy of essential information.
- Do not include real names, locations, credentials, or photo-library data.
- Use repository-native Markdown and validate with `git diff --check`.

## Dependencies

None.

## Status / progress

- 2026-09-27 - Task created, repository conventions reviewed, and status set
  to `in-progress`.
- 2026-09-27 - Determined that the repository-native implementation is a
  reusable resource guide rather than application code.
- 2026-09-27 - Created the digital photo organization guide with a reversible
  inventory, staging, backup, filing, naming, deduplication, metadata,
  curation, validation, and maintenance workflow.
- 2026-09-27 - Added reusable source-inventory and progress-log tables,
  portable folder and filename examples, special-source handling, rollback
  steps, and a definition of done.
- 2026-09-27 - Verified all acceptance criteria against the finished guide;
  required-section checks and `git diff --check` passed.
- 2026-09-27 - Completed the handoff and set the task status to `done`.

## Open questions

No open questions. Platform and storage choices are intentionally left
provider-neutral.

## Handoff / results

- **Outcome:** Delivered a standalone, beginner-friendly system for organizing
  digital photos safely without requiring a particular platform or provider.
- **Changes:** Added
  `3-Resources/Digital-Photos/organizing-digital-photos.md` and this completed
  AIC task record.
- **Validation:** Traced all 12 acceptance criteria to explicit guide content,
  confirmed all required workflow sections programmatically, and ran
  `git diff --check` successfully.
- **Remaining work:** Review and merge the pull request.
