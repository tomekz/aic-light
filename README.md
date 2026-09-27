# AIC-Lite: AI Agents with a Second Brain

This repository is two things in one:

1. A **beginner setup guide** for running AI agents in the GitHub Copilot App.
2. A **working second brain** that stores notes, task plans, progress, and
   results between agent sessions.

You can use this repository as a model to build the same system with your own
Windows computer and GitHub account. You do not need to know terminal commands
or install Copilot CLI, Node.js, or GitHub CLI.

> [!IMPORTANT]
> The second brain is not automatic chat memory. Agents remember important
> information by writing it into repository files and merging those changes
> into the `main` branch.

## How the system works

1. You describe a task.
2. Copilot creates a self-contained `AIC-*.md` task brief.
3. A dedicated agent session works on that task in its own safe copy and
   branch.
4. The agent records progress, decisions, blockers, and results in the task
   file.
5. The agent creates a pull request (PR) showing its proposed changes.
6. You review and merge the PR. The result is now part of the second brain.

Different tasks can run at the same time because each one has its own session
and branch.

## Repository map

This second brain uses the [PARA method](https://fortelabs.com/blog/para/):

| Folder | What belongs there |
| --- | --- |
| [`1-Projects/`](1-Projects/) | Active work with a clear finish |
| [`1-Projects/AIC-Tasks/`](1-Projects/AIC-Tasks/) | One self-contained file per AI task |
| [`2-Areas/`](2-Areas/) | Ongoing responsibilities |
| [`3-Resources/`](3-Resources/) | Reusable notes and reference material |
| [`4-Archives/`](4-Archives/) | Finished or inactive material worth keeping |
| [`.github/copilot-instructions.md`](.github/copilot-instructions.md) | Permanent rules that guide Copilot in this repository |

---

## Set up your own copy on Windows

### 1. Create and secure a GitHub account

1. Create an account at [github.com/signup](https://github.com/signup).
2. Verify your email address.
3. On GitHub, open your profile menu and select **Settings**.
4. Select **Password and authentication**.
5. Enable **two-factor authentication (2FA)**.
6. Use an authenticator app when possible and save the recovery codes in a
   password manager.

### 2. Choose a Copilot plan

The Copilot App is available with all Copilot plans. Copilot Free is enough to
try the workflow; paid plans provide more usage and model choices.

Check [GitHub's current Copilot plans](https://docs.github.com/en/copilot/get-started/plans)
for current features, prices, and limits.

### 3. Install the required applications

1. Open [Git for Windows](https://git-scm.com/download/win).
2. Download and run the installer. Keep its default choices. The Copilot App
   needs Git, but you will not need to type Git commands.
3. Open the
   [GitHub Copilot App download page](https://github.com/features/ai/github-app).
4. Download and install the Windows version.
5. Open the App and select **Sign in to GitHub**.
6. Finish sign-in in the browser window that opens.

### 4. Create a private second-brain repository

1. On [GitHub](https://github.com), select the **+** menu in the upper-right.
2. Select **New repository**.
3. Name it `second-brain`.
4. Choose **Private**.
5. Select **Add a README file**.
6. Select **Create repository**.

Keep the repository private. Never save passwords, API keys, access tokens,
recovery codes, payment-card details, or other secrets in it.

### 5. Connect the repository to the Copilot App

1. Return to the Copilot App.
2. Next to **Projects** in the sidebar, select **+**.
3. Choose **GitHub repository**.
4. Find and select your `second-brain` repository.
5. Wait while the App prepares the project.

The App downloads and manages the repository for you.

### 6. Ask Copilot to build the second brain

1. Select **+** next to the new project.
2. Choose a **new working tree**.
3. Choose **Plan** mode.
4. Paste this request:

> Set up this repository as an AIC-Lite second brain for a non-technical user.
> Create the PARA folders `1-Projects`, `2-Areas`, `3-Resources`, and
> `4-Archives`. Inside `1-Projects`, create `AIC-Tasks/README.md` and
> `AIC-Tasks/AIC-TEMPLATE.md`. The template must include metadata, objective,
> context, scope, non-goals, acceptance criteria, relevant links, constraints,
> dependencies, dated progress, open questions, and handoff/results. Create
> `.github/copilot-instructions.md` with the rules below. Update the root
> README with a short folder map. Show me the plan before changing files.
>
> Rules: use one dedicated session per AIC task; keep each task file current;
> launch ready tasks in Autopilot with Allow all; work until every acceptance
> criterion is verified; create a pull request for my review; ask only about
> real blockers or protected actions; never store secrets; ask before spending
> money, publishing private information, or making destructive changes outside
> the task.

5. Read the plan and approve it if it matches the request.
6. When Copilot finishes, select **Changes** and review the files.
7. Select **Create PR**.
8. Review the PR and merge it.

Your second brain is now ready.

---

## Use the AIC task workflow

### Start a task

In a chat or project session, say:

> Start a new AIC task to organize my household warranty information. Include
> product names, purchase dates, warranty end dates, receipt locations, and
> support links. Do not store passwords or payment details.

Copilot should:

1. Create a focused file such as
   `1-Projects/AIC-Tasks/AIC-organize-warranties.md`.
2. Fill every section without inventing missing facts.
3. Commit the task brief so another session can read it.
4. Launch one dedicated session for that task.

### Let a ready task run

The default for a clear, bounded AIC task is:

- **New working tree** so its files are isolated.
- **Autopilot** so the agent continues through multiple steps.
- **Allow all** so routine tool approvals do not interrupt the work.
- Minimal interaction until the acceptance criteria are verified and the PR is
  ready.

Allow all does not cancel the safety rules. The agent must stop for a real
blocker, missing sensitive information, spending, publication of private
information, destructive out-of-scope work, or another decision reserved for
you.

Use **Plan** or **Interactive** instead when the task is vague, sensitive,
expensive, broad, or hard to reverse.

### Run tasks in parallel

- Use one active session per `AIC-*.md` task.
- Never give the same task file to two active sessions.
- Start each task in a new working tree.
- Let independent tasks run at the same time.
- Merge prerequisite work before starting a task that depends on it.
- Review tasks that edit the same file carefully; their PRs may conflict.

### Check progress

- Under **Projects**, select a session to read its messages and see whether it
  is active or waiting for you.
- In **My work**, review pull requests, checks, and review comments.
- In the task file, read **Status / progress**, **Open questions**, and
  **Handoff / results**.

### Pause or resume

Switching sessions or closing the App does not require a new task. Reopen the
App and select the existing session.

If you must use a replacement session, say:

> Continue the task in `1-Projects/AIC-Tasks/AIC-<task-name>.md`. Read its
> progress, decisions, blockers, and acceptance criteria before doing
> anything.

### Finish a task

Before merging its PR:

1. Confirm every acceptance criterion is checked truthfully.
2. Read the handoff/results section.
3. Review **Changes** or **Files changed**.
4. Look for secrets, unexpected deletions, and unrelated changes.
5. Check available validation results.
6. Merge only when you accept the result.

After the merge, the task and its results are part of the durable second brain.

---

## Safety rules

- Keep the repository **private**.
- Enable GitHub **2FA**.
- Keep secrets in a password manager, never in repository files.
- Use a cloud or local sandbox when appropriate.
- Use Plan or Interactive mode for risky work.
- Review every PR before merging it.
- Require approval for spending, publication of private information, deletion
  of important data, and other hard-to-reverse actions.
- Archive useful completed material instead of deleting it.

## Essential terms

| Term | Meaning |
| --- | --- |
| **Repository** | A folder and its saved history on GitHub |
| **Project** | A repository or folder connected to the Copilot App |
| **Session** | One agent conversation and its workspace |
| **Working tree** | A separate local copy used by one session |
| **Branch** | A separate version containing one task's changes |
| **Pull request (PR)** | The review page used before adding changes to `main` |
| **Commit** | A saved snapshot of changes |
| **Merge** | Add approved PR changes to the main version |

## Official help

- [Getting started with the GitHub Copilot App](https://docs.github.com/en/copilot/get-started/quickstart-copilot-app)
- [About the GitHub Copilot App](https://docs.github.com/en/copilot/concepts/agents/github-copilot-app)
- [Working with agent sessions](https://docs.github.com/en/copilot/how-tos/github-copilot-app/agent-sessions)
- [Managing issues and pull requests](https://docs.github.com/en/copilot/how-tos/github-copilot-app/managing-issues-and-pull-requests)
- [Adding repository instructions](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions)
- [Creating a GitHub repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
- [Configuring two-factor authentication](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)

The App changes over time. If a label moves, follow the same concept and check
the current official help page.
