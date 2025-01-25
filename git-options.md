### 1. What is the purpose of the `git init` command?  
A. To clone a repository  
B. To create a new Git repository  
C. To configure Git username and email  
D. To delete an existing repository  

**Correct Answer:** B. To create a new Git repository  
**Explanation:** The `git init` command initializes a new Git repository in the current directory.

---

### 2. Which command configures your Git username globally?  
A. `git user.name`  
B. `git config --global user.name`  
C. `git set user.name`  
D. `git global-config user.name`  

**Correct Answer:** B. `git config --global user.name`  
**Explanation:** The `--global` flag ensures the configuration applies across all repositories on your system.

---

### 3. What does the `git log` command display?  
A. A list of branches  
B. The commit history  
C. The working directory status  
D. Files staged for the next commit  

**Correct Answer:** B. The commit history  
**Explanation:** The `git log` command shows the history of commits, including their hash, author, and message.

---

### 4. How can you delete a Git branch locally?  
A. `git delete-branch`  
B. `git branch -d <branch-name>`  
C. `git remove branch <branch-name>`  
D. `git rm branch <branch-name>`  

**Correct Answer:** B. `git branch -d <branch-name>`  
**Explanation:** The `-d` option is used to safely delete a branch locally.

---

### 5. What is the difference between `git pull` and `git fetch`?  
A. `git pull` fetches and merges changes; `git fetch` only downloads changes.  
B. `git pull` only downloads changes; `git fetch` fetches and merges changes.  
C. Both perform the same function.  
D. `git pull` downloads changes without merging.  

**Correct Answer:** A. `git pull` fetches and merges changes; `git fetch` only downloads changes.  
**Explanation:** `git pull` combines `git fetch` with an automatic merge.

---

### 6. What is the function of a `.gitignore` file?  
A. To ignore all files in the repository  
B. To list files that should not be staged or committed  
C. To prevent repository deletion  
D. To restrict access to the repository  

**Correct Answer:** B. To list files that should not be staged or committed  
**Explanation:** A `.gitignore` file specifies patterns of files or directories that Git should ignore.

---

### 7. What is the purpose of the `git rebase` command?  
A. To merge branches  
B. To move a branch onto another base commit  
C. To delete commits  
D. To revert changes  

**Correct Answer:** B. To move a branch onto another base commit  
**Explanation:** Rebasing rewrites commit history to create a linear sequence of commits.

---

### 8. Which command would you use to revert changes in a specific commit?  
A. `git reset`  
B. `git revert <commit-hash>`  
C. `git undo <commit-hash>`  
D. `git checkout <commit-hash>`  

**Correct Answer:** B. `git revert <commit-hash>`  
**Explanation:** `git revert` creates a new commit that undoes the changes introduced by a specific commit.

---

### 9. How can you change the remote URL of an existing repository?  
A. `git config remote set-url`  
B. `git remote set-url <new-url>`  
C. `git change remote-url <new-url>`  
D. `git update remote-url <new-url>`  

**Correct Answer:** B. `git remote set-url <new-url>`  
**Explanation:** This command updates the remote URL for an existing repository.

---

### 10. What does the `git diff` command show?  
A. The list of all branches  
B. Differences between two commits or the working directory and index  
C. The commit history  
D. Changes in the last commit  

**Correct Answer:** B. Differences between two commits or the working directory and index  
**Explanation:** `git diff` compares changes in files, either staged or unstaged.

---

### 11. What does the `git clone` command do?  
A. Deletes a remote repository  
B. Creates a copy of a repository locally  
C. Initializes a new repository  
D. Merges two repositories  

**Correct Answer:** B. Creates a copy of a repository locally  
**Explanation:** The `git clone` command copies an existing remote repository to the local machine.

---

### 12. How can you check the status of your working directory?  
A. `git check`  
B. `git status`  
C. `git monitor`  
D. `git inspect`  

**Correct Answer:** B. `git status`  
**Explanation:** The `git status` command shows the state of the working directory and staging area.

---

### 13. Which command lists all local branches?  
A. `git branch`  
B. `git show-branches`  
C. `git list-branches`  
D. `git branches`  

**Correct Answer:** A. `git branch`  
**Explanation:** Running `git branch` without arguments lists all local branches.

---

### 14. What is the default branch in Git?  
A. `main`  
B. `master`  
C. `develop`  
D. `trunk`  

**Correct Answer:** A. `main` (or `master` for older setups)  
**Explanation:** Git now defaults to `main` for new repositories.

---

### 15. How can you merge one branch into another?  
A. `git branch-merge <branch-name>`  
B. `git merge <branch-name>`  
C. `git pull <branch-name>`  
D. `git add <branch-name>`  

**Correct Answer:** B. `git merge <branch-name>`  
**Explanation:** The `git merge` command merges the specified branch into the current branch.

---

### 16. What happens if you run `git reset --hard HEAD~1`?  
A. It stages the last commit.  
B. It removes the last commit and associated changes.  
C. It reverts the last commit.  
D. It creates a new branch from the last commit.  

**Correct Answer:** B. It removes the last commit and associated changes.  
**Explanation:** The `--hard` flag resets the commit and working directory.

---

### 17. Which of the following commands initializes a bare repository?  
A. `git init --bare`  
B. `git create bare`  
C. `git bare init`  
D. `git init bare`  

**Correct Answer:** A. `git init --bare`  
**Explanation:** The `--bare` flag initializes a repository without a working directory.

---

### 18. How do you undo the last commit without deleting the changes?  
A. `git reset --soft HEAD~1`  
B. `git revert HEAD`  
C. `git reset --hard HEAD~1`  
D. `git checkout HEAD~1`  

**Correct Answer:** A. `git reset --soft HEAD~1`  
**Explanation:** The `--soft` flag undoes the commit but retains the changes in the staging area.

---

### 19. Which command pushes all local branches to the remote repository?  
A. `git push -u origin *`  
B. `git push --all`  
C. `git push -a`  
D. `git push origin --all`  

**Correct Answer:** D. `git push origin --all`  
**Explanation:** This command ensures all local branches are pushed to the specified remote.

---

### 20. What does the `git stash` command do?  
A. Deletes uncommitted changes  
B. Temporarily saves uncommitted changes  
C. Commits changes directly  
D. Undoes the last commit  

**Correct Answer:** B. Temporarily saves uncommitted changes  
**Explanation:** The `git stash` command saves changes and restores a clean working directory.

---

### 21. How do you apply stashed changes?  
A. `git apply stash`  
B. `git restore stash`  
C. `git stash apply`  
D. `git stash push`  

**Correct Answer:** C. `git stash apply`  
**Explanation:** This command restores the most recently stashed changes.

---

### 22. Which file stores the configuration for ignoring specific file types?  
A. `.gitignore`  
B. `.config`  
C. `.gitconfig`  
D. `.gitsettings`  

**Correct Answer:** A. `.gitignore`  
**Explanation:** The `.gitignore` file defines the patterns of files or directories Git should ignore.

---

