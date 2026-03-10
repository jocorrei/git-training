# Branching — Working Without Breaking Things

A **branch** is your own safe copy of the project where you can make changes freely without affecting anyone else. When your work is ready, you merge it back.

---

## Create a dev branch

```bash
git checkout -b dev
```

Output:

```
Switched to a new branch 'dev'
```

You're now on the `dev` branch. Your commit from the previous section came with you — it's already here.

Confirm:

```bash
git branch
```

```
* dev
  main
```

---

## Push to GitHub

```bash
git push -u origin dev
```

The `-u origin dev` part tells Git: *"push this branch to GitHub and remember this connection for future pushes"*. You only need `-u origin dev` the first time. After that, just `git push` is enough.

Output:

```
 * [new branch]      dev -> dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
```

---

## Confirm on GitHub

Go to the repo on GitHub (your instructor will share the URL). Click the branch dropdown — you'll see `dev` listed alongside `main`. Your change is live on GitHub, safely isolated from `main`.

---

## Why branches matter

Think of `main` as the published version of a website. You never edit it directly — you work on a draft (your branch), get it reviewed, and only then publish it.

Every change you make from now on follows this pattern:

```
Create branch → Make changes → Push branch → Open PR → Get reviewed → Merge to main
```

In the next section, you'll see what happens when two people make conflicting changes on the same branch at the same time.
