---
name: aic-task
description: Create, launch, coordinate, execute, and finish one or more AIC tasks. Use whenever the user asks to start, create, run, continue, or complete an AIC task, including several parallel AIC tasks. The user only needs to describe the desired work; this skill owns the task records, sessions, progress tracking, commits, and pull requests.
---

# AIC task lifecycle

Treat "AIC task" as a request for the complete workflow below. The user does
not need to repeat these process instructions.

## Core rules

- One independent task equals one `AIC-*.md` document, one active agent
  session, one branch, and one pull request.
- Split a request containing multiple independent tasks before starting work.
- Run independent tasks in parallel.
- Use Autopilot and allow-all permissions by default for ready, bounded tasks.
- Make reasonable low-risk decisions without routine questions.
- Stop only for a genuine blocker or an action involving secrets, spending,
  publishing private information, destructive changes outside scope, or a
  decision explicitly reserved for the user.
- Never report success based only on creation of the requested output.

## Create each task record

1. Read `README.md`, `1-Projects/AIC-Tasks/README.md`,
   `1-Projects/AIC-Tasks/AIC-TEMPLATE.md`, and relevant repository context.
2. Create
   `1-Projects/AIC-Tasks/AIC-<concise-lowercase-kebab-case-name>.md`.
3. Preserve every template section.
4. Write a concrete objective, boundaries, verifiable acceptance criteria,
   relevant paths or links, constraints, dependencies, and all known context.
5. Do not invent facts. Use `Unknown`, `None`, `N/A`, or an open question.
6. Set status to `ready` when work can start or `blocked` when a required
   dependency is missing. Add the current date.

If the coordinating context can edit the repository, commit each unrelated
task brief separately before launching its worker. Base the worker on the
branch containing that commit.

If the coordinating context cannot edit repository files, launch one dedicated
project session per task with the full task description and require that
session to create its `AIC-*.md` record as its first change before producing
the requested output.

## Launch each task session

Launch a dedicated project session in a new working tree:

- mode: Autopilot;
- permissions: allow all, when the host exposes that setting;
- base: the commit or branch containing the task brief, when one already
  exists;
- notification: enabled so the coordinator can verify completion.

Give the session this instruction, substituting its actual task path and
including the full original requirements:

```text
Execute the AIC task in <task-path>. If the task record does not exist yet,
create it from 1-Projects/AIC-Tasks/AIC-TEMPLATE.md before changing any output
file. Treat it as the source of truth. Run autonomously through the mandatory
AIC completion gate. Do not stop after creating only the requested output.
```

## Execute the task

The dedicated task session must:

1. Open the task record before changing an output file.
2. Set status to `in-progress` and add a dated progress entry.
3. Work only within scope and update progress at meaningful checkpoints.
4. Record durable decisions and blockers in the task record.
5. Validate every acceptance criterion against the actual result.
6. Check completed criteria, set status to `done`, and complete
   **Handoff / results** with outcome, changes, validation, and remaining work.
7. Commit the task record and all scoped output together.
8. Publish the branch and create a pull request.
9. Report the task path, validation performed, and pull request.

If commit, publication, or pull-request creation fails, diagnose and retry. If
it remains impossible, set status to `blocked`, record the exact failure, and
report that the task is incomplete.

## Coordinate and verify

After launching workers, continue monitoring them. For every task, verify:

- the expected `AIC-*.md` file exists on its branch;
- status, dated progress, acceptance criteria, and handoff are complete;
- the requested output exists;
- the changes are committed;
- the branch is published;
- a pull request exists.

If a worker is idle but any item is missing, send it a correction and require
it to continue. Do not tell the user that the overall request is complete until
every task passes this verification.

Leave pull requests open for the user's review unless the user explicitly asks
you to merge them.
