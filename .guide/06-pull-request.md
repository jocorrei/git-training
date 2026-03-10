# Pull Requests — Getting Your Work Reviewed

A **Pull Request** (PR) is a formal way of saying: *"I'm done with my changes. Can someone review them before they go to main?"*

It's how every professional team ships code. Nothing goes to `main` without a PR.

---

## Create the PR from the terminal

Make sure you're on the `dev` branch with everything pushed:

```bash
git status
```

Should say `nothing to commit, working tree clean`. If not, commit and push first.

Now create the PR:

```bash
gh pr create
```

The CLI will walk you through it interactively:

```
? Title: Add my details and favourite tool
? Body: Leave blank to open editor, enter to skip
? What's next? Submit
```

For the title, write something descriptive. For the body, press Enter to skip for now (you can add a description later).

Output:

```
https://github.com/YOUR-INSTRUCTOR/git-masterclass/pull/1
```

Your PR is live. Copy that URL.

---

## See it on GitHub

Open the PR URL in your browser. You'll see:

- **The title and description** you wrote
- **The Files changed tab** — every line you added (green) and removed (red)
- **The Commits tab** — all commits that are part of this PR
- **The conversation** — where reviewers leave comments

This is exactly what your instructor sees when they review your work.

---

## Wait for approval

Your instructor will review the PR and either:

- **Approve it** — the PR can be merged
- **Request changes** — they'll leave a comment explaining what to fix

If changes are requested, fix them locally, commit, and push again. The PR updates automatically — no need to create a new one.

---

## Merge the PR

Once approved, click **Merge pull request** → **Confirm merge** on GitHub.

Your changes are now on `main`. The work you did on `dev` is officially part of the project.

GitHub will offer to delete the `dev` branch — go ahead. The branch has served its purpose.

---

## Sync your local main

Your local `main` is still behind. Pull the latest:

```bash
git checkout main
git pull
```

You're fully up to date.

---

## The complete workflow you just learned

```
Clone repo
    ↓
Make changes locally
    ↓
git add → git commit
    ↓
git push → BLOCKED on main
    ↓
Create branch (dev)
    ↓
git push → SUCCESS
    ↓
Conflict → pull → fix → commit → push
    ↓
gh pr create → review → merge
    ↓
Done
```

This is the real workflow used by development teams at companies of every size. You now know how to use it.
