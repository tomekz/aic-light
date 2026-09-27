# AIC tasks

This folder contains personal task briefs designed to serve as complete context
for independent, parallel Copilot chats.

The project skill at [`.github/skills/aic-task/SKILL.md`](../../.github/skills/aic-task/SKILL.md)
automatically applies this workflow when the user asks to start or run AIC
tasks. The user only describes the work; the skill handles task records,
dedicated sessions, progress, commits, and pull requests.

## Create a task

1. Copy [`AIC-TEMPLATE.md`](AIC-TEMPLATE.md) in this folder.
2. Rename the copy to `AIC-<short-task-name>.md`, using a concise lowercase
   kebab-case name, such as `AIC-organize-tax-records.md`.
3. Fill in every section. Write `None`, `N/A`, or `No open questions` rather
   than leaving ambiguity. Link relevant repository files with relative paths.
4. Keep the task focused enough for one chat to own from start to handoff.

`AIC-TEMPLATE.md` is the only file in this folder exempt from the task naming
convention.

## Start parallel chats

For each ready `AIC-*.md` task document:

1. Start a separate Copilot chat in the workspace where the task should run.
2. Give that chat the full task document as its primary context, for example:

   ```text
   Execute the task described in
   1-Projects/AIC-Tasks/AIC-<short-task-name>.md. Treat the document as the
   source of truth, update its progress and handoff sections, and verify the
   acceptance criteria before finishing.
   ```

3. Use only one active chat per task document to avoid conflicting updates.
4. Record decisions and progress in the task document so another chat can
   resume without relying on conversation history.
5. When finished, set the status to `done`, complete **Handoff / results**, and
   move the document to `4-Archives/Projects/AIC-Tasks/` when it is no longer
   active.

Tasks may run in parallel when their **Dependencies** sections do not conflict.

## Required completion contract

An AIC task is not finished when its output file is merely created. Its agent
must also:

1. Keep the task document on the same branch as the output.
2. Mark verified acceptance criteria and complete the dated progress and
   handoff sections.
3. Commit all scoped changes.
4. Publish the branch and create a pull request.
5. Report the task path, validation result, and pull request.

If one prompt requests several independent AIC tasks, create one task document,
commit, and dedicated session for each. The coordinating session must verify
this completion contract for every child session instead of accepting a
success message at face value.