### 23. What is the purpose of `git config --global core.editor`?  
A. Sets the global Git username  
B. Sets the default text editor for Git  
C. Changes the Git repository URL  
D. Installs Git on the system  

**Correct Answer:** B. Sets the default text editor for Git  
**Explanation:** This configuration defines which editor is used for Git commit messages.

---

### 24. Which command lists the commits in reverse chronological order?  
A. `git log`  
B. `git reverse-log`  
C. `git commits-list`  
D. `git log --reverse`  

**Correct Answer:** A. `git log`  
**Explanation:** By default, `git log` lists commits starting from the most recent.

---

### 25. What does `HEAD` refer to in Git?  
A. The first commit in the repository  
B. The branch being currently worked on  
C. The latest commit of the current branch  
D. The remote repository  

**Correct Answer:** C. The latest commit of the current branch  
**Explanation:** `HEAD` points to the tip of the current branch.

---

### 26. How do you view the remote repository URL?  
A. `git remote -v`  
B. `git remote --show`  
C. `git show remote`  
D. `git config remote-url`  

**Correct Answer:** A. `git remote -v`  
**Explanation:** The `-v` option shows the remote URL(s) associated with the repository.

---

### 27. What does `git tag` do?  
A. Creates a new branch  
B. Tags specific commits for reference  
C. Removes branches  
D. Lists all branches  

**Correct Answer:** B. Tags specific commits for reference  
**Explanation:** Tags are often used to mark releases or significant commits.

---

### 28. How do you remove a remote repository?  
A. `git remove remote <name>`  
B. `git remote rm <name>`  
C. `git delete remote <name>`  
D. `git remote remove <name>`  

**Correct Answer:** B. `git remote rm <name>`  
**Explanation:** This command removes the specified remote repository.

---

### 29. Which command shows the commit history in a graphical format?  
A. `git graph`  
B. `git log --graph`  
C. `git history --graph`  
D. `git commit-graph`  

**Correct Answer:** B. `git log --graph`  
**Explanation:** This option adds an ASCII representation of the commit history.

---

### 30. How can you check the difference between the working directory and the last commit?  
A. `git diff HEAD`  
B. `git diff --staged`  
C. `git diff --last`  
D. `git compare HEAD`  

**Correct Answer:** A. `git diff HEAD`  
**Explanation:** This shows changes in the working directory compared to the latest commit.

---

### 31. What does the `git push` command do?  
A. Sends changes to the local repository  
B. Downloads changes from the remote repository  
C. Uploads changes to the remote repository  
D. Deletes a branch on the remote repository  

**Correct Answer:** C. Uploads changes to the remote repository  
**Explanation:** The `git push` command is used to send your local commits to the remote repository.

---

### 32. How do you view the differences between two branches?  
A. `git compare <branch1> <branch2>`  
B. `git diff <branch1> <branch2>`  
C. `git log <branch1> <branch2>`  
D. `git status <branch1> <branch2>`  

**Correct Answer:** B. `git diff <branch1> <branch2>`  
**Explanation:** `git diff` allows you to compare the differences between two branches.

---

### 33. How can you create a new branch in Git?  
A. `git create branch <branch-name>`  
B. `git branch <branch-name>`  
C. `git new branch <branch-name>`  
D. `git checkout -b <branch-name>`  

**Correct Answer:** B. `git branch <branch-name>`  
**Explanation:** `git branch <branch-name>` creates a new branch without switching to it.

---

### 34. What command is used to rename a local branch in Git?  
A. `git branch -m <new-name>`  
B. `git rename <new-name>`  
C. `git branch --rename <new-name>`  
D. `git switch --rename <new-name>`  

**Correct Answer:** A. `git branch -m <new-name>`  
**Explanation:** The `-m` flag renames the current branch.

---

### 35. How do you delete a remote branch in Git?  
A. `git remote delete <branch-name>`  
B. `git push origin --delete <branch-name>`  
C. `git branch -d <branch-name>`  
D. `git remove branch <branch-name>`  

**Correct Answer:** B. `git push origin --delete <branch-name>`  
**Explanation:** This command deletes the branch on the remote repository.

---

### 36. What command is used to view the commit history of a specific file?  
A. `git log <file-name>`  
B. `git history <file-name>`  
C. `git show <file-name>`  
D. `git diff <file-name>`  

**Correct Answer:** A. `git log <file-name>`  
**Explanation:** `git log <file-name>` shows the commit history for a specific file.

---

### 37. What is the purpose of `git merge --no-ff`?  
A. Forces a fast-forward merge  
B. Merges without preserving history  
C. Ensures a merge commit even if the merge could be fast-forwarded  
D. Discards the commit history during merging  

**Correct Answer:** C. Ensures a merge commit even if the merge could be fast-forwarded  
**Explanation:** The `--no-ff` option forces a merge commit even when the merge could be done as a fast-forward.

---

### 38. Which command will list all remote repositories associated with your local Git repository?  
A. `git remote list`  
B. `git remote -v`  
C. `git remote show`  
D. `git remote status`  

**Correct Answer:** B. `git remote -v`  
**Explanation:** `git remote -v` lists all remotes and their corresponding URLs.

---

### 39. What does the `git reset --soft HEAD~1` command do?  
A. It resets the commit history and moves HEAD one commit back.  
B. It moves HEAD back without changing the working directory.  
C. It undoes the last commit and deletes all changes.  
D. It removes a commit but keeps the changes staged.  

**Correct Answer:** D. It removes a commit but keeps the changes staged.  
**Explanation:** `--soft` leaves the working directory and staging area as is but removes the commit.

---

### 40. How do you view all the branches (local and remote)?  
A. `git branch --all`  
B. `git branches`  
C. `git list branches`  
D. `git show branches`  

**Correct Answer:** A. `git branch --all`  
**Explanation:** The `--all` option shows both local and remote branches.

---

### 41. What command shows the history of a specific branch?  
A. `git log <branch-name>`  
B. `git show <branch-name>`  
C. `git history <branch-name>`  
D. `git branch log <branch-name>`  

**Correct Answer:** A. `git log <branch-name>`  
**Explanation:** `git log <branch-name>` shows the commit history for that specific branch.

---

### 42. How do you check which files have been staged for commit?  
A. `git commit --staged`  
B. `git status`  
C. `git staged`  
D. `git log --staged`  

**Correct Answer:** B. `git status`  
**Explanation:** `git status` displays the files that are staged for commit.

---

### 43. What does the `git diff` command compare?  
A. The staged changes with the last commit  
B. The changes between branches  
C. The local repository with the remote repository  
D. The working directory and the staging area  

**Correct Answer:** D. The working directory and the staging area  
**Explanation:** `git diff` compares uncommitted changes between the working directory and the staging area.

---

### 44. How can you list all the Git configuration settings?  
A. `git config --list`  
B. `git config show`  
C. `git list config`  
D. `git config list --show`  

**Correct Answer:** A. `git config --list`  
**Explanation:** `git config --list` displays all the Git configuration settings.

