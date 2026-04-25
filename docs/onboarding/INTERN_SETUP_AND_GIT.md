# Internship Onboarding

## Before You Start

You need:

- A GitHub account
- Git installed
- Node.js installed
- Bun installed
- VS Code or Cursor installed

### Check everything is installed

Open your Terminal app and run:

```bash
git --version
node --version
bun --version
```

If any command shows an error, install that tool first.

## Step 1: Make your own copy of the project (Fork)

1. Open this link: `https://github.com/mwijanarko1/My-Akhirah-Account`
2. Click the **Fork** button (top-right).
3. GitHub will create your own copy under your account.

Why this matters:

- You work in your own copy safely.
- You do not accidentally change the main project directly.

## Step 2: Download your fork to your computer (Clone)

Choose **one** of these options.

### Option A (Terminal - copy/paste)

Run this command (replace `YOUR_GITHUB_USERNAME`):

```bash
git clone https://github.com/YOUR_GITHUB_USERNAME/My-Akhirah-Account.git
cd My-Akhirah-Account
```

### Option B (Cursor or VS Code style editor)

1. Open Cursor or VS Code.
2. Open the Command Palette:
   - macOS: `Cmd + Shift + P`
   - Windows: `Ctrl + Shift + P`
3. Type: `Git: Clone` or `Clone Repository`
4. Paste your fork URL:
   - `https://github.com/YOUR_GITHUB_USERNAME/My-Akhirah-Account.git`
5. Choose a folder on your computer.
6. Click **Open** when cloning is finished.

### Option C (Create your own folder first, then ask AI)

Use this if you want full control of where files go.

1. Create a new empty folder anywhere you want (example: `My-Akhirah-Work`).
2. Open that empty folder in your editor.
3. Ask AI to clone your fork inside this folder.
4. Ask AI to move files from the cloned subfolder into the root of your folder.

Copy this prompt to your AI:

```text
I already opened an empty folder.
Please do these steps:
1) Clone this repo into this folder:
https://github.com/YOUR_GITHUB_USERNAME/My-Akhirah-Account.git
2) Move all files from the cloned folder into the current folder root (including hidden files like .gitignore).
3) Remove the now-empty cloned subfolder.
4) Confirm that README.md is in the current folder root.
```

Important:

- Run those commands only inside your new empty folder.
- After this, files should be directly in your chosen folder (not inside another nested folder).

After cloning, make sure you are inside the project folder before Step 3.

## Step 3: Connect to the main team project

Run:

```bash
git remote add upstream https://github.com/mwijanarko1/My-Akhirah-Account.git
git remote -v
```

You should see:

- `origin` (this is your fork)
- `upstream` (this is the main team project)

## Step 4: Install the project and run it

Run:

```bash
bun install
bun run dev
```

Then open: [http://localhost:3000](http://localhost:3000)

If you see the website, setup is successful.

## Step 5: Add environment file

Create a file named `.env.local` in the project root.

Copy the values shared by Mikhail on slack

Very important:

- Never share this file publicly.
- Never upload this file to GitHub.
- Never put real secret keys in chats or screenshots.

## Step 6: Create a new branch before editing

Always create a branch first.

Run:

```bash
git checkout -b feature/short-name
```

Example:

```bash
git checkout -b feature/campaign-cards
```

## Step 7: Do your work, save, and commit

After you make your changes:

```bash
git add .
git commit -m "Update campaign cards layout"
git push origin feature/campaign-cards
```

If your branch name is different, use your own branch name in the last command.

## Step 8: Open a Pull Request (PR)

1. Go to your fork on GitHub.
2. Click **Compare & pull request**.
3. Make sure:
   - Base repository = `mwijanarko1/My-Akhirah-Account`
   - Base branch = `main`
   - Compare branch = your branch
4. Add clear notes in the PR:
   - What changed
   - Why you changed it
   - How to test it
5. Add Mikhail as reviewer.

## Step 9: Simple daily routine

Every day before starting new code:

```bash
git checkout main
git fetch upstream
git pull upstream main
git push origin main
```

Then go back to your branch:

```bash
git checkout your-branch-name
git rebase main
```

If this is confusing, ask Mikhail and do not guess.

## Golden Rules (Do Not Break)

- Never push directly to `main`.
- Never commit `.env.local`.
- Never change payment/auth/Convex security logic without Mikhail review.
- Keep PRs small (one feature or one fix).
- Ask for help early.

## If Something Goes Wrong

Message Mikhail immediately if:

- Git shows conflicts you do not understand
- You are not sure which command to run
- You think you leaked a key/secret
- Your app is broken after pulling latest changes
