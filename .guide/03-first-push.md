# Your First Push (and Why It Fails)

Time to make your first change and try to push it to GitHub. Spoiler: it won't work — and that's the point.

---

## Edit CHANGE_ME.md

Open `CHANGE_ME.md` in any text editor and fill in your name, role, and what you want to learn. Save the file.

---

## Stage and commit your change

Check what changed:

```bash
git status
```

Git will show `CHANGE_ME.md` as modified. Stage it:

```bash
git add CHANGE_ME.md
```

Commit it with a message:

```bash
git commit -m "Add my details to CHANGE_ME.md"
```

You've saved a snapshot of your change locally. It exists on your machine but not on GitHub yet.

---

## Try to push

```bash
git push
```

You'll get an error:

```
remote: error: GH006: Protected branch update failed for refs/heads/main.
remote: error: At least 1 approving review is required by reviewers with write access.
To https://github.com/YOUR-INSTRUCTOR/git-masterclass.git
 ! [remote rejected] main -> main (protected branch hook declined)
error: failed to push some refs to 'https://github.com/...'
```

---

## Why did this happen?

The `main` branch is **protected**. The project owner has configured GitHub to block anyone from pushing directly to it. This is standard practice on any professional team.

The rule is simple: **nothing goes to main without a review**.

This is not a bug. This is the system working exactly as intended.

The solution is to create your own branch, push there, and open a Pull Request so your changes can be reviewed before they reach main. That's what you'll do next.

---

## What you learned

- How to stage, commit, and push
- That `main` is protected and why that matters
- That the real workflow always goes through branches
