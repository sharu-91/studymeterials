# Git and GitHub CLI Commands

## GitHub CLI (`gh`) Commands

- `gh auth switch`  
  Switch between GitHub users.
- `gh repo create <reponame>`  
  Create a new repository on GitHub.
- `gh auth status`  
  Check which user is currently authenticated.
- `gh repo clone <reponame>`  
  Clone a repository from GitHub.
- `gh pr create`  
  Create a pull request.
- `gh pr status`  
  View pull request status.
- `gh issue list`  
  List issues in the repository.

## Git Commands for basic git operations.

- `git config --global user.name "<username>"`  
  Set the global username for Git (run once per machine).
- `git config --global user.email "<useremail>"`  
  Set the global email for Git (run once per machine).
- `git init`  
  Initialize a new Git repository in the current directory.
- `git add .`  
  Stage all changes in the current directory for commit.
- `git commit -m "<commit message>"`  
  Commit staged changes with a message.
- `git checkout -b <branchname>`  
  Create and switch to a new branch.
- `git push origin <branchname>`  
  Push the branch to the remote repository.
- `git stash`  
  Stash local changes for later use.
- `git stash pop`  
  Apply stashed changes and remove them from the stash list.

  ### Checking Differences
  - `git diff`  
    Show unstaged changes between your working directory and the index.
  - `git diff --staged`  
    Show changes between the index and the last commit (what will be committed).
  - `git diff <branch1> <branch2>`  
    Show differences between two branches.

  ### Resolving Merge Conflicts
  - `git status`  
    Show files with conflicts after a merge attempt.
  - `git diff`  
    Show conflict markers in files.
  - Edit conflicted files to resolve conflicts, then:
      - `git add <filename>`  
        Mark the conflict as resolved for a file.
  - `git commit`  
    Commit the merge after resolving all conflicts.
  - `git merge --abort`  
    Abort the merge and return to the pre-merge state (if you want to cancel the merge).

---

**Note:**
- Replace `<username>`, `<useremail>`, `<reponame>`, `<branchname>`, and `<commit message>` with your actual values.
- Some commands in the original file were corrected for syntax and clarity.
