# Complete Beginner Guide: Git + GitHub + VS Code

## First — What is Git and Why Do You Need It?

Imagine you are writing an essay.

You save it as:
- `essay.docx`
- `essay_final.docx`
- `essay_final2.docx`
- `essay_ACTUALLY_FINAL.docx`

This is messy. You don't know what changed between versions. If you break something, you can't easily go back.

**Git solves this problem.**

Git is a tool that:
- Tracks every change you make to your code
- Lets you go back to any previous version
- Lets you work with a team without overwriting each other's work
- Keeps a full history of your project

Think of Git like a **"save checkpoint" system** in a video game. Every time you commit, you create a checkpoint you can return to at any time.

---

## What is GitHub?

Git lives on **your computer**.
GitHub lives on **the internet**.

**GitHub** is a website that stores your code online so that:
- Your code is backed up (not lost if your laptop breaks)
- Other people can see or work on your code
- You can access it from any computer

> Git = the tool on your computer
> GitHub = the website that stores your code online

They are two different things. Git works without GitHub, but GitHub needs Git.

---

## What is VS Code?

**VS Code (Visual Studio Code)** is a code editor — like Microsoft Word, but for writing code.

It is free, popular, and works on Windows and Mac.

You will write your code inside VS Code.

---

## What is a Terminal?

The **terminal** (also called Command Prompt, PowerShell, or Command Line) is a window where you type commands directly to your computer.

Instead of clicking with a mouse, you type instructions.

Example:
```bash
mkdir my-project
```
This command creates a folder called `my-project`.

It looks scary at first — but you will only use a few commands. Each one is explained below.

---

## What is a Folder / Repository?

In Git, your project folder is called a **repository** (or "repo").

It is just a normal folder on your computer — but once you run `git init` inside it, Git starts tracking everything inside it.

---

# PART 1 — Installation

---

## Step 1: Install Git

1. Go to → https://git-scm.com/downloads
2. Click the download for your system (Windows or Mac)
3. Open the installer and click **Next** on every screen (default settings are fine)
4. Click **Finish**

---

## Step 2: Install VS Code

1. Go to → https://code.visualstudio.com/
2. Click **Download for Windows** or **Download for Mac**
3. Open the installer
4. Follow the steps — make sure to check **"Add to PATH"** if asked (Windows)
5. Click **Finish**

---

## Step 3: Create a GitHub Account

1. Go to → https://github.com
2. Click **Sign up**
3. Enter your email, create a password, choose a username
4. Verify your email address

> Your GitHub username will be part of your public profile. Choose something professional.

---

# PART 2 — Learn the Terminal (5 Commands You Need)

Before anything else, you need to know how to use the terminal.

---

## How to Open the Terminal

**On Windows:**
1. Press the `Windows` key on your keyboard
2. Type `cmd` or `PowerShell`
3. Press `Enter`

**On Mac:**
1. Press `Cmd + Space` at the same time
2. Type `Terminal`
3. Press `Enter`

A black or white window will open. This is your terminal.

---

## The 5 Commands You Will Use

### 1. `pwd` — Where am I?

```bash
pwd
```

This shows you which folder you are currently inside.

Example output:
```
C:\Users\YourName
```

---

### 2. `ls` — What is inside this folder?

```bash
ls
```

This lists all files and folders in your current location.

> On Windows Command Prompt, use `dir` instead of `ls`

---

### 3. `cd` — Move into a folder

```bash
cd my-project
```

This moves you inside the `my-project` folder.

```bash
cd ..
```

This moves you **up** one folder (back to the parent folder).

---

### 4. `mkdir` — Create a new folder

```bash
mkdir my-project
```

This creates a new folder called `my-project`.

---

### 5. `code .` — Open current folder in VS Code

```bash
code .
```

The `.` means "this folder". This opens your current folder in VS Code.

---

# PART 3 — Set Up Git

---

## Step 4: Verify Git is Installed

Open your terminal and type:

```bash
git --version
```

You should see something like:
```
git version 2.44.0
```

If you see an error like `git is not recognized`, Git was not installed correctly. Go back and reinstall it.

---

## Step 5: Tell Git Who You Are (Do This Once)

Git needs to know your name and email so it can label your changes.

Run these two commands (replace with your real name and email):

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

> Use the same email as your GitHub account.

To confirm it worked:

```bash
git config --global user.name
git config --global user.email
```

It should print back what you entered.

---

# PART 4 — Create Your First Project

---

## Step 6: Create a Project Folder

In your terminal, type:

```bash
mkdir my-first-project
cd my-first-project
```

What happened:
- `mkdir my-first-project` → created a new folder called `my-first-project`
- `cd my-first-project` → you are now inside that folder

To confirm where you are:
```bash
pwd
```

---

## Step 7: Open the Folder in VS Code

```bash
code .
```

