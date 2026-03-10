# Setup

Before writing a single line, you need two tools on your machine: **Git** and the **GitHub CLI**. This takes about 5 minutes.

---

## Step 1 — Install Git

Open **Terminal** (press `Cmd+Space`, type `Terminal`, hit Enter).

Check if Git is already installed:

```bash
git --version
```

If you see something like `git version 2.x.x`, you're done — skip to Step 2.

If you get a popup saying *"The git command requires the command line developer tools"*, click **Install** and wait for it to finish. Then run `git --version` again to confirm.

---

## Step 2 — Install the GitHub CLI

The GitHub CLI (`gh`) lets you interact with GitHub directly from the terminal — cloning repos, creating pull requests, and more, without touching the browser.

Install it with Homebrew:

```bash
brew install gh
```

If you don't have Homebrew installed, run this first:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then run `brew install gh` again.

Confirm it worked:

```bash
gh --version
```

---

## Step 3 — Authenticate with GitHub

Connect the CLI to your GitHub account:

```bash
gh auth login
```

You'll be asked a few questions. Answer them like this:

```
? Where do you use GitHub?          GitHub.com
? What is your preferred protocol?  HTTPS
? Authenticate Git with credentials? Yes
? How would you like to authenticate? Login with a web browser
```

It will show you a one-time code and open a browser window. Paste the code, click Authorize, and you're done.

Confirm it worked:

```bash
gh auth status
```

You should see your GitHub username and a green checkmark.

---

## You're ready

You now have everything you need. In the next section you'll clone the course repository and start working.
