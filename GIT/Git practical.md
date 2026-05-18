# Git Practical Guide

## 1. Restoring from GitHub (Backup)

If your laptop crashes or is lost, your code is safe on GitHub and you can restore it anytime.

**Q: How do you restore code? Is `git pull` the command?**

Yes. If you are on a new machine:

```bash
git clone <repo-url>   # gets the entire repo
git checkout features/weekly-savings  # switch to your branch
```

---

## 2. Teammate Collaboration Without Merging to `main`

Teammates can see your branch, review your code, and work on it together without needing access to your machine.

**Q: Can a teammate make changes without the code being merged to `main`? How do you merge it later? Do merge conflicts occur at this stage?**

Yes, teammates can pull your branch and make changes without it being in `main`:

```bash
git checkout features/weekly-savings
git pull origin features/weekly-savings
```

To merge later, open a **Pull Request (PR)** on GitHub, get it reviewed, then merge.

Merge conflicts happen when two people edit the **same lines in the same file**. Git cannot decide which change to keep, so it asks you to resolve it manually.

---

## 3. How Often Should You Push?

Every push is tracked with a commit history, so you can always go back to a previous version if something breaks.

**Q: Is it good practice to push code too often — after a day's work, or after switching to another task? Or is it a bad habit in terms of performance?**

Push at the end of every meaningful piece of work — end of day, after completing a feature, or before switching tasks. This is **good practice**, not bad. It protects your work and keeps the remote up to date. There is **no performance penalty** — pushing frequently is encouraged.

> **In short:** Local commits save your work on your machine, but pushing is what makes it permanent and shareable on the remote server (GitHub).

---

## 4. First Push of a New Branch

If `git push` fails with:

```
fatal: The current branch features/weekly-savings has no upstream branch.
To push the current branch and set the remote as upstream, use
    git push --set-upstream origin features/weekly-savings
```

**Q: What does "no upstream branch" mean?**

It means your local branch doesn't have a corresponding branch on GitHub (remote) yet, so Git doesn't know where to push it. Fix it with:

```bash
git push --set-upstream origin features/weekly-savings
```

After this first push, future `git push` commands on this branch will work automatically.

---

## 5. Going Back to a Previous Commit

**Q: What is the command to go back to my commit and start working from there?**

First, find the commit you want:

```bash
git log --oneline
```

Then check it out:

```bash
git checkout <commit-hash>    # view that state
```

Or to reset your branch back to that commit:

```bash
git reset --hard <commit-hash>   # WARNING: discards changes after that commit
```

The safer option, if you just want to undo recent changes, is:

```bash
git revert <commit-hash>   # creates a new commit that undoes it, keeps history intact
```
