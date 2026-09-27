# AIC-review-local-links

## Task metadata

- **Status:** done
- **Owner:** Unassigned
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Review every tracked Markdown file in the repository for broken repository-local
links and document a complete, reproducible set of results.

## Background / context

This repository is a PARA second brain whose navigation depends on Markdown
links between notes and folders. Broken local links make information difficult
to discover and can leave task or setup guidance disconnected. The review must
stand on its own and must not rely on the conversation that created this task.

At task creation, the repository contains Markdown files in the root,
`.github/`, and each numbered PARA folder. Re-enumerate tracked Markdown files
from Git when executing the task so newly added or moved files are included.

## Scope

- Enumerate every tracked `*.md` file in the repository.
- Inspect Markdown inline links, reference-style links, autolinks when they
  resolve locally, and linked local images or other repository files.
- Resolve relative paths from the directory containing the source Markdown
  file and repository-root-relative paths from the repository root.
- Validate directory destinations, URL-encoded local paths, and local heading
  fragments using GitHub Markdown heading behavior closely enough to identify
  actionable failures.
- Document the review method, files reviewed, and every broken local link with
  source file, line number, literal destination, and reason it is broken.
- Explicitly document that no broken local links were found if the review is
  clean.

## Non-goals

- Checking the availability or content of external HTTP(S), email, or other
  non-local destinations.
- Rewriting prose, reorganizing PARA content, or changing valid links.
- Fixing broken links; this task is limited to review and documentation.
- Validating links in untracked, generated, ignored, or non-Markdown files as
  source documents.

## Requirements / acceptance criteria

- [x] Every Markdown file reported by `git ls-files "*.md"` is included in the
  review, and the final documentation records the file count and reviewed
  paths.
- [x] Every repository-local Markdown link and image destination in those files
  is checked for an existing file or directory; any fragment is checked against
  the destination document.
- [x] Each broken link is documented with its source path, line number, literal
  destination, and a concise failure reason, with duplicate occurrences
  retained when they occur at different locations.
- [x] The final documentation distinguishes broken links from links that could
  not be conclusively validated, and records any limitations or ambiguities.
- [x] The review method is reproducible and includes the commands or script
  used; any temporary audit tooling is removed before completion unless it is
  intentionally retained and documented.
- [x] **Status / progress** and **Handoff / results** contain dated evidence of
  the completed review, and the task status is set to `done`.
- [x] The final repository diff is limited to this task document and any
  clearly justified durable results artifact.

## Relevant files / links

- `README.md` - repository organization and primary navigation.
- `.github/copilot-instructions.md` - repository-specific operating guidance.
- `1-Projects/` - active project notes, including this task.
- `2-Areas/` - ongoing-area notes.
- `3-Resources/` - reference notes and setup guidance.
- `4-Archives/` - archived content.
- `1-Projects/AIC-Tasks/README.md` - AIC task workflow.
- `1-Projects/AIC-Tasks/AIC-TEMPLATE.md` - required task structure.

## Constraints and decisions

- Follow the organization and naming guidance in the root `README.md`.
- Treat Markdown files as link sources only when they are tracked by Git.
- Treat links with no URI scheme, `file:` links, root-relative paths, and
  fragment-only destinations as local; ignore external schemes such as
  `http:`, `https:`, and `mailto:`.
- Ignore query strings when checking a local filesystem destination, but retain
  them in documented literal destinations.
- Do not silently classify parser limitations as valid links. Record ambiguous
  or unsupported syntax separately.
- Prefer an existing repository tool if one is already suitable. Do not add a
  dependency solely for this one-time review unless necessary.
- Record results directly in **Handoff / results**. Create a separate durable
  Markdown report only if the findings are too extensive to remain readable
  there.

## Dependencies

- None.

## Status / progress

