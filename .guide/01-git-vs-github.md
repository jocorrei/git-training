# Git vs GitHub

## The one-line version

**Git** is a tool that runs on your computer and tracks changes to your files.
**GitHub** is a website that stores those changes in the cloud so you can share them with others.

They are not the same thing. You can use Git without GitHub. But together, they are how almost every software team in the world manages code.

---

## The analogy

Think about Google Docs.

When you write a document in Google Docs, it saves every version automatically. You can go back in time and see what the document looked like last Tuesday. You can share it with someone and work on it at the same time.

Git and GitHub do the same thing — but for code files.

| Google Docs | Git / GitHub |
|---|---|
| Saves versions automatically | You decide when to save a version (called a "commit") |
| Lives in the cloud | Git lives on your computer, GitHub stores it online |
| Share with a link | Share via a repository (repo) |
| Comments on the doc | Comments on a Pull Request |

The key difference: **Git gives you control**. You decide what gets saved, when, and with a message explaining why.

---

## Why developers use it

Imagine you're editing an HTML file for a campaign landing page. You make 40 changes over two days. Then the client says *"can we go back to how the button looked on Monday?"*

Without Git: you're digging through `final_v2_backup_REAL.html` files hoping you saved it somewhere.

With Git: you type one command and you're back to Monday in seconds.

Now imagine two people editing that same file at the same time. Without Git, whoever saves last wins and the other person's work is gone. With Git, both changes are tracked and can be merged intelligently.

---

## Key vocabulary

| Term | What it means |
|---|---|
| **Repository (repo)** | A folder tracked by Git. Think of it as a project. |
| **Commit** | A saved snapshot of your changes, with a message describing what you did |
| **Branch** | A parallel version of your project where you can experiment safely |
| **Pull Request (PR)** | A proposal to merge your changes into the main project |
| **Clone** | Download a repo from GitHub to your computer |
| **Push** | Upload your local commits to GitHub |
| **Pull** | Download the latest changes from GitHub to your computer |

You don't need to memorize these now. They'll make sense once you use them.
