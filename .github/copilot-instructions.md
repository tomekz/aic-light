# Repository instructions

This repository is a PARA second brain. Follow the organization and naming
guidance in the root `README.md`.

## Starting an AIC task

When the user asks to "start a new AIC task", "create an AIC task", or uses
equivalent wording, treat it as a request to create and launch a self-contained
parallel task:

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
   brief. Do not perform the task in the orchestration chat unless session
   creation is unavailable or the user explicitly asks.
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

Use one active chat per `AIC-*.md` document. Different AIC task documents may
run in parallel when their dependencies and edited files do not conflict.

## Executing an AIC task

When a chat is assigned an existing `AIC-*.md` document:

- Treat the document as the source of truth and remain within its scope.
- Update **Status / progress** at meaningful checkpoints and whenever blocked.
- Record durable decisions and answers to open questions in the document.
- Before finishing, verify the acceptance criteria and complete
  **Handoff / results** with the outcome, changes, validation, and remaining
  work.
- Commit the task document updates together with the corresponding work and
  create a pull request unless the user explicitly requests another delivery
  method.
