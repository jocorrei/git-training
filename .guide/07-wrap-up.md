# Wrap Up

Two things to close the session: a secret you should never commit, and the full workflow in one place.

---

## Never commit secrets

Open the `.env.example` file in this repo. It looks like this:

```
API_KEY=your-api-key-here
DATABASE_URL=your-database-url-here
```

In a real project, `.env` holds actual values — API keys, database passwords, tokens. These are secrets. If you commit them to GitHub, even on a private repo, they are compromised. People get hacked this way. Companies lose money this way.

The solution is `.gitignore`.

---

## What is .gitignore?

Open the `.gitignore` file at the root of this repo. You'll see:

```
.env
```

That single line tells Git: *"never track this file, no matter what"*. Even if you run `git add .`, Git will skip `.env` completely.

Check it yourself:

```bash
cp .env.example .env
```

Now open `.env` and replace the placeholder values with anything:

```
API_KEY=super-secret-123
DATABASE_URL=postgres://localhost/mydb
```

Save the file. Now run:

```bash
git status
```

`.env` doesn't appear. Git is ignoring it exactly as instructed.

Run this to confirm:

```bash
git check-ignore -v .env
```

Output:

```
.gitignore:1:.env    .env
```

Git tells you exactly which line in `.gitignore` is responsible for ignoring the file.

---

## The rule

| File | Commit it? |
|---|---|
| `.env.example` | ✅ Yes — it's a template with no real values |
| `.env` | ❌ Never — it has real secrets |
| `.gitignore` | ✅ Yes — it protects the whole team |

Always commit `.env.example` so teammates know which variables they need. Never commit `.env`.

---

## The complete workflow

This is everything you learned today, in order:

```bash
# 1. One-time setup
brew install gh
gh auth login

# 2. Get the project
gh repo clone jocorrei/git-training
cd git-training

# 3. Start a new piece of work — always branch first
git checkout -b your-branch-name

# 4. Make changes, then save them
git add .
git commit -m "Describe what you did"

# 5. Upload to GitHub
git push -u origin your-branch-name   # first push on a new branch
git push                               # every push after that

# 6. If someone else pushed changes first
git pull                               # get their changes
# fix conflicts if any, then:
git add .
git commit -m "Resolve conflict"
git push

# 7. Open a Pull Request
gh pr create

# 8. After your PR is merged, sync your local main
git checkout main
git pull
```

That's it. This is the workflow used by development teams at every company, every day.

---

## Quick reference card

| Command | What it does |
|---|---|
| `git status` | What has changed? |
| `git add .` | Stage all changes |
| `git commit -m "..."` | Save a snapshot |
| `git push` | Upload to GitHub |
| `git pull` | Download latest changes |
| `git checkout -b name` | Create and switch to a new branch |
| `git branch` | List all branches |
| `git log --oneline` | See commit history |
| `gh pr create` | Open a Pull Request |
| `gh auth status` | Check GitHub authentication |