---

### 45. How do you view the changes made in a specific commit?  
A. `git show <commit-hash>`  
B. `git log <commit-hash>`  
C. `git diff <commit-hash>`  
D. `git changes <commit-hash>`  

**Correct Answer:** A. `git show <commit-hash>`  
**Explanation:** `git show` displays the changes introduced by a specific commit.

---

### 46. What does the `git revert` command do?  
A. Undoes a commit by creating a new commit that reverses its changes  
B. Deletes a commit from history  
C. Moves a commit to a different branch  
D. Discards changes made in the working directory  

**Correct Answer:** A. Undoes a commit by creating a new commit that reverses its changes  
**Explanation:** `git revert` creates a new commit that reverses the changes made by a previous commit.

---

### 47. How can you retrieve changes from a remote repository without merging them into your branch?  
A. `git fetch`  
B. `git pull`  
C. `git sync`  
D. `git get`  

**Correct Answer:** A. `git fetch`  
**Explanation:** `git fetch` retrieves changes from the remote repository without applying them to the current branch.

---

### 48. What does `git commit --amend` do?  
A. Merges the current commit with the previous one  
B. Deletes the most recent commit  
C. Modifies the last commit by adding changes  
D. Reverts the most recent commit  

**Correct Answer:** C. Modifies the last commit by adding changes  
**Explanation:** This command allows you to amend the previous commit by adding changes to it.

---

### 49. How do you remove a file from both the staging area and the working directory?  
A. `git rm <file-name>`  
B. `git remove <file-name>`  
C. `git delete <file-name>`  
D. `git rm --staged <file-name>`  

**Correct Answer:** A. `git rm <file-name>`  
**Explanation:** `git rm` removes a file from both the staging area and the working directory.

---

### 50. What command is used to see the differences between the staged and working directory?  
A. `git diff --staged`  
B. `git status --staged`  
C. `git log --staged`  
D. `git compare --staged`  

**Correct Answer:** A. `git diff --staged`  
**Explanation:** This command shows the differences between the staged changes and the last commit.

---

### 51. How do you create a new Git repository?  
A. `git start`  
B. `git create`  
C. `git init`  
D. `git new`  

**Correct Answer:** C. `git init`  
**Explanation:** The `git init` command initializes a new Git repository in the current directory.

---

### 52. What is the difference between `git merge` and `git rebase`?  
A. `git merge` integrates two branches into one, while `git rebase` re-applies commits on top of another branch  
B. `git merge` re-applies commits, while `git rebase` integrates two branches into one  
C. Both do the same thing  
D. `git merge` is used only for remote branches, while `git rebase` is for local branches  

**Correct Answer:** A. `git merge` integrates two branches into one, while `git rebase` re-applies commits on top of another branch  
**Explanation:** Merging creates a merge commit, whereas rebasing re-applies changes from one branch onto another without creating a merge commit.

---

### 53. How do you view the current configuration for a Git repository?  
A. `git config --list`  
B. `git show config`  
C. `git config show`  
D. `git repository --config`  

**Correct Answer:** A. `git config --list`  
**Explanation:** This command lists all Git configuration settings for the repository.

---

### 54. What does `git rm --cached <file>` do?  
A. Removes a file from the working directory  
B. Removes a file from the staging area  
C. Removes a file from the repository history  
D. Removes a file from the working directory and staging area  

**Correct Answer:** B. Removes a file from the staging area  
**Explanation:** The `--cached` option removes the file from the staging area but leaves it in the working directory.

---

### 55. Which of the following commands is used to view the Git commit history in a concise format?  
A. `git log --oneline`  
B. `git show`  
C. `git history --compact`  
D. `git log --compact`  

**Correct Answer:** A. `git log --oneline`  
**Explanation:** This command displays the commit history in a one-line format, showing the commit hash and message.

---

### 56. How do you undo changes to a file that has not been committed yet?  
A. `git checkout <file>`  
B. `git reset <file>`  
C. `git clean <file>`  
D. `git revert <file>`  

**Correct Answer:** A. `git checkout <file>`  
**Explanation:** `git checkout <file>` reverts the file to the version in the last commit, discarding uncommitted changes.

---

### 57. What does `git log --graph` do?  
A. Shows the commit history in a graphical representation  
B. Compares two branches  
C. Displays the commit history in chronological order  
D. Lists all remote branches  

**Correct Answer:** A. Shows the commit history in a graphical representation  
**Explanation:** `git log --graph` adds an ASCII representation of the commit history to the output.

---

### 58. How do you list all the tags in a Git repository?  
A. `git list tags`  
B. `git tags`  
C. `git tag`  
D. `git show tags`  

**Correct Answer:** C. `git tag`  
**Explanation:** The `git tag` command lists all tags in the current repository.

---

### 59. How can you change the email address used for your commits in Git?  
A. `git config user.email "<new-email>"`  
B. `git set email "<new-email>"`  
C. `git change-email "<new-email>"`  
D. `git commit --email "<new-email>"`  

**Correct Answer:** A. `git config user.email "<new-email>"`  
**Explanation:** This command sets the email address for the current repository or globally.

---

### 60. What is the default behavior of `git pull`?  
A. It fetches and merges changes from the current branch in the remote repository  
B. It fetches and reverts changes from the remote repository  
C. It fetches and deletes changes from the remote repository  
D. It fetches and stages changes without merging  

**Correct Answer:** A. It fetches and merges changes from the current branch in the remote repository  
**Explanation:** `git pull` fetches changes from the remote and automatically merges them into the current branch.

---

### 61. How do you set a global username in Git?  
A. `git config --global username <name>`  
B. `git config user.username <name>`  
C. `git config --global user.name <name>`  
D. `git set --global user.name <name>`  

**Correct Answer:** C. `git config --global user.name <name>`  
**Explanation:** This command sets a global username for all Git repositories on the machine.

---

### 62. How can you view changes made between two commits?  
A. `git diff <commit1> <commit2>`  
B. `git log <commit1> <commit2>`  
C. `git compare <commit1> <commit2>`  
D. `git show <commit1> <commit2>`  

**Correct Answer:** A. `git diff <commit1> <commit2>`  
**Explanation:** The `git diff` command compares the differences between two commits.

---

### 63. What does `git reset --hard` do?  
A. Reverts changes in the working directory and staging area  
B. Discards the last commit  
C. Removes a specific commit  
D. Moves the HEAD to a specific commit  

**Correct Answer:** A. Reverts changes in the working directory and staging area  
**Explanation:** The `--hard` option resets the working directory and the staging area to the specified commit.

---

### 64. How do you check out a previous commit in Git?  
A. `git checkout <commit-hash>`  
B. `git reset <commit-hash>`  
C. `git revert <commit-hash>`  
D. `git move <commit-hash>`  

**Correct Answer:** A. `git checkout <commit-hash>`  
**Explanation:** This command checks out a specific commit, updating the working directory to that commit’s state.

---