VS Code will open with your empty folder.

> If `code .` does not work on Mac:
> 1. Open VS Code manually
> 2. Press `Cmd + Shift + P`
> 3. Type: `Shell Command: Install 'code' command in PATH`
> 4. Press Enter, then try again

> If `code .` does not work on Windows:
> 1. Open VS Code manually
> 2. Click **File → Open Folder**
> 3. Navigate to and select your folder

---

## Step 8: Create Your First File

Inside VS Code:
1. Look at the left panel (Explorer)
2. Click the **New File** icon (looks like a page with a `+`)
3. Name the file: `index.txt`
4. Press `Enter`

Click on the file and type:

```
Hello, this is my first file.
I am learning Git.
```

Save the file:
- **Windows:** `Ctrl + S`
- **Mac:** `Cmd + S`

---

# PART 5 — Using Git

---

## Step 9: Initialize Git in Your Project

Go back to your terminal. Make sure you are still inside `my-first-project`.

```bash
git init
```

You should see:
```
Initialized empty Git repository in .../my-first-project/.git/
```

What this did:
- Git is now watching your folder
- Every change you make can now be tracked
- A hidden folder called `.git` was created — **do not delete it** (it stores your history)

---

## Step 10: Check the Status of Your Project

```bash
git status
```

You will see something like:
```
Untracked files:
  index.txt
```

This means Git can see your file, but it is **not yet being tracked**.

> `git status` is your best friend. Run it whenever you are confused — it tells you exactly what is happening.

---

## Step 11: Stage Your File

Before saving a checkpoint, you have to tell Git **which files to include**.

This is called **staging**.

```bash
git add .
```

The `.` means "add everything in this folder".

Run `git status` again:
```
Changes to be committed:
  new file: index.txt
```

Your file is now staged — ready to be saved.

---

## Step 12: Commit (Save a Checkpoint)

Now save the checkpoint:

```bash
git commit -m "First commit - added index.txt"
```

The `-m` means "message". Always write a short message describing what you changed.

Good commit messages:
- `"Added homepage layout"`
- `"Fixed login bug"`
- `"Updated README with setup instructions"`

Bad commit messages:
- `"stuff"`
- `"asdfgh"`
- `"changes"`

You should see:
```
[main (root-commit) abc1234] First commit - added index.txt
 1 file changed, 2 insertions(+)
```

**Congratulations — you just made your first Git commit.**

---

## Understanding the 3-Step Git Flow

Every time you work, you follow this pattern:

```
1. Make changes to your files
        ↓
2. git add .         ← stage your changes
        ↓
3. git commit -m ""  ← save the checkpoint
```

This is the core of Git. Everything else builds on this.

---

# PART 6 — Connect to GitHub

---

## Step 13: Create a Repository on GitHub

1. Go to → https://github.com
2. Log in to your account
3. Click the **+** button in the top right corner
4. Click **New repository**
5. Fill in:
   - **Repository name:** `my-first-project`
   - **Description:** (optional) `My first Git project`
   - Keep it **Public** (so others can see it) or **Private** (only you)
   - **Do NOT** check "Add a README file" (we already have files)
6. Click **Create repository**

You will see a page with setup instructions. We will use the commands from that page next.

---

## Step 14: Copy Your Repository URL

On the GitHub page you just created, look for a URL that looks like this:

```
https://github.com/your-username/my-first-project.git
```

Copy this URL.

---

## Step 15: Connect Your Local Project to GitHub

In your terminal:

```bash
git remote add origin https://github.com/your-username/my-first-project.git
```

What this does:
- `remote` = a connection to an online location
- `add` = add a new connection
- `origin` = the name we give this connection (a standard name everyone uses)
- The URL = where your GitHub repo is

To confirm it worked:
```bash
git remote -v
```

You should see:
```
origin  https://github.com/your-username/my-first-project.git (fetch)
origin  https://github.com/your-username/my-first-project.git (push)
```

---

## Step 16: Push Your Code to GitHub

```bash
git branch -M main
git push -u origin main
```

Line by line:
- `git branch -M main` → renames your branch to `main` (modern standard)
- `git push -u origin main` → uploads your code to GitHub

> The first time you push, GitHub may ask you to log in. Enter your GitHub username and password.

> **Note for Windows users:** A login window may pop up automatically. Sign in with your GitHub account.

> **Note for Mac users:** You may need to use a Personal Access Token instead of your password. If GitHub rejects your password, go to: GitHub → Settings → Developer Settings → Personal Access Tokens → Generate new token. Use that token as your password.

After pushing, refresh your GitHub repository page — **your file is now online!**

---

# PART 7 — Daily Workflow

---

## Every Day, Every Change — Follow This Pattern

