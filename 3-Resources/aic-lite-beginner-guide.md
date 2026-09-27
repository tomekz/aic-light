# AIC-Lite: Your Own AI Assistant Setup (Beginner Guide)

A lightweight version of our "AI Champion" setup. You don't need an orchestrator.
You run the AI agents yourself. Three things make this work:

1. **Copilot instructions**: fixed rules the AI reads every time it starts.
2. **Second brain**: a private GitHub repo of notes, so the AI remembers things between sessions.
3. **Work board**: one file that tracks what each agent is working on, so you can run 2-3 at once.

Setup takes about 1-2 hours. You don't need any git knowledge before you start.

---

## Part 1 - Accounts and plan (about 20 min)

### 1.1 Create a GitHub account
1. Go to https://github.com/signup and sign up. Use a username you're happy to keep.
2. Verify your email.
3. **Turn on two-factor authentication (2FA)**: Settings → Password and authentication →
   Enable 2FA. Use an authenticator app. Save the recovery codes in your password manager.

### 1.2 Buy a Copilot plan
1. Go to https://github.com/features/copilot/plans.
2. **Recommended: Copilot Pro+.** This is the top individual tier. It gives you the
   frontier models (the strongest Claude, GPT and Gemini models) and the most premium
   requests. Copilot Pro is cheaper but has fewer premium requests and fewer models.
   Check the page for current prices and limits.
3. After you buy, open https://github.com/settings/copilot and make sure the models you
   want are **enabled**. Some are off by default.

---

## Part 2 - Install the tools (about 30 min)

Install these on your computer. macOS, Windows or Linux all work.

| Tool | Why | Where |
|------|-----|-------|
| **Git** | Saves versions of files and syncs them to GitHub | https://git-scm.com/downloads (macOS: run `xcode-select --install`) |
| **Node.js 22+ (LTS)** | Required by the Copilot CLI | https://nodejs.org |
| **GitHub CLI (`gh`)** | Signs you in to GitHub from the terminal | https://cli.github.com |
| **VS Code** (optional, recommended) | Nice way to read and edit your notes | https://code.visualstudio.com |
| **Copilot CLI** | The AI agent you'll run | See the command below |

Open a terminal. On macOS that's the **Terminal** app. On Windows use **Windows Terminal**.
Then run these one at a time:

```bash
# 1. Install the Copilot CLI
npm install -g @github/copilot

# 2. Tell git who you are (use your GitHub email)
git config --global user.name  "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main

# 3. Sign in to GitHub. Pick: GitHub.com → HTTPS → Login with a web browser
gh auth login
gh auth setup-git

# 4. Start Copilot once and sign in when it asks
copilot
```

In Copilot, type `/login` if it asks you to. Type `/model` to see which models you can use
and pick a frontier one. Type `/exit` to quit.

---

## Part 3 - Git in 5 minutes (only what you need)

Git takes snapshots of a folder. GitHub keeps a copy of those snapshots online.

| Word | Meaning |
|------|---------|
| **repo** | A folder that git tracks |
| **clone** | Download a repo from GitHub to your computer |
| **commit** | Save a snapshot of your changes, with a short message |
| **push** | Upload your commits to GitHub |
| **pull** | Download the latest changes from GitHub |

These four commands cover 95% of what you'll do:

```bash
git pull                          # get the latest version first
git add -A                        # stage all your changes
git commit -m "what I changed"    # take a snapshot
git push                          # upload it to GitHub
```

> Tip: you can ask Copilot to do it for you: *"commit and push my notes with a sensible message"*.

---

## Part 4 - Create your Second Brain repo (about 20 min)

The AI forgets everything when a session ends. This repo is its long-term memory, and yours.

### 4.1 Create it
```bash
cd ~                                   # your home folder
gh repo create second-brain --private --clone
cd second-brain
```
> ⚠️ Keep it **private**. Never put passwords, API keys or tokens in it.

### 4.2 Folder layout (simple "PARA" style)
```bash
mkdir -p 00-Inbox 01-Projects 02-Areas 03-Resources 04-Archive 99-Templates work/tasks
```