### 65. How do you list all the remotes in a Git repository?  
A. `git remote list`  
B. `git remotes`  
C. `git remote show`  
D. `git remote -v`  

**Correct Answer:** D. `git remote -v`  
**Explanation:** This command lists the remotes associated with the repository and their URLs.

---

### 66. How do you change the default branch name from `master` to `main`?  
A. `git branch -m master main`  
B. `git branch --rename master main`  
C. `git config --global default-branch main`  
D. `git init --main`  

**Correct Answer:** A. `git branch -m master main`  
**Explanation:** The `-m` option renames the local branch `master` to `main`.

---

### 67. What is the function of `.gitignore` file?  
A. Stores the commit history  
B. Prevents tracking of certain files and directories  
C. Contains Git configuration settings  
D. Specifies which branches to keep  

**Correct Answer:** B. Prevents tracking of certain files and directories  
**Explanation:** The `.gitignore` file specifies files or directories that should not be tracked by Git.

---

### 68. What does the `git fetch` command do?  
A. Downloads changes from the remote repository but does not merge them  
B. Merges changes from the remote repository  
C. Deletes branches in the remote repository  
D. Lists the changes in the remote repository  

**Correct Answer:** A. Downloads changes from the remote repository but does not merge them  
**Explanation:** `git fetch` updates the local repository with changes from the remote, without applying them to the working directory.

---

### 69. How do you undo the last commit but keep the changes in your working directory?  
A. `git reset --soft HEAD~1`  
B. `git reset --hard HEAD~1`  
C. `git revert HEAD~1`  
D. `git reset --mixed HEAD~1`  

**Correct Answer:** D. `git reset --mixed HEAD~1`  
**Explanation:** This command undoes the last commit but keeps the changes in the working directory.

---

### 70. How do you create a new tag in Git?  
A. `git tag <tag-name>`  
B. `git create tag <tag-name>`  
C. `git add tag <tag-name>`  
D. `git mark tag <tag-name>`  

**Correct Answer:** A. `git tag <tag-name>`  
**Explanation:** This command creates a new tag in the repository.

---

### 71. How can you push a new tag to a remote repository?  
A. `git push <remote> <tag-name>`  
B. `git push --tags`  
C. `git push origin <tag-name>`  
D. `git push --tag <tag-name>`  

**Correct Answer:** B. `git push --tags`  
**Explanation:** The `git push --tags` command pushes all tags to the remote repository.

---

### 72. What is the purpose of the `git stash` command?  
A. It commits changes without affecting the working directory  
B. It temporarily saves changes that are not ready to be committed  
C. It deletes the current branch  
D. It reverts the last commit  

**Correct Answer:** B. It temporarily saves changes that are not ready to be committed  
**Explanation:** `git stash` allows you to save your uncommitted changes so that you can work on something else and reapply them later.

---

### 73. How can you view the changes in a specific commit?  
A. `git log <commit-hash>`  
B. `git show <commit-hash>`  
C. `git diff <commit-hash>`  
D. `git status <commit-hash>`  

**Correct Answer:** B. `git show <commit-hash>`  
**Explanation:** The `git show <commit-hash>` command displays the changes introduced in the specified commit.

---

### 74. What does `git commit --amend` do?  
A. Reverts the previous commit  
B. Allows you to modify the most recent commit  
C. Changes the author of the last commit  
D. Combines the current commit with the next one  

**Correct Answer:** B. Allows you to modify the most recent commit  
**Explanation:** `git commit --amend` lets you modify the last commit, either by changing its content or commit message.

---

### 75. How can you retrieve a deleted branch in Git?  
A. `git checkout -b <branch-name>`  
B. `git branch <branch-name>`  
C. `git reflog`  
D. `git restore <branch-name>`  

**Correct Answer:** C. `git reflog`  
**Explanation:** The `git reflog` command tracks changes to the HEAD, including deleted branches, so you can use it to recover a deleted branch.

---

### 76. What is a "detached HEAD" state in Git?  
A. A state where HEAD is not pointing to any commit  
B. A state where HEAD is pointing to a specific branch  
C. A state where HEAD is pointing to a remote repository  
D. A state where HEAD is pointing to an untracked file  

**Correct Answer:** A. A state where HEAD is not pointing to any commit  
**Explanation:** A detached HEAD state occurs when HEAD is pointing to a specific commit rather than a branch.

---

### 77. How can you list all the remotes associated with your repository?  
A. `git remote show`  
B. `git remotes`  
C. `git remote list`  
D. `git remote -v`  

**Correct Answer:** D. `git remote -v`  
**Explanation:** `git remote -v` lists all remote repositories and their corresponding URLs.

---

### 78. How do you apply stashed changes in Git?  
A. `git stash pop`  
B. `git stash apply`  
C. `git stash bring`  
D. `git apply stash`  

**Correct Answer:** A. `git stash pop`  
**Explanation:** `git stash pop` restores the most recent stashed changes and removes them from the stash list.

---

### 79. What does `git fetch` do?  
A. Updates the working directory with changes from the remote repository  
B. Downloads changes from the remote repository but does not merge them  
C. Merges changes from the remote repository into the current branch  
D. Pushes changes to the remote repository  

**Correct Answer:** B. Downloads changes from the remote repository but does not merge them  
**Explanation:** `git fetch` fetches updates from the remote but does not apply them to the current branch.

---

### 80. How do you undo a commit that has already been pushed to a remote repository?  
A. `git reset --hard HEAD~1`  
B. `git push --force`  
C. `git revert <commit-hash>`  
D. `git reset --soft HEAD~1`  

**Correct Answer:** C. `git revert <commit-hash>`  
**Explanation:** `git revert <commit-hash>` creates a new commit that undoes the changes from the specified commit.

---

### 81. How do you check which branch you're currently working on?  
A. `git status`  
B. `git branch -v`  
C. `git current`  
D. `git show branch`  

**Correct Answer:** A. `git status`  
**Explanation:** `git status` shows the current branch you're working on in addition to the status of files.

---

### 82. What does the `git clean` command do?  
A. Cleans up the commit history  
B. Removes untracked files from the working directory  
C. Reverts changes made in the working directory  
D. Deletes the Git repository  

**Correct Answer:** B. Removes untracked files from the working directory  
**Explanation:** `git clean` removes files that are not tracked by Git, which can help clear up unnecessary files.

---

### 83. What is the purpose of `git diff`?  
A. It compares changes between commits  
B. It shows the differences between the working directory and the staging area  
C. It shows the changes in a branch  
D. It compares changes between remote repositories  

**Correct Answer:** B. It shows the differences between the working directory and the staging area  
**Explanation:** `git diff` compares uncommitted changes in the working directory to the staging area.

---

### 84. How do you list all the branches in a Git repository?  
A. `git branches`  
B. `git list branches`  
C. `git branch`  
D. `git show branches`  

**Correct Answer:** C. `git branch`  
**Explanation:** The `git branch` command lists all local branches in the repository.

---

### 85. What does the `git cherry-pick` command do?  
A. Applies a commit from another branch to the current branch  
B. Creates a new branch with specific commits  
C. Deletes a commit from the history  
D. Merges two branches together  