```bash
# 1. Make changes to your files in VS Code

# 2. See what changed
git status

# 3. Stage all changes
git add .

# 4. Save a checkpoint with a message
git commit -m "describe what you changed"

# 5. Upload to GitHub
git push
```

That's it. This is what professional developers do every single day.

---

## Step 17: Practice — Make a Change and Push It

1. Open `index.txt` in VS Code
2. Add a new line:

```
Hello, this is my first file.
I am learning Git.
Today I made my second commit.
```

3. Save the file (`Ctrl + S` or `Cmd + S`)

4. In the terminal:

```bash
git status
```

You will see:
```
modified: index.txt
```

5. Stage and commit:

```bash
git add .
git commit -m "Updated index.txt with second line"
```

6. Push to GitHub:

```bash
git push
```

7. Go to your GitHub repository and refresh the page — you will see your updated file.

---

# PART 8 — Other Useful Commands

---

## See Your Commit History

```bash
git log
```

This shows every commit you have made, with the date, author, and message.

Press `q` to exit the log.

For a shorter view:
```bash
git log --oneline
```

---

## Pull — Get the Latest Code

If you are working from a different computer, or someone else pushed changes:

```bash
git pull
```

This downloads the latest version from GitHub to your computer.

> Always `git pull` before you start working.

---

## Clone — Download a Project from GitHub

If you want to download any project from GitHub (yours or someone else's):

```bash
git clone https://github.com/username/project-name.git
cd project-name
code .
```

---

# PART 9 — Common Errors and Fixes

---

### Error: `git: command not found` or `git is not recognized`

**Cause:** Git was not installed correctly.

**Fix:** Reinstall Git from https://git-scm.com/downloads and restart your terminal.

---

### Error: `code .` does not open VS Code

**Fix on Mac:**
1. Open VS Code
2. Press `Cmd + Shift + P`
3. Type: `Shell Command: Install 'code' command in PATH`
4. Press Enter

**Fix on Windows:**
1. During VS Code installation, make sure **"Add to PATH"** was checked
2. If not, reinstall VS Code and check that option

---

### Error: `failed to push some refs`

**Cause:** GitHub has changes that your computer does not have.

**Fix:**
```bash
git pull
git push
```

---

### Error: `remote origin already exists`

**Cause:** You already added a remote connection.

**Fix:**
```bash
git remote remove origin
git remote add origin https://github.com/your-username/your-repo.git
```

---

### Error: `Please tell me who you are`

**Cause:** You skipped the Git configuration step.

**Fix:**
```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

---

# PART 10 — Full Workflow from Zero to GitHub

Here is everything together in one place:

```bash
# === SETUP (Do once) ===
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"

# === CREATE PROJECT ===
mkdir my-first-project
cd my-first-project

# === OPEN IN VS CODE ===
code .

# === START GIT ===
git init

# === (Create your files in VS Code and save them) ===

# === FIRST SAVE ===
git add .
git commit -m "First commit"

# === CONNECT TO GITHUB ===
git remote add origin https://github.com/your-username/my-first-project.git
git branch -M main
git push -u origin main

# === DAILY WORKFLOW (repeat forever) ===
# (make changes in VS Code)
git add .
git commit -m "what you changed"
git push
```

---

# PART 11 — Practice Task (Do This By Yourself)

Go through every step alone without looking at the guide:

1. Create a new folder called `practice-project`
2. Navigate into it using the terminal
3. Open it in VS Code
4. Initialize Git
5. Create a file called `notes.txt`
6. Write 3 lines of text in it
7. Stage and commit the file
8. Create a new repository on GitHub
9. Connect your local project to GitHub
10. Push your code
11. Go to GitHub and confirm your file is there
12. Edit your file — add 2 more lines
13. Stage, commit, and push again
14. Refresh GitHub — confirm the update is there

If you can complete all 14 steps without help, you have learned the fundamentals of Git.

---

# Summary — Key Concepts

| Word | Meaning |
|---|---|
| **Git** | A tool that tracks changes to your code |
| **GitHub** | A website that stores your code online |
| **Repository (repo)** | Your project folder tracked by Git |
| **Commit** | A saved checkpoint of your project |
| **Stage** | Selecting which files to include in the next commit |
| **Push** | Uploading your commits to GitHub |
| **Pull** | Downloading the latest changes from GitHub |
| **Clone** | Downloading a repository from GitHub to your computer |
| **Remote** | A connection to an online repository |
| **Origin** | The standard name for your GitHub remote |
| **Main** | The name of your primary branch |

---

# Final Advice

- **Do not memorize commands** — understand what they do, then practice
- **Run `git status` often** — it always tells you what is happening
- **Commit often** — small commits with clear messages are better than one huge commit
- **Push at the end of every work session** — your code is only backed up after you push
- **It is okay to make mistakes** — Git is designed to let you undo and recover

The only way to learn Git is to use it every day. Start with a small project and push something to GitHub today.
