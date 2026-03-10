# Conflicts — When Two People Edit the Same Thing

A **merge conflict** happens when two people change the same lines of the same file. Git doesn't know which version to keep, so it stops and asks you to decide.

This is the moment most beginners panic. By the end of this section, you won't.

---

## Make another change

Open `CHANGE_ME.md` and add a line at the bottom:

```
**Favourite tool:**  (write anything)
```

Save the file, stage, and commit:

```bash
git add CHANGE_ME.md
git commit -m "Add favourite tool"
```

Now try to push:

```bash
git push
```

You'll get an error:

```
 ! [rejected]        dev -> dev (fetch first)
error: failed to push some refs to 'https://github.com/...'
hint: Updates were rejected because the remote contains work that you do not have locally.
hint: Integrate the remote changes before pushing again.
```

---

## What just happened?

While you were working, your instructor pushed a change to the `dev` branch on GitHub. Now your local version and the GitHub version have **diverged** — they both have commits the other doesn't know about.

Git refuses to push because it doesn't want to overwrite your instructor's work.

---

## Step 1 — Pull the remote changes

```bash
git pull
```

Git will try to merge the remote changes with yours automatically. But since both you and your instructor edited the same lines, it can't — and it tells you:

```
Auto-merging CHANGE_ME.md
CONFLICT (content): Merge conflict in CHANGE_ME.md
Automatic merge failed; fix conflicts and then commit the result.
```

---

## Step 2 — Open the conflicted file

Open `CHANGE_ME.md`. You'll see something like this:

```
<<<<<<< HEAD
**Favourite tool:** Figma
=======
**Favourite tool:** Notion
>>>>>>> abc1234 (Add favourite tool from instructor)
```

Git is showing you both versions:
- Everything between `<<<<<<< HEAD` and `=======` is **your version**
- Everything between `=======` and `>>>>>>>` is **their version**

---

## Step 3 — Resolve the conflict

Edit the file to keep what makes sense. You can keep yours, keep theirs, or combine both. For example:

```
**Favourite tool:** Figma (and Notion for docs)
```

Delete the `<<<<<<<`, `=======`, and `>>>>>>>` lines completely — Git added those as markers, they're not real content.

Save the file.

---

## Step 4 — Commit the resolution

```bash
git add CHANGE_ME.md
git commit -m "Resolve conflict in CHANGE_ME.md"
git push
```

Output:

```
To https://github.com/YOUR-INSTRUCTOR/git-masterclass.git
   abc1234..def5678  dev -> dev
```

The conflict is resolved. Your changes and your instructor's changes now coexist on the branch.

---

## What you learned

- Conflicts happen when two people edit the same lines
- Git marks them clearly — it never silently overwrites anyone's work
- Resolving them is just editing a file and committing the result
- The process is always: `pull → fix → add → commit → push`