**Correct Answer:** A. Applies a commit from another branch to the current branch  
**Explanation:** `git cherry-pick` is used to apply the changes from a specific commit from another branch to the current branch.

---

### 86. How do you delete a local branch in Git?  
A. `git remove <branch-name>`  
B. `git delete branch <branch-name>`  
C. `git branch -d <branch-name>`  
D. `git branch --delete <branch-name>`  

**Correct Answer:** C. `git branch -d <branch-name>`  
**Explanation:** `git branch -d <branch-name>` deletes a local branch in the repository.

---

### 87. How do you merge a feature branch into the main branch?  
A. `git merge main`  
B. `git merge <feature-branch>`  
C. `git branch merge <feature-branch>`  
D. `git pull <feature-branch>`  

**Correct Answer:** B. `git merge <feature-branch>`  
**Explanation:** You merge the feature branch into the main branch by switching to the main branch and running `git merge <feature-branch>`.

---

### 88. What does `git pull --rebase` do?  
A. Reverts changes in the current branch  
B. Fetches changes from the remote repository and re-applies local changes on top  
C. Merges changes from the remote repository  
D. Fetches and merges changes from the remote repository  

**Correct Answer:** B. Fetches changes from the remote repository and re-applies local changes on top  
**Explanation:** `git pull --rebase` fetches remote changes and re-applies your local commits on top of them, avoiding a merge commit.

---

### 89. How do you show the difference between two branches?  
A. `git diff <branch1> <branch2>`  
B. `git log <branch1> <branch2>`  
C. `git compare <branch1> <branch2>`  
D. `git branch diff <branch1> <branch2>`  

**Correct Answer:** A. `git diff <branch1> <branch2>`  
**Explanation:** `git diff <branch1> <branch2>` shows the differences between two branches.

---

### 90. How do you fetch and merge the latest changes from the main branch into your current branch?  
A. `git pull origin main`  
B. `git fetch`  
C. `git merge main`  
D. `git fetch origin main`  

**Correct Answer:** A. `git pull origin main`  
**Explanation:** `git pull origin main` fetches and merges the latest changes from the remote main branch into your current branch.

---

### 91. How do you create a new branch and switch to it in one command?  
A. `git branch <branch-name> && git checkout <branch-name>`  
B. `git create <branch-name>`  
C. `git checkout -b <branch-name>`  
D. `git switch <branch-name>`  

**Correct Answer:** C. `git checkout -b <branch-name>`  
**Explanation:** The `git checkout -b <branch-name>` command creates a new branch and switches to it in a single step.

---

### 92. How can you remove a file from Git's tracking but not delete it from your local directory?  
A. `git rm <file-name>`  
B. `git rm --cached <file-name>`  
C. `git ignore <file-name>`  
D. `git untrack <file-name>`  

**Correct Answer:** B. `git rm --cached <file-name>`  
**Explanation:** The `--cached` option removes the file from Git's index (staging area) but keeps it in the local directory.

---

### 93. What does `git reset --soft HEAD~1` do?  
A. It discards the last commit and the changes in the working directory  
B. It moves the HEAD to the previous commit but keeps the changes staged  
C. It reverts the last commit and removes it from the history  
D. It moves the HEAD to the previous commit without affecting the working directory  

**Correct Answer:** B. It moves the HEAD to the previous commit but keeps the changes staged  
**Explanation:** The `--soft` option moves the HEAD pointer to the specified commit but leaves the changes staged for the next commit.

---

### 94. How do you check the status of a file in Git?  
A. `git status <file-name>`  
B. `git file-status <file-name>`  
C. `git show <file-name>`  
D. `git diff <file-name>`  

**Correct Answer:** A. `git status <file-name>`  
**Explanation:** `git status` shows the state of files in the working directory and staging area, including changes not yet staged or committed.

---

### 95. How do you remove all untracked files from the working directory?  
A. `git reset --clean`  
B. `git clean -f`  
C. `git prune -f`  
D. `git discard --untracked`  

**Correct Answer:** B. `git clean -f`  
**Explanation:** The `git clean -f` command removes untracked files from the working directory.

---

### 96. What is the purpose of `git commit --amend`?  
A. To modify the commit message of the most recent commit  
B. To discard the most recent commit  
C. To merge the current commit with the previous one  
D. To delete the last commit from the history  

**Correct Answer:** A. To modify the commit message of the most recent commit  
**Explanation:** The `git commit --amend` command allows you to change the message of the last commit.

---

### 97. How do you discard all local changes in the working directory?  
A. `git reset --hard`  
B. `git reset --mixed`  
C. `git restore --all`  
D. `git restore --discard`  

**Correct Answer:** A. `git reset --hard`  
**Explanation:** The `git reset --hard` command discards all local changes, including both staged and unstaged changes, and resets the working directory to the last commit.

---

### 98. How do you view the differences between two commits?  
A. `git diff <commit1> <commit2>`  
B. `git compare <commit1> <commit2>`  
C. `git log <commit1> <commit2>`  
D. `git show <commit1> <commit2>`  

**Correct Answer:** A. `git diff <commit1> <commit2>`  
**Explanation:** `git diff <commit1> <commit2>` compares two commits and shows the differences between them.

---

### 99. How do you create a remote branch in Git?  
A. `git branch <branch-name> --remote`  
B. `git push origin <branch-name>`  
C. `git remote add <branch-name>`  
D. `git remote branch <branch-name>`  

**Correct Answer:** B. `git push origin <branch-name>`  
**Explanation:** To create a remote branch, you first push the local branch to the remote repository using `git push origin <branch-name>`.

---

### 100. How do you merge the `feature` branch into the `develop` branch?  
A. `git merge feature develop`  
B. `git merge develop feature`  
C. `git checkout develop && git merge feature`  
D. `git checkout feature && git merge develop`  

**Correct Answer:** C. `git checkout develop && git merge feature`  
**Explanation:** To merge the `feature` branch into `develop`, you first checkout the `develop` branch and then run `git merge feature`.

---

### 101. What command is used to list all remote repositories associated with the local repository?  
A. `git remote show`  
B. `git remote -v`  
C. `git list remotes`  
D. `git remote list`  

**Correct Answer:** B. `git remote -v`  
**Explanation:** `git remote -v` shows the URLs of all remotes associated with the repository.

---

### 102. How can you resolve conflicts when merging two branches?  
A. Manually edit the conflicting files and then commit  
B. Use `git merge --resolve`  
C. Use `git reset` to discard changes  
D. Automatically accept the changes from one branch  

**Correct Answer:** A. Manually edit the conflicting files and then commit  
**Explanation:** When there are merge conflicts, you must manually edit the conflicting files, resolve the conflict, and commit the changes.

---

### 103. How do you clone a repository with a specific branch from GitHub?  
A. `git clone -b <branch-name> <repo-url>`  
B. `git fetch -b <branch-name> <repo-url>`  
C. `git clone <repo-url> --branch <branch-name>`  
D. `git clone --branch <branch-name> <repo-url>`  

