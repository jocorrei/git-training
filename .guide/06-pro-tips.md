# Pro Tips

## 1. Use a .gitignore file

Some files should never be committed: passwords, API keys, local config files, generated folders. A `.gitignore` file tells Git to ignore them completely.

Create a `.gitignore` in your repo root:

```
# Dependencies
node_modules/

# Environment variables (NEVER commit these)
.env
.env.local

# OS files
.DS_Store
Thumbs.db

# Build output
dist/
build/
```

GitHub has a collection of ready-made `.gitignore` templates for every language. When creating a repo, you can pick one from the dropdown.

---

## 2. Fix your last commit message

You just committed and realized you made a typo in the message. Fix it before pushing:

```bash
git commit --amend -m "Correct message here"
```

**Only do this before pushing.** Once a commit is on GitHub, amending rewrites history and causes problems for teammates.

---

## 3. Undo a commit (keep the changes)

You committed too early and want to add more changes to it:

```bash
git reset --soft HEAD~1
```

This removes the last commit but keeps your files exactly as they were. Your changes go back to "staged" and you can commit again.

---

## 4. See who changed a line

Want to know who last touched a specific line in a file?

```bash
git blame <filename>
```

This shows every line with the commit hash, author name, and date. On GitHub, you can also click **Blame** on any file to see this in the browser.

---

## 5. GitHub Desktop as a fallback

If you ever forget a command or feel stuck in the terminal, **GitHub Desktop** is a free GUI app that does everything visually. It's not a crutch — it's a valid tool, and many experienced developers use it for certain tasks.

Download it at [desktop.github.com](https://desktop.github.com).

---

## 6. Write commit messages in imperative mood

Commit messages read better when they complete this sentence: *"If applied, this commit will..."*

| Wrong | Right |
|---|---|
| `Added tracking script` | `Add tracking script` |
| `Fixed broken image` | `Fix broken image` |
| `Updated copy` | `Update hero section copy` |

---

## 7. git stash — save work without committing

You're in the middle of something and need to quickly switch branches, but you're not ready to commit yet.

```bash
git stash
```

Your changes are saved in a temporary shelf. Switch branches, do your thing, then come back and restore:

```bash
git stash pop
```

---

## 8. Shortcuts worth memorizing

```bash
git status                  # Your best friend, run it constantly
git log --oneline           # Clean commit history
git diff                    # What changed since last commit
git checkout -              # Switch to the previous branch
git push -u origin HEAD     # Push current branch without typing its name
```

---

## What to learn next

You now know enough Git to work professionally. When you're ready to go deeper:

- **Rebasing** — a cleaner alternative to merging
- **Cherry-pick** — apply a single commit from another branch
- **Git bisect** — find which commit introduced a bug
- **GitHub Actions** — automate tasks when you push code (tests, deployments)
- **Protected branches** — prevent direct pushes to main in a team setting