| Folder | What goes in it |
|--------|-----------------|
| `00-Inbox/` | Quick notes you haven't sorted yet. Sort them weekly. |
| `01-Projects/` | Things with an end date (for example `01-Projects/new-laptop-setup/`) |
| `02-Areas/` | Ongoing responsibilities (for example `02-Areas/home-network/`, `02-Areas/finances/`) |
| `03-Resources/` | Reference notes, how-tos, snippets, useful links |
| `04-Archive/` | Finished projects. Move them here instead of deleting them. |
| `99-Templates/` | Note templates |
| `work/BOARD.md` | **The work board**: what every agent is doing right now |
| `work/tasks/` | One file per task (the brief plus a progress log) |

### 4.3 Create the starter files

**`README.md`** (the map the AI reads first):
```markdown
# Second Brain
Personal knowledge base. The AI reads this first.

- Active work: work/BOARD.md
- Task files: work/tasks/<task-id>.md
- Notes use lowercase-with-dashes.md names.
- Every note starts with: Title, Date, Tags, a one-line Summary.
```

**`99-Templates/task.md`**:
```markdown
# T-000 - <short title>
- Status: todo | doing | blocked | done
- Agent: <terminal tab name, e.g. A1>
- Started: YYYY-MM-DD
- Repo/folder: <where the work happens>

## Goal (what "done" looks like)
- ...

## Plan
1. ...

## Log (newest at the bottom, the agent appends here)
- YYYY-MM-DD HH:MM - started

## Result / lessons learned
- ...
```

**`99-Templates/note.md`**:
```markdown
# <Title>
- Date: YYYY-MM-DD
- Tags: #tag1 #tag2
- Summary: one line

## Notes
...
```

**`work/BOARD.md`**:
```markdown
# Work Board
Keep this short. One row per active task. Move done rows to "Done" weekly.

## Active
| Task | Title | Agent | Status | Last update | Next step |
|------|-------|-------|--------|-------------|-----------|

## Waiting on me (agent is blocked / needs a decision)
- (none)

## Done (this week)
- (none)
```

Save everything to GitHub:
```bash
git add -A && git commit -m "Initial second brain" && git push
```

---

## Part 5 - Copilot instructions (the rules) (about 15 min)

Copilot automatically reads **`~/.copilot/copilot-instructions.md`** at the start of every
session. This is where you tell it who you are, where your second brain lives and how to
track work.

Create the file:
```bash
mkdir -p ~/.copilot
code ~/.copilot/copilot-instructions.md     # or: nano ~/.copilot/copilot-instructions.md
```

Paste this, then edit the parts in `<...>`:

```markdown
# My Copilot Instructions

## About me
- I'm <name>, a beginner-to-intermediate tech person. Explain things simply.
- Ask before deleting files, spending money, or changing anything outside the current folder.
- Never put passwords, tokens or keys into files or commits.

## Second brain (long-term memory)
- My knowledge base is the git repo at ~/second-brain.
- BEFORE answering "what do I know / what did we do about X", search ~/second-brain first.
- AFTER finishing something worth remembering (a decision, a fix, a how-to),
  write or update a note in the right folder using 99-Templates/note.md,
  then commit and push: `git -C ~/second-brain pull --rebase && git -C ~/second-brain add -A && git -C ~/second-brain commit -m "<msg>" && git -C ~/second-brain push`.

## Working on tasks (I run several agents in parallel)
- Every piece of work has a task id like T-012 and a file ~/second-brain/work/tasks/T-012-<slug>.md.
- When I say "start task T-012: <description>":
  1. Create the task file from 99-Templates/task.md (if it doesn't exist).
  2. Add or update its row in ~/second-brain/work/BOARD.md (Status = doing).
  3. Write a short plan in the task file and show it to me before doing big changes.
- While working: append one line to the task's "Log" at each milestone
  (plan done, change made, tested, blocked, done). Keep BOARD.md "Last update" and "Next step" current.
- If you need a decision from me, set Status = blocked, add it under "Waiting on me", and stop.
- Only touch the task file and BOARD.md row for YOUR task, because other agents edit the same repo.
- Always `git pull --rebase` before committing to ~/second-brain. If the push fails, pull again and retry.
- When done: fill in "Result / lessons learned", set Status = done, and move the row to "Done".

## Style
- Short answers, bullet points, copy-pasteable commands.
```