**Correct Answer:** A. `git clone -b <branch-name> <repo-url>`  
**Explanation:** The `-b` option in `git clone` specifies the branch you want to clone.

---

### 104. How do you rename a Git branch locally?  
A. `git branch rename <new-name>`  
B. `git rename <old-name> <new-name>`  
C. `git branch -m <new-name>`  
D. `git checkout -b <new-name>`  

**Correct Answer:** C. `git branch -m <new-name>`  
**Explanation:** The `git branch -m` command allows you to rename the current branch or another branch to a new name.

---

### 105. What does the `git pull` command do?  
A. Fetches changes from the remote and merges them into the local branch  
B. Only fetches changes without merging them  
C. Merges two branches locally without fetching changes  
D. Pushes the local changes to the remote repository  

**Correct Answer:** A. Fetches changes from the remote and merges them into the local branch  
**Explanation:** `git pull` fetches changes from the remote repository and merges them into the current branch.

---

### 106. How do you remove a tag from the remote repository?  
A. `git tag -d <tag-name>`  
B. `git remove <tag-name>`  
C. `git push --delete origin <tag-name>`  
D. `git push origin --remove <tag-name>`  

**Correct Answer:** C. `git push --delete origin <tag-name>`  
**Explanation:** To remove a tag from the remote, use `git push --delete origin <tag-name>`.

---

### 107. How do you show the changes in a specific commit compared to the previous commit?  
A. `git diff HEAD~1 <commit-hash>`  
B. `git show <commit-hash>`  
C. `git diff <commit-hash> HEAD~1`  
D. `git log --show <commit-hash>`  

**Correct Answer:** B. `git show <commit-hash>`  
**Explanation:** `git show <commit-hash>` displays the changes made in the specified commit compared to its parent.

---

### 108. What is the purpose of the `.gitignore` file?  
A. To specify files to be tracked by Git  
B. To exclude files from being staged  
C. To specify files that should not be tracked by Git  
D. To list files that should be committed  

**Correct Answer:** C. To specify files that should not be tracked by Git  
**Explanation:** The `.gitignore` file tells Git which files and directories to ignore and not track.

---

### 109. How do you undo the last commit but keep the changes in your working directory?  
A. `git reset --hard HEAD~1`  
B. `git reset --soft HEAD~1`  
C. `git revert HEAD~1`  
D. `git reset --mixed HEAD~1`  

**Correct Answer:** D. `git reset --mixed HEAD~1`  
**Explanation:** `git reset --mixed HEAD~1` removes the last commit but keeps the changes in your working directory for further edits.

---

### 110. How do you switch to a different branch in Git?  
A. `git switch <branch-name>`  
B. `git checkout <branch-name>`  
C. `git branch switch <branch-name>`  
D. Both A and B  

**Correct Answer:** D. Both A and B  
**Explanation:** Both `git switch <branch-name>` and `git checkout <branch-name>` can be used to switch branches.

---

### 111. What does `git diff` compare?  
A. The differences between two commits  
B. The differences between the working directory and the staging area  
C. The differences between branches  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** `git diff` compares various states of the repository, including the working directory, staging area, and between commits.

---

### 112. How do you discard uncommitted changes in a file?  
A. `git discard <file-name>`  
B. `git reset <file-name>`  
C. `git checkout -- <file-name>`  
D. `git clean <file-name>`  

**Correct Answer:** C. `git checkout -- <file-name>`  
**Explanation:** `git checkout -- <file-name>` discards uncommitted changes in a specific file, restoring it to the state of the last commit.

---

### 113. How do you create a new Git repository in an existing directory?  
A. `git init`  
B. `git create`  
C. `git clone`  
D. `git start`  

**Correct Answer:** A. `git init`  
**Explanation:** `git init` initializes a new Git repository in the current directory.

---

### 114. What command is used to check the commit history?  
A. `git history`  
B. `git log`  
C. `git show log`  
D. `git commit --history`  

**Correct Answer:** B. `git log`  
**Explanation:** `git log` shows the commit history of the current branch.

---

### 115. How do you find out which files have been modified between two commits?  
A. `git diff <commit1> <commit2>`  
B. `git diff <commit1>.. <commit2>`  
C. `git compare <commit1> <commit2>`  
D. `git status <commit1> <commit2>`  

**Correct Answer:** A. `git diff <commit1> <commit2>`  
**Explanation:** `git diff <commit1> <commit2>` compares two commits and shows the differences, including modified files.

---

### 116. What is the default behavior of `git reset`?  
A. It moves the HEAD pointer to the specified commit without changing the working directory  
B. It moves the HEAD pointer and updates the working directory to match the commit  
C. It moves the HEAD pointer and keeps the changes staged  
D. It deletes the last commit  

**Correct Answer:** A. It moves the HEAD pointer to the specified commit without changing the working directory  
**Explanation:** The default `git reset` (`git reset --mixed`) moves the HEAD pointer but leaves the working directory unchanged.

---

### 117. How do you fetch all branches from a remote repository?  
A. `git fetch origin`  
B. `git pull --all`  
C. `git fetch --all`  
D. `git pull origin --all`  

**Correct Answer:** C. `git fetch --all`  
**Explanation:** `git fetch --all` fetches all branches and tags from all remotes.

---

### 118. What does `git remote -v` do?  
A. Lists all remote repositories and their associated URLs  
B. Lists all tracked branches  
C. Verifies the status of the remote repository  
D. Displays the current branch name  

**Correct Answer:** A. Lists all remote repositories and their associated URLs  
**Explanation:** `git remote -v` displays the URLs of all remotes associated with the repository.

---

### 119. How do you get information about a specific remote in Git?  
A. `git remote show <remote-name>`  
B. `git info <remote-name>`  
C. `git remote -v <remote-name>`  
D. `git show remote <remote-name>`  

**Correct Answer:** A. `git remote show <remote-name>`  
**Explanation:** `git remote show <remote-name>` displays detailed information about a specific remote, such as the branches it tracks.

---

### 120. How do you delete a remote branch in Git?  
A. `git branch -d <branch-name>`  
B. `git push origin --delete <branch-name>`  
C. `git remote delete <branch-name>`  
D. `git remove --remote <branch-name>`  

**Correct Answer:** B. `git push origin --delete <branch-name>`  
**Explanation:** To delete a remote branch, use `git push origin --delete <branch-name>`.

---

### 121. How do you rebase your current branch onto another branch?  
A. `git rebase <branch-name>`  
B. `git merge <branch-name>`  
C. `git rebase onto <branch-name>`  
D. `git pull --rebase <branch-name>`  

**Correct Answer:** A. `git rebase <branch-name>`  
**Explanation:** `git rebase <branch-name>` applies your current branch’s changes on top of the specified branch.

---

### 122. How do you remove a file from the Git index without deleting it from the working directory?  
A. `git rm --cached <file-name>`  
B. `git rm <file-name>`  
C. `git reset <file-name>`  
D. `git untrack <file-name>`  

