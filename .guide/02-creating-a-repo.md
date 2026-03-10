# Creating a Repository

## What you'll do

By the end of this section you'll have a real repository on GitHub, cloned to your computer and ready to work with.

---

## Step 1 — Create a repo on GitHub

1. Go to [github.com](https://github.com) and sign in
2. Click the **+** icon in the top right → **New repository**
3. Fill in the form:
   - **Repository name**: `my-first-repo` (or anything you like)
   - **Description**: optional, but good habit to fill in
   - **Public vs Private**: choose Public for now
   - Check **"Add a README file"** — this creates the first file automatically
4. Click **Create repository**

You now have a live repository on the internet.

---

## Step 2 — Clone it to your computer

Cloning means downloading the repo so you can work on it locally.

On your repo page, click the green **Code** button, make sure **HTTPS** is selected, and copy the URL. It looks like:

```
https://github.com/your-username/my-first-repo.git
```

Open your terminal and run:

```bash
git clone https://github.com/your-username/my-first-repo.git
```

This creates a folder called `my-first-repo` on your computer. Navigate into it:

```bash
cd my-first-repo
```

---

## Step 3 — Explore what's inside

```bash
ls
```

You'll see `README.md` — the file GitHub created for you. This is a Markdown file. It's what shows up on your repo's homepage on GitHub.

Run this to see that Git is already tracking this folder:

```bash
git status
```

It should say `nothing to commit, working tree clean`. That means your local copy is in sync with GitHub.

---

## What just happened

```
GitHub (cloud)          Your computer (local)
┌─────────────────┐     ┌─────────────────┐
│  my-first-repo  │────▶│  my-first-repo  │
│  (README.md)    │clone│  (README.md)    │
└─────────────────┘     └─────────────────┘
```

You now have two copies: one on GitHub, one on your machine. Git keeps them in sync. The next section shows you how.
