# AIC-rewrite-beginner-guide-for-copilot-app

## Task metadata

- **Status:** done
- **Owner:** Unassigned
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Review and rewrite the AIC-Lite beginner guide so it teaches a non-technical
beginner to use the GitHub Copilot App's graphical interface rather than
Copilot CLI or terminal-driven workflows.

## Background / context

The current guide assumes that the reader installs and operates Copilot CLI,
uses terminal tabs as agents, and runs Git, GitHub CLI, Node.js, and shell
commands directly. The intended reader instead uses the GitHub Copilot App
window and may not know how to use a terminal. The guide should provide a
coherent GUI-first path from initial setup through creating and maintaining a
second-brain repository, starting parallel tasks, reviewing agent activity,
resuming work, and preserving results.

This is a substantive review and rewrite. Do not mechanically rename CLI
concepts: verify that every instruction and workflow accurately matches the
current GitHub Copilot App UI and remove terminal-only concepts that are not
needed.

## Scope

- Review the entire beginner guide for Copilot CLI, terminal, shell-command,
  manual Git, and other technical assumptions.
- Rewrite installation, setup, second-brain creation, instructions, daily
  workflow, parallel task management, pausing/resuming, and safety guidance for
  the GitHub Copilot App GUI.
- Prefer actions performed through the Copilot App and GitHub website.
- Explain necessary concepts and UI actions in plain language suitable for a
  reader with no terminal experience.
- Replace or remove CLI command tables, terminal-tab instructions, command-line
  code blocks, and advice that is irrelevant to the GUI workflow.
- Preserve the useful intent of the guide: durable instructions, a private
  second brain, self-contained tasks, safe parallel work, progress tracking,
  and beginner-friendly guardrails.
- Review repository references to the beginner guide and update directly
  related wording if it incorrectly describes the revised workflow.
- Verify UI-specific claims against current official GitHub or GitHub Copilot
  App documentation when possible.

## Non-goals

- Teaching Copilot CLI, GitHub CLI, shell commands, terminal usage, or manual
  Git as part of the primary workflow.
- Documenting the full automated AIC system or advanced command-line workflows.
- Changing the repository's AIC task orchestration conventions.
- Reorganizing unrelated PARA content.
- Building or changing application code.

## Requirements / acceptance criteria

- [x] `README.md` consistently presents the GitHub
      Copilot App window as the primary interface.
- [x] A beginner can follow the guide without installing Copilot CLI, Node.js,
      GitHub CLI, or learning terminal commands.
- [x] Every remaining terminal or command-line step is removed, replaced with
      a GUI alternative, or explicitly identified as optional and unnecessary
      for the main workflow.
- [x] The end-to-end workflow is internally consistent: account and plan,
      app/project setup, private second brain, durable instructions, task
      creation, parallel sessions, progress review, pause/resume, and safe
      completion all use compatible GUI concepts.
- [x] References to terminal tabs, CLI slash/bang commands, direct shell paths,
      manual `git` commands, and CLI-only configuration locations are removed
      unless retained in a clearly labeled optional advanced note.
- [x] The revised guide uses short steps, plain language, and explains any
      unavoidable GitHub, repository, project, session, branch, worktree, or
      pull-request terminology before relying on it.
- [x] Security guidance remains prominent: use 2FA, keep the second brain
      private, never store secrets, and review risky or destructive actions.
- [x] Claims about the GitHub Copilot App UI and capabilities are checked
      against current official documentation; uncertain UI details are not
      invented.
- [x] Directly related repository references are checked and updated where
      needed.
- [x] Perform a final editorial review for broken links, stale CLI assumptions,
      contradictions, spelling, readability, and complete Markdown structure.

## Relevant files / links

- `README.md` - primary guide, consolidated at the repository entry point.
- `README.md` - links to and summarizes the beginner guide.
- `1-Projects/AIC-Tasks/README.md` - repository's current parallel AIC task
  workflow and terminology.
- `.github/copilot-instructions.md` - inspect only if useful for accurately
  explaining repository-level instructions.
- https://springtime-technologies.ghe.com/tomasz-zadrozny/aic-light/blob/main/README.md
  - user-provided link to the current guide.
- Official GitHub and GitHub Copilot documentation - authoritative source for
  current GUI behavior and terminology.

## Constraints and decisions

- The target audience is a GUI user who does not know how to use a terminal.
- The guide must assume the GitHub Copilot App window, not Copilot CLI.
- Terminal steps are generally unnecessary and should not be prerequisites.
- Prefer GUI-native workflows over command-line equivalents, even when the
  command-line version is shorter.
- Keep the guide beginner-friendly and lightweight; advanced details should not
  obscure the main path.
- Do not invent app controls, menu names, capabilities, or availability. Use
  generic but actionable wording if official documentation does not establish
  an exact label.
- Preserve the existing file path unless a compelling repository convention
  requires otherwise.
- Keep the second-brain repository private and avoid examples that encourage
  storing credentials or other secrets.

## Dependencies

- Access to the current repository contents.
- Access to current official GitHub documentation for fact-checking.

## Status / progress

- 2026-09-27 - Task created and marked ready for a dedicated Copilot session.
- 2026-09-27 - Verified the current Copilot App project, session, mode,
  Changes/PR, My work, and isolated-worktree workflows against official GitHub
  documentation.
- 2026-09-27 - Rewrote the guide around a GUI-only primary workflow and aligned
  parallel task tracking with the repository's `AIC-*.md` convention.
- 2026-09-27 - Completed editorial, stale-CLI, Markdown-structure, repository
  reference, and external-link checks; all acceptance criteria passed.
- 2026-09-27 - Added the requested low-interaction AIC default: dedicated
  sessions use Autopilot with Allow all and continue to verified completion,
  while retaining explicit safety stop conditions.
- 2026-09-27 - Consolidated the second-brain explanation and complete Windows
  setup guide into the root README, removing the duplicate resource page.
- 2026-09-27 - Simplified the README into a shorter single-page explanation
  and replication guide while preserving setup, workflow, and safety details.
- 2026-09-27 - Enabled the repository as a GitHub template and changed the
  setup path to create a ready private copy with **Use this template**.

## Open questions

- None. The guide links to current official documentation and tells readers to
  follow the documented concepts when minor labels or positions change.

## Handoff / results

Complete this section before closing the task:

- **Outcome:** Replaced the terminal-first beginner guide with a complete,
  GUI-first GitHub Copilot App workflow for non-technical users.
- **Changes:** Rewrote setup, private repository creation, durable
  instructions, AIC task briefs, parallel sessions, review, pause/resume,
  low-interaction Autopilot execution, completion, and safety guidance. Updated
  the repository instructions and consolidated the complete guide into the
  root README.
- **Validation:** Checked all acceptance criteria, searched for stale CLI and
  terminal instructions, verified Markdown structure and whitespace, reviewed
  the complete diff, and checked every external link. All documentation links
  returned HTTP 200; `github.com/signup` returned HTTP 403 to the automated
  link checker but remains the official browser signup URL.
- **Remaining work:** None.
