# Repository instructions

This repository is a PARA second brain. Follow the organization and naming
guidance in the root `README.md`.

## Starting an AIC task

When the user asks to "start a new AIC task", "create an AIC task", or uses
equivalent wording, treat it as a request to create and launch a self-contained
parallel task. **AIC is a required lifecycle, not merely a label or a suggested
file location. Do not skip any lifecycle step even when the requested output
itself is simple.**

If one request contains multiple independent AIC tasks, split it into one
`AIC-*.md` document and one dedicated session per task. Create and commit each
brief separately. Do not execute any of those tasks in the orchestration chat.

For each task:

1. Read `1-Projects/AIC-Tasks/README.md` and
   `1-Projects/AIC-Tasks/AIC-TEMPLATE.md`.
2. Derive a concise lowercase kebab-case task name and create
   `1-Projects/AIC-Tasks/AIC-<short-task-name>.md`.
3. Preserve every template section. Fill it from the user's request and
   relevant repository context. Do not invent facts; mark missing information
   explicitly as `Unknown`, `None`, `N/A`, or an open question.
4. Make the document sufficient for a separate Copilot chat with no access to
   the originating conversation. Include a concrete objective, boundaries,
   verifiable acceptance criteria, relevant paths or links, constraints,
   decisions, dependencies, and known context.
5. Set the initial status to `ready` when work can begin or `blocked` when a
   required dependency is missing. Use the current date for created, updated,
   and progress entries.
6. Persist the task brief in Git before launching work so the new session can
   read it. Do not combine unrelated task briefs in the same commit.
7. Launch one dedicated Copilot project session for that AIC document when
   session creation is available. Base it on the commit containing the task
   brief. Run it in Autopilot with allow-all permissions by default so it can
   finish with minimal operator interaction. Do not perform the task in the
   orchestration chat unless session creation is unavailable or the user
   explicitly asks.
8. Give the dedicated session this instruction, substituting the actual path:

   ```text
   Execute the task in 1-Projects/AIC-Tasks/AIC-<short-task-name>.md.
   Treat that document as the source of truth. Work autonomously, keep its
   Status / progress section updated with dated checkpoints, record decisions
   and blockers, and complete Handoff / results before finishing. Verify every
   acceptance criterion, commit the changes, and create a pull request.
   ```

9. Tell the user the task document path and the dedicated session that was
   started. If a session could not be launched, state that plainly and leave
   the committed task document ready to run.
10. Monitor the dedicated session to completion. Before reporting the task as
    finished, verify that its task document is updated, its scoped changes are
    committed, and its pull request exists. If any item is missing, send the
    session a correction and keep the task open.

Use one active chat per `AIC-*.md` document. Different AIC task documents may
run in parallel when their dependencies and edited files do not conflict.

## Executing an AIC task

When a chat is assigned an existing `AIC-*.md` document:

- Before changing another file, open the assigned task document, set its
  status to `in-progress`, and add a dated progress entry.
- Treat the document as the source of truth and remain within its scope.
- Work autonomously through completion with allow-all permissions by default.
  Make reasonable low-risk decisions without routine check-ins. Stop only for
  a genuine blocker or an action involving secrets, spending, publication of
  private information, destructive changes outside scope, or another decision
  explicitly reserved for the user.
- Update **Status / progress** at meaningful checkpoints and whenever blocked.
- Record durable decisions and answers to open questions in the document.
- Before finishing, verify the acceptance criteria and complete
  **Handoff / results** with the outcome, changes, validation, and remaining
  work.
- Commit the task document updates together with the corresponding work and
  create a pull request unless the user explicitly requests another delivery
  method.

### Mandatory completion gate

Do not say that an AIC task is complete and do not stop after creating only the
requested output. Completion requires all of the following:

1. The assigned `AIC-*.md` file exists on the task branch.
2. Every acceptance criterion is checked and was actually verified.
3. Status is `done`, dated progress is current, and **Handoff / results** is
   complete.
4. All scoped output and task-record changes are committed.
5. The branch is published and a pull request has been created.
6. The user or orchestration session receives the task path, validation result,
   and pull-request reference.

If committing, publishing, or pull-request creation fails, diagnose and retry.
If it still cannot be completed, leave the task `blocked`, record the exact
blocker in the task document, and report that the task is not complete.
