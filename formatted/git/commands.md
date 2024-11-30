# Git

## `git init`
**Definition:** Initializes a new Git repository in your project directory. This creates a `.git` folder where Git stores all its data.  
**Example:**  
```bash
git init # Initializes a Git repository in the current directory.
```


## `git clone`
**Definition:** Creates a copy of an existing repository from a remote source (e.g., GitHub) to your local machine. 
**Example:**  
```bash
git clone <repository-url> # Clones the repository from the URL to your local machine.
```


## `git add`
**Definition:** Adds changes in the working directory to the staging area.
**Example:**  
```bash
git add <file>  # Stages the specified file.
git add .       # Stages all changes in the current directory.
```


## `git commit`
**Definition:** Records staged changes in the repository's history.
**Example:**  
```bash
git commit -m "Commit message"  # Commits changes with a descriptive message.
```


## `git status`
**Definition:** Displays the status of the working directory and staging area.
**Example:**  
```bash
git status  # Shows which files are staged, unstaged, or untracked.
```


## `git log`
**Definition:** Displays the commit history.
**Example:**  
```bash
git log          # Shows detailed commit history.
git log --oneline  # Displays commit history in a compact format.
```


## `git push`
**Definition:** Uploads committed changes from your local repository to a remote repository.
**Example:**  
```bash
git push              # Pushes changes to the default remote and branch.
git push origin <branch-name>  # Pushes changes to the specified branch on the remote repository.
```


## `git pull`
**Definition:** Fetches and merges changes from a remote repository to your local repository.
**Example:**  
```bash
git pull               # Fetches and merges changes from the default branch of the remote repository.
git pull origin <branch-name>  # Fetches and merges changes from the specified branch.
```


## `git branch`
**Definition:** Lists, creates, or deletes branches.
**Example:**  
```bash
git branch                 # Lists all branches in the repository.
git branch <branch-name>   # Creates a new branch.
git branch -d <branch-name>  # Deletes the specified branch.
```


## `git checkout`
**Definition:** Switches branches or restores working tree files.
**Example:**  
```bash
git checkout <branch-name>       # Switches to the specified branch.
git checkout -b <branch-name>    # Creates and switches to a new branch.
git checkout -- <file>           # Discards changes to the specified file in the working directory.
```


## `git merge`
**Definition:** Combines changes from different branches.
**Example:**  
```bash
git merge <branch-name>  # Merges the specified branch into the current branch.
```


## `git remote`
**Definition:** Manages connections to remote repositories.
**Example:**  
```bash
git remote                    # Lists all configured remotes.
git remote add <name> <url>   # Adds a remote with the specified name and URL.
git remote remove <name>      # Removes the specified remote.
```


## `git fetch`
**Definition:** Downloads objects and refs from a remote repository without merging.
**Example:**  
```bash
git fetch  # Downloads data from the remote repository.
```


## `git reset`
**Definition:** Resets the current HEAD to a specified state.
**Example:**  
```bash
git reset --soft <commit-hash>  # Moves HEAD to the commit, keeping changes. Use <HEAD~1> for the previous commit.
git reset --mixed <commit-hash>  # Moves HEAD to the commit, unstaging changes. Use <HEAD~1> for the previous commit.
git reset --hard <commit-hash>  # Moves HEAD to the commit, discarding changes. Use <HEAD~1> for the previous commit.
```


## `git rebase`
**Definition:** Reapplies commits on top of another base tip.
**Example:**  
```bash
git rebase <branch-name>  # Rebases the current branch onto the specified branch.
```


## `git tag`
**Definition:** Creates, lists, deletes, or verifies tags.
**Example:**  
```bash
git tag                     # Lists all tags.
git tag <tag-name>          # Creates a new tag with the specified name.
git tag -d <tag-name>       # Deletes the specified tag.
```


## `git stash`
**Definition:** Stashes changes in the working directory.
**Example:**  
```bash
git stash           # Stashes changes in the working directory.
git stash apply     # Applies the most recent stash.
git stash list      # Lists all stashes.
```


## `git diff`
**Definition:** Shows changes between commits, commit and working tree, etc.
**Example:**  
```bash
git diff                 # Shows changes between the working directory and the staging area.
git diff <commit1> <commit2>  # Shows changes between two commits.
```


## `git config`
**Definition:** Sets configuration values for Git.
**Example:**  
```bash
git config --global user.name "Your Name" # Sets the name for Git commits.
git config --global user.email "Your Email" # Sets the email for Git commits.
```


## `git rm`
**Definition:** Removes files from the working directory and staging area.
**Example:**  
```bash
git rm <file>  # Removes the specified file and stages the deletion.
```


## `git mv`
**Definition:** Moves or renames files in the working directory and staging area.
**Example:**  
```bash
git mv <old-file> <new-file>  # Renames the specified file and stages the change.
```


## `git show`
**Definition:** Shows information about a Git object (commit, tag, etc.).
**Example:**  
```bash
git show <commit>  # Shows information about the specified commit.
```


## `git cherry-pick`
**Definition:** Picks a commit from another branch and applies it to the current branch.
**Example:**  
```bash
git cherry-pick <commit-hash>  # Applies the specified commit to the current branch.
```