**Correct Answer:** A. `git rm --cached <file-name>`  
**Explanation:** `git rm --cached` removes a file from Git’s staging area without deleting it from the local working directory.

---

### 123. What does the command `git show` display?  
A. The commit history of the current branch  
B. The differences between two commits  
C. The content of a specific commit  
D. The status of the working directory  

**Correct Answer:** C. The content of a specific commit  
**Explanation:** `git show` displays detailed information about a commit, including changes made and metadata such as the author and date.

---

### 124. What is the default behavior of `git merge`?  
A. It creates a new commit that combines changes from the merged branches  
B. It overwrites the current branch with changes from the merged branch  
C. It applies changes from the merged branch directly to the working directory  
D. It updates the current branch without committing  

**Correct Answer:** A. It creates a new commit that combines changes from the merged branches  
**Explanation:** `git merge` creates a merge commit that combines the histories of the two branches.

---

### 125. How do you list all the commits in a Git repository?  
A. `git log`  
B. `git history`  
C. `git show`  
D. `git list commits`  

**Correct Answer:** A. `git log`  
**Explanation:** `git log` lists all commits in the current branch, showing the commit hash, author, date, and message.

---

### 126. How do you resolve a merge conflict during a merge?  
A. Use `git pull --conflict`  
B. Manually edit the conflicting files, then commit the changes  
C. Use `git merge --abort`  
D. Use `git merge --resolve`  

**Correct Answer:** B. Manually edit the conflicting files, then commit the changes  
**Explanation:** After a merge conflict, you need to manually resolve the conflicts in the affected files and then commit the changes.

---

### 127. How do you view the changes made in the working directory compared to the last commit?  
A. `git diff`  
B. `git log`  
C. `git show`  
D. `git status`  

**Correct Answer:** A. `git diff`  
**Explanation:** `git diff` shows the differences between the working directory and the last commit.

---

### 128. What is the purpose of `git pull --rebase`?  
A. To fetch and merge changes from the remote repository  
B. To fetch changes and rebase the current branch on top of the remote branch  
C. To pull only new commits from the remote  
D. To merge remote changes without checking out the branch  

**Correct Answer:** B. To fetch changes and rebase the current branch on top of the remote branch  
**Explanation:** `git pull --rebase` fetches the changes and applies your local commits on top of the updated remote branch, avoiding a merge commit.

---

### 129. What does the `git reset --hard` command do?  
A. Resets the repository to the last commit and deletes all local changes  
B. Removes the last commit but keeps the working directory changes  
C. Moves the HEAD to the previous commit but leaves the working directory unchanged  
D. Removes all changes from the working directory but keeps the commits  

**Correct Answer:** A. Resets the repository to the last commit and deletes all local changes  
**Explanation:** `git reset --hard` resets the repository to the last commit, discarding all local changes, both staged and unstaged.

---

### 130. What does the `git fetch` command do?  
A. Downloads changes from the remote repository but does not merge them  
B. Downloads and merges changes from the remote repository  
C. Downloads new branches but does not merge them  
D. Downloads and commits changes automatically  

**Correct Answer:** A. Downloads changes from the remote repository but does not merge them  
**Explanation:** `git fetch` retrieves changes from the remote repository but does not automatically merge them into the current branch.

---

### 131. What is the purpose of the `git diff` command?  
A. To show changes between commits  
B. To compare the current working directory with the index  
C. To compare the current branch with another branch  
D. All of the above  

**Correct Answer:** D. All of the above  
**Explanation:** `git diff` shows differences in various contexts, such as between commits, between the working directory and index, or between branches.

---

### 132. How can you view the commit history of a specific file?  
A. `git log <file-name>`  
B. `git history <file-name>`  
C. `git show <file-name>`  
D. `git status <file-name>`  

**Correct Answer:** A. `git log <file-name>`  
**Explanation:** `git log <file-name>` shows the commit history of a specific file, including changes made to it.

---

### 133. How do you delete a local branch in Git?  
A. `git branch delete <branch-name>`  
B. `git branch -d <branch-name>`  
C. `git remove <branch-name>`  
D. `git delete <branch-name>`  

**Correct Answer:** B. `git branch -d <branch-name>`  
**Explanation:** `git branch -d <branch-name>` deletes a local branch, but it prevents deletion if the branch has unmerged changes.

---

### 134. How do you create a new Git tag?  
A. `git create tag <tag-name>`  
B. `git tag <tag-name>`  
C. `git add tag <tag-name>`  
D. `git new tag <tag-name>`  

**Correct Answer:** B. `git tag <tag-name>`  
**Explanation:** `git tag <tag-name>` creates a new tag pointing to the current commit.

---

### 135. How can you find which branch is currently checked out in Git?  
A. `git branch`  
B. `git status`  
C. `git log`  
D. `git branch -v`  

**Correct Answer:** A. `git branch`  
**Explanation:** `git branch` lists all local branches and highlights the currently checked-out branch.

---

### 136. How do you retrieve the latest changes from the remote repository?  
A. `git fetch origin`  
B. `git pull origin`  
C. `git update`  
D. `git refresh`  

**Correct Answer:** B. `git pull origin`  
**Explanation:** `git pull origin` retrieves the latest changes from the specified remote repository and merges them into the current branch.

---

### 137. How do you push changes to a remote repository in Git?  
A. `git upload`  
B. `git push`  
C. `git send`  
D. `git commit`  

**Correct Answer:** B. `git push`  
**Explanation:** `git push` is used to upload local commits to a remote repository.

---

### 138. How can you show the changes between your working directory and the index?  
A. `git diff`  
B. `git status`  
C. `git diff --cached`  
D. `git log`  

**Correct Answer:** A. `git diff`  
**Explanation:** `git diff` shows the differences between your working directory and the index (staging area).

---

### 139. What command is used to apply changes from a patch file in Git?  
A. `git apply`  
B. `git patch`  
C. `git diff`  
D. `git commit`  

**Correct Answer:** A. `git apply`  
**Explanation:** `git apply` applies changes from a patch file to the working directory.

---

### 140. How can you track a new file in Git after creating it?  
A. `git add <file-name>`  
B. `git track <file-name>`  
C. `git commit <file-name>`  
D. `git status <file-name>`  

**Correct Answer:** A. `git add <file-name>`  
**Explanation:** `git add <file-name>` stages a new file, making it ready for committing.

---

### 141. What does the command `git status` show?  
A. The status of the remote repository  
B. The list of all commits in the branch  
C. The current branch, staged changes, and untracked files  
D. The last commit made  

**Correct Answer:** C. The current branch, staged changes, and untracked files  
**Explanation:** `git status` shows the current branch, files that are staged for commit, files that are modified but not staged, and untracked files.

---

### 142. How do you view the changes made in a specific commit?  
A. `git diff <commit-hash>`  
B. `git log <commit-hash>`  
C. `git show <commit-hash>`  
D. `git show --changes <commit-hash>`  

