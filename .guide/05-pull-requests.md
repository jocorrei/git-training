# Pull Requests

## What is a Pull Request?

A Pull Request (PR) is a way of saying: *"I made some changes on my branch. Can someone review them before we merge into main?"*

It's the core collaboration mechanism on GitHub. Even if you work alone, PRs are a good habit — they give you a clean record of every change and why it was made.

---

## The workflow

```
Create branch → Make changes → Push branch → Open PR → Review → Merge
```

---

## Step 1 — Push your branch to GitHub

Make sure you have a branch with some commits that aren't on main yet. If you completed the branching section, use `update-readme-title`. Otherwise create one now:

```bash
git checkout -b add-project-description
```

Make a change, commit it:

```bash
git add .
git commit -m "Add project description to README"
git push -u origin add-project-description
```

---

## Step 2 — Open a Pull Request on GitHub

1. Go to your repo on GitHub
2. You'll see a yellow banner: **"Your branch had recent pushes"** → click **Compare & pull request**
3. Fill in the PR form:
   - **Title**: short summary of what you did (`Add project description to README`)
   - **Description**: explain *why* you made this change. What problem does it solve?
4. Click **Create pull request**

---

## Step 3 — Review the PR

On the PR page, click the **Files changed** tab. This shows a diff — exactly what lines were added (green) and removed (red).

This is what a teammate would see when reviewing your work. They can:
- Leave comments on specific lines
- Approve the PR
- Request changes before merging

---

## Step 4 — Merge the PR

Once approved (or if you're working alone), click **Merge pull request** → **Confirm merge**.

Your changes are now on main. GitHub will offer to delete the branch — go ahead and do it, the branch has served its purpose.

---

## Step 5 — Sync your local main

GitHub's main is now ahead of your local main. Pull the changes down:

```bash
git checkout main
git pull
```

---

## What makes a good PR?

| | Bad PR | Good PR |
|---|---|---|
| Size | 47 files changed | 3-5 files changed |
| Title | `updates` | `Fix broken link in campaign footer` |
| Description | (empty) | Explains what changed and why |
| Commits | `aaa`, `test`, `fix2` | Clear, logical messages |

**Small PRs get reviewed faster and merged with fewer problems.** If a PR is too big, break it into smaller ones.

---

## PR description template

This is a simple template you can use every time:

```markdown
## What
Brief description of the change.

## Why
What problem does this solve? What was wrong before?

## How to test
Steps to verify the change works correctly.
```

---

## Draft Pull Requests

If your work isn't ready for review yet, open a **Draft PR**. Click the arrow next to "Create pull request" and select **Create draft pull request**.

This lets teammates see your work in progress without them thinking it's ready to merge.
