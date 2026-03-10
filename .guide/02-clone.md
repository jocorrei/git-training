# Clone the Repository

A **repository** (repo) is a project tracked by Git. Cloning means downloading a copy of it to your computer so you can work on it locally.

---

## What is this repo?

The repo you're about to clone is the one used for this masterclass. It's a private repo — you've been given access to it. Think of it as a shared project folder that lives on GitHub and that your whole team can contribute to.

---

## Clone it

Run this command:

```bash
gh repo clone YOUR-INSTRUCTOR/git-masterclass
```

Replace `YOUR-INSTRUCTOR` with the GitHub username your instructor gives you.

The `gh repo clone` command does two things at once: it clones the repo *and* sets up the GitHub connection automatically, so you don't have to configure anything manually.

You'll see output like:

```
Cloning into 'git-masterclass'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
```

---

## Navigate into the folder

```bash
cd git-masterclass
```

You're now inside the project. List the files:

```bash
ls
```

You'll see `CHANGE_ME.md`, `README.md`, and a `.guide/` folder with all the lesson content.

---

## Check the status

```bash
git status
```

Output:

```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

This means your local copy is in sync with GitHub. Nothing has changed yet.

---

## Check which branch you're on

```bash
git branch
```

Output:

```
* main
```

The `*` means you're on the `main` branch. Keep that in mind — it'll matter in the next section.