**Correct Answer:** C. `git show <commit-hash>`  
**Explanation:** `git show <commit-hash>` shows detailed information about a specific commit, including changes and commit metadata.

---

### 143. What is the purpose of `git merge --no-ff`?  
A. To merge the branches but discard the merge commit  
B. To force a fast-forward merge  
C. To merge without updating the working directory  
D. To ensure a merge commit is always created  

**Correct Answer:** D. To ensure a merge commit is always created  
**Explanation:** `git merge --no-ff` ensures that a merge commit is created even if the merge could be fast-forwarded.

---

### 144. How do you list all tags in a Git repository?  
A. `git list tags`  
B. `git tag -l`  
C. `git tags`  
D. `git show tags`  

**Correct Answer:** B. `git tag -l`  
**Explanation:** `git tag -l` lists all tags in the repository.

---

### 145. How can you see which files are staged for the next commit?  
A. `git diff`  
B. `git status`  
C. `git staged`  
D. `git show`  

**Correct Answer:** B. `git status`  
**Explanation:** `git status` shows the files that are staged for the next commit.

---

### 146. How can you merge two branches in Git?  
A. `git merge <branch-name>`  
B. `git checkout merge <branch-name>`  
C. `git rebase <branch-name>`  
D. `git join <branch-name>`  

**Correct Answer:** A. `git merge <branch-name>`  
**Explanation:** `git merge <branch-name>` merges the specified branch into the current branch.

---

### 147. What does the `git log --oneline` command do?  
A. Displays commit history in a concise format with one line per commit  
B. Displays the last commit only  
C. Lists only the branches in the repository  
D. Shows detailed commit information  

**Correct Answer:** A. Displays commit history in a concise format with one line per commit  
**Explanation:** `git log --oneline` displays the commit history in a condensed format with each commit on a single line.

---

### 148. How do you configure your Git user name and email?  
A. `git config --global user.name <name> && git config --global user.email <email>`  
B. `git set username <name>`  
C. `git config --set user.name <name> && git config --set user.email <email>`  
D. `git init username <name> && git init email <email>`  

**Correct Answer:** A. `git config --global user.name <name> && git config --global user.email <email>`  
**Explanation:** This command sets your global Git user name and email, which will be used for commits.

---

### 149. How do you rename the remote URL of a repository?  
A. `git remote rename <new-url>`  
B. `git remote set-url origin <new-url>`  
C. `git push origin rename <new-url>`  
D. `git update-url origin <new-url>`  

**Correct Answer:** B. `git remote set-url origin <new-url>`  
**Explanation:** `git remote set-url origin <new-url>` changes the URL of the remote repository.

---

### 150. How do you find out which files are tracked by Git?  
A. `git status`  
B. `git log`  
C. `git ls-files`  
D. `git tracked`  

**Correct Answer:** C. `git ls-files`  
**Explanation:** `git ls-files` lists all the files that are being tracked by Git.

---

### 151. What is the purpose of the `git diff --cached` command?  
A. Shows the difference between the last commit and the working directory  
B. Shows the difference between the staged files and the last commit  
C. Shows the difference between the working directory and the staging area  
D. Shows the files that are currently being staged  

**Correct Answer:** B. Shows the difference between the staged files and the last commit  
**Explanation:** `git diff --cached` shows changes that are staged for commit, comparing them to the last commit.

---

### 152. How do you discard changes in the staging area?  
A. `git reset <file-name>`  
B. `git checkout -- <file-name>`  
C. `git diff --cached <file-name>`  
D. `git reset --hard`  

**Correct Answer:** A. `git reset <file-name>`  
**Explanation:** `git reset <file-name>` removes the file from the staging area while keeping the changes in the working directory.

---

### 153. What is the difference between `git pull` and `git fetch`?  
A. `git pull` fetches changes from the remote repository and merges them; `git fetch` only downloads changes  
B. `git pull` updates the current branch; `git fetch` updates all branches  
C. `git pull` creates a commit; `git fetch` does not  
D. `git pull` updates the working directory; `git fetch` does not  

**Correct Answer:** A. `git pull` fetches changes from the remote repository and merges them; `git fetch` only downloads changes  
**Explanation:** `git pull` combines both `git fetch` and `git merge`, while `git fetch` only retrieves the changes without applying them.

---

### 154. How do you restore a deleted file in Git?  
A. `git reset --hard <commit-hash>`  
B. `git checkout <commit-hash> <file-name>`  
C. `git restore <file-name>`  
D. `git revert <commit-hash>`  

**Correct Answer:** B. `git checkout <commit-hash> <file-name>`  
**Explanation:** `git checkout <commit-hash> <file-name>` restores a deleted file from a specific commit.

---

### 155. What does the `git log --graph` command do?  
A. Shows a visual representation of the commit history  
B. Lists only merged commits  
C. Shows the commit details  
D. Displays the changes made in each commit  

**Correct Answer:** A. Shows a visual representation of the commit history  
**Explanation:** `git log --graph` displays the commit history with a graphical representation of the branch structure.

---

### 156. How do you push changes to a specific branch in Git?  
A. `git push <branch-name>`  
B. `git push origin <branch-name>`  
C. `git push --branch <branch-name>`  
D. `git push branch <branch-name>`  

**Correct Answer:** B. `git push origin <branch-name>`  
**Explanation:** `git push origin <branch-name>` pushes the changes in the current branch to the specified remote branch.

---

### 157. How do you merge the latest changes from the `main` branch into your current branch?  
A. `git merge main`  
B. `git fetch main`  
C. `git pull origin main`  
D. `git rebase main`  

**Correct Answer:** C. `git pull origin main`  
**Explanation:** `git pull origin main` fetches and merges the latest changes from the `main` branch into your current branch.

---

### 158. How can you undo a commit that hasn't been pushed to the remote repository?  
A. `git revert`  
B. `git reset --hard`  
C. `git reset --soft`  
D. `git checkout <commit-hash>`  

**Correct Answer:** C. `git reset --soft`  
**Explanation:** `git reset --soft` undoes the last commit but keeps changes in the staging area, so you can make adjustments before recommitting.

---

### 159. How do you view the differences between two commits in Git?  
A. `git diff <commit-hash-1> <commit-hash-2>`  
B. `git compare <commit-hash-1> <commit-hash-2>`  
C. `git log <commit-hash-1> <commit-hash-2>`  
D. `git diff --commits <commit-hash-1> <commit-hash-2>`  

**Correct Answer:** A. `git diff <commit-hash-1> <commit-hash-2>`  
**Explanation:** `git diff <commit-hash-1> <commit-hash-2>` shows the differences between two specific commits.

---

### 160. What is the purpose of the `.gitignore` file?  
A. To list files and directories that should be ignored by Git  
B. To store Git configuration settings  
C. To track all files in the repository  
D. To list files that should be committed  

**Correct Answer:** A. To list files and directories that should be ignored by Git  
**Explanation:** The `.gitignore` file specifies which files and directories should not be tracked by Git.