- 2026-09-27 - Task created and marked ready for independent execution.
- 2026-09-27 - Enumerated all 10 tracked Markdown files with
  `git ls-files "*.md"` and reviewed every file as a link source.
- 2026-09-27 - Checked all 9 repository-local link occurrences with a
  dependency-free PowerShell audit, including relative file and directory
  resolution, URL decoding, repository-boundary checks, and GitHub-style
  heading-fragment validation.
- 2026-09-27 - Completed a separate syntax scan for inline links, reference
  definitions and uses, autolinks, and HTML `href`/`src` attributes. No broken
  or inconclusive repository-local links were found.

## Open questions

- No open questions.

## Handoff / results

- **Outcome:** Reviewed all 10 tracked Markdown files and all 9
  repository-local link occurrences. No broken links and no inconclusive links
  were found.
- **Changes:** Updated this task document only; no repository content links
  required changes and no durable audit artifact was necessary.
- **Validation:** The reviewed paths were:
  - `.github/copilot-instructions.md`
  - `1-Projects/AIC-Tasks/AIC-TEMPLATE.md`
  - `1-Projects/AIC-Tasks/AIC-review-local-links.md`
  - `1-Projects/AIC-Tasks/README.md`
  - `1-Projects/README.md`
  - `2-Areas/README.md`
  - `3-Resources/README.md`
  - `3-Resources/aic-lite-beginner-guide.md`
  - `4-Archives/README.md`
  - `README.md`

  The valid local destinations checked were:

  | Source | Line | Literal destination |
  | --- | ---: | --- |
  | `1-Projects/AIC-Tasks/README.md` | 8 | `AIC-TEMPLATE.md` |
  | `1-Projects/README.md` | 6 | `AIC-Tasks/` |
  | `README.md` | 10 | `1-Projects/` |
  | `README.md` | 11 | `2-Areas/` |
  | `README.md` | 12 | `3-Resources/` |
  | `README.md` | 13 | `4-Archives/` |
  | `README.md` | 21 | `1-Projects/AIC-Tasks/` |
  | `README.md` | 30 | `1-Projects/AIC-Tasks/` |
  | `README.md` | 36 | `3-Resources/aic-lite-beginner-guide.md` |

  Reproduction method:

  1. Run `git ls-files "*.md"` to establish the complete source set.
  2. Scan those files outside fenced and inline code for inline links and
     images, reference definitions and uses, `file:` autolinks, and HTML
     `href`/`src` attributes.
  3. Ignore destinations with non-local schemes. For local destinations, strip
     query strings, URL-decode paths and fragments, resolve relative paths from
     the source file and leading-slash paths from the repository root, reject
     paths outside the repository, and check the resulting path with
     `Test-Path -LiteralPath`.
  4. For a Markdown destination with a fragment, derive GitHub-style heading
     slugs, including numeric suffixes for duplicates, and require a matching
     slug.
  5. Retain source path, one-based line number, and literal destination for
     every occurrence. The temporary PowerShell audit script used for these
     steps was removed after the results were recorded.

  A separate extraction check used:

  ```powershell
  rg -n '!?\\[[^\\]]*\\]\\([^\\)]*\\)' -g '*.md'
  rg -n '^\\s*\\[[^\\]]+\\]:\\s*\\S+' -g '*.md'
  rg -n '<(?:[^ >]+@[^ >]+|(?:https?|file):[^ >]+)>' -g '*.md'
  rg -n '(?:href|src)\\s*=\\s*["''][^"'']+["'']' -g '*.md'
  ```

  **Broken links:** None.

  **Inconclusive links:** None.

  **Limitations / ambiguities:** External destinations were intentionally not
  tested. The repository contains no local reference-style links, local
  autolinks, linked images, HTML link attributes, URL-encoded local paths, or
  local heading fragments, so those syntax classes had no occurrences to
  validate against the filesystem. Markdown examples inside fenced or inline
  code were treated as code rather than navigational links.
- **Remaining work:** None.
