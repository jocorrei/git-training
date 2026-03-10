# Local Workflow

## The core loop

Everything in Git comes down to repeating this loop:

```
Make a change → Stage it → Commit it → Push it
```

You'll do this dozens of times a day. Let's walk through each step.

---

## Step 1 — Make a change

Open `README.md` in any text editor and add a line at the bottom:

```
This is my first change.
```

Save the file.

---

## Step 2 — See what changed

```bash
git status
```

Git will tell you that `README.md` has been modified. It shows up in red under "Changes not staged for commit".

To see the exact lines you changed:

```bash
git diff
```

Lines in red (starting with `-`) were removed. Lines in green (starting with `+`) were added.

---

## Step 3 — Stage your changes

Staging means telling Git *"include this in the next commit"*. Think of it like putting items in a box before sealing it.

```bash
git add README.md
```

To stage everything at once:

```bash
git add .
```

Run `git status` again. The file is now green under "Changes to be committed". It's in the box, but the box isn't sealed yet.

---

## Step 4 — Commit

A commit seals the box and puts a label on it.

```bash
git commit -m "Add first line to README"
```

The `-m` flag is followed by your commit message. Good messages are short and describe **what** and **why**, not how.

| Bad message | Good message |
|---|---|
| `update` | `Fix broken link in header` |
| `changes` | `Add UTM tracking to campaign page` |
| `asdfgh` | `Remove deprecated analytics script` |

Run `git log` to see your commit history:

```bash
git log --oneline
```

You'll see your new commit at the top with a short ID (called a hash) and your message.

---

## Step 5 — Push to GitHub

Your commit exists on your computer but not on GitHub yet. Push it:

```bash
git push
```

Go to your repo on GitHub and refresh. Your change is now live.

---

## The full picture

```
Your computer                        GitHub
┌──────────────────────────┐        ┌─────────────┐
│                          │        │             │
│  Edit file               │        │             │
│      ↓                   │        │             │
│  git add .               │        │             │
│      ↓                   │        │             │
│  git commit -m "..."     │──push─▶│   GitHub    │
│                          │        │             │
│  git log (check history) │        │             │
└──────────────────────────┘        └─────────────┘
```

---

## Commands cheat sheet

```bash
git status          # What's changed?
git diff            # Show me the exact changes
git add .           # Stage everything
git add <file>      # Stage one file
git commit -m "..."  # Commit with a message
git push            # Upload to GitHub
git log --oneline   # See commit history
```

---

## Practice exercise

1. Create a new file called `notes.md` and write anything in it
2. Stage it with `git add`
3. Commit it with a meaningful message
4. Push it to GitHub
5. Confirm it appears on your GitHub repo page
