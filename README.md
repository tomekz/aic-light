# AIC-Lite Second Brain

This repository is a private second brain designed for the AIC task system. It
keeps your useful context, active work, and completed results in one durable
place while the GitHub Copilot App runs separate AI agent sessions for you.

The idea is simple:

1. **Write knowledge down.** Notes in the repository survive after a chat
   ends.
2. **Define work before starting it.** Each substantial job gets a
   self-contained `AIC-*.md` task brief with scope and completion checks.
3. **Give each task its own session.** The App creates an isolated working tree
   and branch, so several agents can work safely in parallel.
4. **Let ready tasks run.** A bounded task normally runs in Autopilot with
   Allow all until its acceptance criteria are verified.
5. **Review before keeping changes.** The agent creates a pull request (PR);
   you inspect it, then merge accepted work into the main repository.
6. **Keep a durable trail.** The task file records progress, decisions,
   blockers, and results so work can be resumed without relying on chat memory.

The folders use the [PARA method](https://fortelabs.com/blog/para/):

| Folder | Purpose |
| --- | --- |
| [`1-Projects/`](1-Projects/) | Active work with a defined outcome and end point |
| [`2-Areas/`](2-Areas/) | Ongoing responsibilities and standards to maintain |
| [`3-Resources/`](3-Resources/) | Reusable reference material and topics of interest |
| [`4-Archives/`](4-Archives/) | Inactive or completed material worth keeping |

The active AIC task system lives in
[`1-Projects/AIC-Tasks/`](1-Projects/AIC-Tasks/). This page explains how a new
Windows user can reproduce the complete setup with a personal GitHub account.

---

## Beginner setup and operating guide

This guide shows you how to build and use a private "second brain" with the
GitHub Copilot App. The App is a desktop program where you can give tasks to AI
agents, watch their progress, review their changes, and keep several tasks
moving at once.

You do not need to know terminal commands. You do not need Copilot CLI,
Node.js, or GitHub CLI. The App handles the technical Git work for you.

Setup takes about one hour. Afterward, your system has three parts:

1. **Durable instructions** tell Copilot how to work in your repository.
2. **A private second brain** stores notes and task history between sessions.
3. **One session per task** lets agents work in parallel without mixing their
   changes.

> [!NOTE]
> GitHub currently requires Git to be installed before you use the Copilot App.
> You do not have to learn Git commands. Install it once when the App's setup
> guide asks you to, then continue in the graphical interface.

---

## Part 1 - Learn the five words you need

| Word | Plain-language meaning |
| --- | --- |
| **Repository** | A folder whose files and history are stored on GitHub. This guide uses one private repository as your second brain. |
| **Project** | A repository or folder that you connect to the Copilot App. |
| **Session** | One conversation with an agent, plus a separate workspace for that task. |
| **Branch** | A safe, separate version of the repository where one session makes changes. |
| **Pull request (PR)** | A review page that shows proposed changes before you add them to the main version. |

You do not have to create branches or separate working folders yourself. When
you start sessions in separate working trees, the App gives each session its
own branch and isolated workspace.

---

## Part 2 - Create and secure your accounts

### 2.1 Create a GitHub account

1. Go to [github.com/signup](https://github.com/signup).
2. Create an account and verify your email address.
3. Open your profile menu on GitHub, then select **Settings**.
4. Select **Password and authentication**.
5. Under **Two-factor authentication**, select
   **Enable two-factor authentication**.
6. Use an authenticator app when possible.
7. Save the recovery codes in a password manager or another secure place.

Two-factor authentication, usually called **2FA**, protects your account even
if somebody learns your password.

### 2.2 Choose a Copilot plan

The Copilot App is available with every Copilot plan. Start with the plan that
matches your expected use:

- **Copilot Free** is suitable for trying the workflow with limited usage.
- **Copilot Pro** gives an individual a larger allowance and a choice of
  models.
- **Copilot Pro+** or **Copilot Max** may suit frequent or complex work.
- An employer may provide **Copilot Business** or **Copilot Enterprise**.

Plans, prices, models, and usage allowances can change. Check
[GitHub's current Copilot plans](https://docs.github.com/en/copilot/get-started/plans)
instead of choosing only from this summary.

---

## Part 3 - Install the GitHub Copilot App on Windows

These steps are for a personal Windows computer. The App also supports macOS
and Linux, but their installers look different.

1. If Git is not already installed, open
   [git-scm.com/download/win](https://git-scm.com/download/win).
2. Download **Git for Windows**, open the downloaded installer, and keep its
   default choices. You will not need to type Git commands.
3. Open the
   [GitHub Copilot App download page](https://github.com/features/ai/github-app).
4. Download the Windows version, open the installer, and complete its prompts.
5. Open the App and select **Sign in to GitHub**.
6. Complete the sign-in steps in the browser window that opens.
7. Choose a theme and finish the short onboarding process.

If you use Copilot through an employer, an administrator may need to allow the
Copilot App. This setting is separate from permission to use Copilot CLI.

### Find your way around

The App's sidebar contains the main places you will use:

- **Projects** lists connected repositories and their sessions.
- **Chats** is for questions and brainstorming that do not need file changes.
- **My work** collects GitHub issues and pull requests.
- **Search** searches your connected repositories.
- **Automations** contains saved recurring tasks. Ignore this until the basic
  workflow feels comfortable.

Labels can move as the App evolves. If your screen differs slightly, use the
same concepts rather than looking for an exact pixel or position.

---

## Part 4 - Create your private second brain

Your second brain is a private repository of Markdown files. Markdown is plain
text with simple headings and lists, like the guide you are reading.

The repository gives your notes a durable home. A new session does not
automatically remember every previous conversation, so important context must
be written into the repository.

### 4.1 Create the repository on GitHub

1. On [GitHub](https://github.com), select the **+** menu in the upper-right
   corner.
2. Select **New repository**.
3. Name it `second-brain`.
4. Add a short description such as `My private notes and AI task history`.
5. Choose **Private**.
6. Select **Add a README file**.
7. Select **Create repository**.

> [!WARNING]
> Keep this repository **private**. Never store passwords, recovery codes,
> access tokens, API keys, private encryption keys, or payment-card details in
> it. Use a password manager for secrets.

### 4.2 Connect it to the Copilot App

1. Return to the Copilot App.
2. Next to **Projects** in the sidebar, select **+**.
3. Under **Add project from**, choose **GitHub repository**.
4. Find and select your new `second-brain` repository.
5. Wait while the App prepares the project.

The App downloads the repository and manages its connection to GitHub. You do
not need to clone it or configure Git yourself.

### 4.3 Ask Copilot to create the structure

1. Select **+** next to your `second-brain` project.
2. Choose a **new working tree** as the session location.
3. Choose **Plan** mode. In this mode, the agent proposes a plan and waits for
   your approval before changing files.
4. Paste the following request:

> Set up this repository as a simple PARA second brain for a non-technical
> user. Create `1-Projects`, `2-Areas`, `3-Resources`, and `4-Archives`.
> Create `1-Projects/AIC-Tasks`, including a README that explains one
> self-contained `AIC-<short-task-name>.md` file per task and an
> `AIC-TEMPLATE.md` with metadata, objective, context, scope, non-goals,
> acceptance criteria, relevant links, constraints, dependencies, progress,
> open questions, and handoff/results. Update the root README with a short map
> of the folders. Add `.github/copilot-instructions.md` telling Copilot to
> follow this structure, keep task progress current, protect secrets, ask
> before destructive or costly actions, and use one session per active task.
> For a ready AIC task, launch its dedicated session in Autopilot with Allow
> all, work through every acceptance criterion without routine check-ins, and
> stop only for a real blocker or an action that requires my approval. Keep the
> wording short and beginner-friendly. Show me the plan before making changes.

5. Read the plan. If it matches the request, approve it.
6. Let the agent finish, then select **Changes** above the prompt box.
7. Read the changed files. Ask questions in the same session if anything is
   unclear.
8. When the result looks right, select **Create PR**.
9. Open the **PR** view, review the summary and changed files, and merge it when
   you are satisfied.

A pull request makes the setup visible for review before it becomes the main
version. After the merge, future sessions start from the updated structure.

---

## Part 5 - Make durable instructions useful

The file `.github/copilot-instructions.md` contains repository-wide
instructions. Copilot automatically adds these instructions when it works in
the repository.

Open the file in the App or on GitHub and check that it covers these rules:

- Explain unfamiliar terms in plain language.
- Follow the folder map in `README.md`.
- Keep one self-contained `AIC-*.md` document for each task.
- Update a task's status, dated progress, decisions, blockers, and results.
- Use a separate session for each active task.
- Run a ready AIC task in Autopilot with **Allow all** and continue until every
  acceptance criterion is complete, asking only about real blockers or
  protected actions.
- Never store secrets in files or commits.
- Ask before deleting important files, spending money, publishing private
  information, or taking another hard-to-reverse action.
- Review current files before editing and verify the result before declaring a
  task done.
- Create a pull request so the user can review completed changes.

These instructions are part of the repository, so they travel with it. They
are more reliable than hoping a new session remembers an old conversation.

If you want to change a rule, ask a session to edit the instructions and
explain the proposed change. Review the diff before merging it.

---

## Part 6 - Create a well-defined task

Do not begin a substantial job with only a vague one-line request. First create
a **task brief**: a file that gives a new session all the context it needs.

### 6.1 Start in a chat

Use **Chats** when you need help shaping an idea but do not yet want file
changes. For example:

> Help me define a small task to organize my household warranty information.
> Ask what is missing and suggest clear completion checks. Do not change files
> yet.

Chats do not create a task branch or workspace. When the idea is clear, start a
project session to record it.

### 6.2 Create the task brief

1. Select **+** next to the `second-brain` project.
2. Choose a **new working tree**.
3. Choose **Plan** or **Interactive** mode.
4. Give the session a request like this:

> Start a new AIC task to organize my household warranty information. The
> result should be an index of products, purchase dates, warranty end dates,
> receipt locations, and support links. Do not copy passwords, card numbers,
> or full account details into the repository. Create the task brief only,
> make it self-contained, and let me review it before starting the work.

The agent should create a file such as:

`1-Projects/AIC-Tasks/AIC-organize-warranties.md`

Before allowing the work to start, check that the brief says:

- what outcome you want;
- what is included and excluded;
- how you will know it is complete;
- which files, links, or source material matter;
- what the agent must not expose or change;
- which questions or dependencies could block progress.

Use `Unknown` or an open question instead of letting the agent invent missing
facts.

### 6.3 Start the dedicated work session

After the task brief is saved, use one dedicated session to execute it. You can
ask the setup session to start that session, or start one yourself with **+**
next to the project.

Use this request, replacing the file name:

> Execute the task in
> `1-Projects/AIC-Tasks/AIC-organize-warranties.md`. Treat that document as the
> source of truth. Work autonomously, keep its status and dated progress
> current, record decisions and blockers, complete its handoff/results section,
> verify every acceptance criterion, and create a pull request.

Start with **Plan** mode for unfamiliar, broad, or risky work. Use
**Interactive** when you expect to make decisions together. Use **Autopilot**
only when the task is clear, bounded, and safe enough for the agent to proceed
without waiting at each step.

### 6.4 Default AIC mode: finish with minimal interaction

Once you have reviewed a ready task brief, the normal AIC workflow is designed
to need as little attention as possible:

1. Start one dedicated session in a **new working tree**.
2. Select **Autopilot** so the agent can keep working through multiple steps.
3. Select **Allow all** for that session when the App asks how agent tool
   approvals should work.
4. Prefer a cloud sandbox, or enable local sandboxing, when the task does not
   need unrestricted access to your computer.
5. Tell the agent to continue until every acceptance criterion is verified,
   the task document is complete, and a pull request is created.

**Allow all** removes routine approval prompts; it does not remove your safety
rules. The agent must still stop for missing information that it cannot infer,
secrets, purchases, publishing private information, destructive changes
outside the task, or another action that the task brief reserves for you.

Use this standard request:

> Run this ready AIC task in Autopilot with minimal operator interaction.
> Continue until all acceptance criteria are verified and the pull request is
> ready. Make reasonable low-risk decisions yourself and record them in the
> task document. Contact me only for a genuine blocker or an explicitly
> protected action.

Use **Plan** or **Interactive** instead when the task is still vague, has a wide
or uncertain impact, handles sensitive material, or could cause an expensive
or hard-to-reverse result.

---

## Part 7 - Run tasks in parallel safely

Each App session can use an isolated working tree and its own branch. This lets
several agents work at the same time without writing over one another.

Start with two parallel sessions until the pattern feels familiar.

Follow these rules:

| Rule | Why it matters |
| --- | --- |
| One task brief has one active session | Two agents updating the same task file can contradict each other. |
| Use a new working tree for each task | The App isolates each task's files and branch. |
| Keep each task focused | Smaller changes are easier to review and merge safely. |
| Record progress in the task document | Another session can resume from the repository, not from memory. |
| Merge completed PRs before starting dependent work | A new session otherwise starts without those changes. |
| Review two tasks that edit the same file carefully | Separate workspaces prevent overwrites while working, but the changes can still conflict when merged. |

Your control panel is split between two App views:

- Under **Projects**, select a session to read its conversation and see whether
  it is active or waiting for you.
- In **My work**, review pull requests, checks, review comments, and completed
  work.

Do not use one session for several unrelated tasks. Start a new session when
you change goals so its context stays focused.

---

## Part 8 - Review, steer, pause, and resume

### While an agent works

1. Select its session under **Projects**.
2. Read recent messages and respond to requests for a decision.
3. If the task is drifting, give a direct correction in the same session.
4. Select **Changes** to inspect additions, removals, and edits.
5. Ask the agent to explain any change you do not understand.

Red usually means removed text; green usually means added text. A large diff
is not automatically bad, but it deserves more careful review.

### Pause and resume

You can switch to another session or close the App without turning the task
into a new conversation. To continue later, reopen the App and select the
existing session under its project.

If you intentionally start a replacement session, point it to the task brief:

> Continue the task in
> `1-Projects/AIC-Tasks/AIC-organize-warranties.md`. Read its progress,
> decisions, blockers, and acceptance criteria before doing anything.

The written progress log is the fallback when conversation context is missing.

Use the App's session management settings to archive finished sessions. Delete
a session only when you are sure you no longer need its working files or chat
history.

### Finish safely

Before merging a pull request:

1. Confirm the task brief's acceptance criteria are checked truthfully.
2. Read the handoff/results section.
3. Open **Changes** or the PR's **Files changed** view.
4. Look for unexpected deletions, private information, or unrelated edits.
5. Check any validation results shown in the PR.
6. Ask for corrections in the session if needed.
7. Merge only when you understand and accept the result.

After merging, the repository's main version contains the durable result. A
PR that is only created but not merged is still proposed work.

---

## Part 9 - A simple routine

### At the start of a work period

1. Open the Copilot App.
2. Look under **Projects** for sessions waiting on you.
3. Open **My work** and check active pull requests.
4. Resume an existing task before creating a duplicate session.
5. Create a task brief before starting new substantial work.

### At the end of a work period

1. Check each active task's status and latest dated progress.
2. Answer or record blockers.
3. Review completed changes and PRs.
4. Merge accepted work so new sessions can see it.
5. Leave unfinished work in its existing session with a clear next step.

### Once a week

Ask a session in the second-brain project:

> Review the repository for stale active tasks, missing progress updates,
> unresolved blockers, and completed tasks that are ready to archive. Propose
> a short cleanup plan. Do not delete anything without my approval.

Move inactive, completed material to `4-Archives` rather than deleting useful
history.

---

## Part 10 - Safety checklist

- [ ] GitHub 2FA is enabled and recovery codes are stored securely.
- [ ] The second-brain repository is **private**.
- [ ] Passwords, tokens, keys, recovery codes, and payment details stay in a
      password manager, not the repository.
- [ ] Risky work starts in **Plan** or **Interactive** mode.
- [ ] Local or cloud sandboxing is used when appropriate and available.
- [ ] Each active task has one task brief and one dedicated session.
- [ ] Ready, bounded AIC tasks use **Autopilot** and **Allow all** for minimal
      routine interaction.
- [ ] Important decisions and progress are written to files, not left only in
      chat history.
- [ ] Every PR is reviewed for unexpected or destructive changes.
- [ ] Completed PRs are merged before dependent tasks begin.
- [ ] Deletion, publication, purchases, and other hard-to-reverse actions
      require explicit approval.

---

## Official references

These GitHub pages describe the current interface and were used to check this
guide:

- [Getting started with the GitHub Copilot App](https://docs.github.com/en/copilot/get-started/quickstart-copilot-app)
- [About the GitHub Copilot App](https://docs.github.com/en/copilot/concepts/agents/github-copilot-app)
- [Working with agent sessions in the GitHub Copilot App](https://docs.github.com/en/copilot/how-tos/github-copilot-app/agent-sessions)
- [Managing issues and pull requests in the App](https://docs.github.com/en/copilot/how-tos/github-copilot-app/managing-issues-and-pull-requests)
- [Adding repository custom instructions](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions)
- [Creating a repository on GitHub](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
- [Configuring two-factor authentication](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)

The App changes over time. Prefer these official pages when a button name or
feature differs from what you see.