> Per-project rules: inside any project repo you can also add `.github/copilot-instructions.md`
> for rules that only apply to that project.

---

## Part 6 - The daily workflow (you are the orchestrator)

### Starting work
1. Open a terminal **tab per agent** and name it after the agent (`A1`, `A2`, `A3`).
   Start with **2 agents at most**, and go up to 3 once you're comfortable.
2. In each tab, go to the folder the task is about, then start Copilot:
   ```bash
   cd ~/projects/my-thing
   copilot
   ```
3. Let the agent reach your second brain, and name the session after the agent:
   ```
   /add-dir ~/second-brain
   /rename A1-T-012
   ```
4. Give it the task in one message:
   > start task T-012: set up automatic backups of my Documents folder to an external drive.
   > You are agent A1.
5. Read its plan and approve it (or correct it).

### While agents run
- **`work/BOARD.md` is your control panel.** Open it in VS Code (it refreshes when files
  change) and you can see what every agent is doing.
- Look at the **"Waiting on me"** section first. That's where agents ask for your decisions.
- Switch tabs, answer, and move on.

### Rules that stop agents getting in each other's way
| Rule | Why |
|------|-----|
| One task = one agent = one tab | You always know who's doing what |
| Two agents never work in the **same project folder** at once | They'd overwrite each other's changes |
| Each agent edits only **its own** task file and board row | No conflicts in the second brain |
| Agents always `git pull --rebase` before pushing | Keeps everyone's notes in sync |
| Big or risky changes → agent shows the plan first | You stay in control |

### Pausing and resuming
- Type `/exit` to quit. Later, run `copilot` again, type `/resume` and pick the session.
- Even if you lose the session, say **"continue task T-012"**. The agent reads the task
  file and its log and picks up where it stopped. That's why the log matters.

### End of day (5 min)
Ask any agent:
> Review work/BOARD.md: update stale rows, list what's waiting on me, commit and push.

### Weekly (15 min)
> Sort 00-Inbox into the right folders, move finished projects to 04-Archive,
> clear the Done section of BOARD.md into a weekly summary note in 02-Areas/weekly/.

---

## Part 7 - Useful Copilot CLI commands

| Command | What it does |
|---------|--------------|
| `/model` | Pick the AI model (use a frontier model for hard tasks, a cheaper one for simple ones) |
| `/resume` | Continue a previous session |
| `/rename` | Name the session (e.g. `A1-T-012`) so `/resume` is easy |
| `/add-dir ~/second-brain` | Let an agent working elsewhere read and write your notes |
| `/plan` | Make the agent plan before it changes anything |
| `/clear` | Start fresh in the same window |
| `/usage` | See how much of your plan you've used |
| `/help` | All commands |
| `@file.txt` | Include a file in your message |
| `!command` | Run a shell command yourself without asking the AI |

---

## Part 8 - Safety checklist

- [ ] 2FA is on for GitHub
- [ ] The second-brain repo is **private**
- [ ] No passwords, keys or tokens in any note or instruction file (use a password manager)
- [ ] Read what the agent is about to run before approving anything that deletes, installs or pays for something
- [ ] Commit and push the second brain at least daily. It's your backup.

---

## Where to go next (optional, once this feels easy)
- **Skills**: save repeated workflows as `~/.copilot/skills/<name>/SKILL.md` so any agent can reuse them.
- **MCP servers**: connect Copilot to other tools such as your calendar, email or issue tracker.
- **Git worktrees**: let two agents work safely on the same project in separate copies.
- **Automation**: this is what the full AIC system automates. It picks up tasks, starts agents
  and updates the board for you. Do it by hand first so you understand every piece.
