# Branching

## The problem branching solves

Have you ever saved a file like this?

```
landing-page.html
landing-page-v2.html
landing-page-v2-FINAL.html
landing-page-v2-FINAL-client-edits.html
landing-page-v2-FINAL-client-edits-2.html
```

That's you manually creating branches. Git does this cleanly, without duplicating files.

A **branch** is a parallel version of your project. You experiment on the branch. If it works, you merge it back. If it doesn't, you throw it away. The original is never touched.

---

## The main branch

Every repo starts with one branch called `main`. This is your production code — the version that's live, working, and stable. The rule is simple: **never work directly on main**.

Always create a new branch for every change you make.

---

## Step 1 — Create and switch to a branch

```bash
git checkout -b add-contact-section
```

This creates a new branch called `add-contact-section` and switches to it immediately.

Check which branch you're on:

```bash
git branch
```

The branch with `*` is your current one.

---

## Step 2 — Make changes on the branch

Edit `README.md` and add:

```
## Contact

Email us at hello@example.com
```

Stage and commit:

```bash
git add .
git commit -m "Add contact section to README"
```

---

## Step 3 — See that main is untouched

Switch back to main:

```bash
git checkout main
```

Open `README.md`. Your contact section is gone — because it only exists on your branch. Main is exactly as you left it.

Switch back to your branch:

```bash
git checkout add-contact-section
```

The contact section is back.

---

## Step 4 — Merge the branch into main

Once you're happy with the changes, merge them:

```bash
git checkout main
git merge add-contact-section
```

Now main has your contact section. The branch did its job.

---

## Step 5 — Push the branch to GitHub

Before merging locally, in a real team workflow you'd push the branch to GitHub first and create a Pull Request (next section). Let's practice pushing a branch:

```bash
git checkout -b update-readme-title
```

Make a small change, commit it, then push:

```bash
git push -u origin update-readme-title
```

The `-u origin` part is only needed the first time you push a new branch. After that, `git push` is enough.

---

## Branch naming conventions

Good branch names describe what the branch does:

| Pattern | Example |
|---|---|
| `feature/` | `feature/add-cookie-banner` |
| `fix/` | `fix/broken-image-link` |
| `update/` | `update/hero-copy` |

Avoid names like `my-branch`, `test`, or `stuff`.

---

## Commands cheat sheet

```bash
git checkout -b <name>     # Create and switch to new branch
git checkout <name>        # Switch to existing branch
git branch                 # List all branches
git merge <name>           # Merge branch into current branch
git push -u origin <name>  # Push new branch to GitHub
git branch -d <name>       # Delete branch after merging
```

---

## Visual summary

```
main:     A ── B ── C ──────────── F (merge)
                      \          /
feature:               D ── E ──
```

Your changes (D, E) happen in isolation. Main stays at C until you're ready to merge.
