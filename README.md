# Git Cheatsheet

# Overview of commands
* `add` adds file contents to the staging area
* `commit` records a snapshot of the staging area
* `status` view the status of your files in the working directory and staging area
* `diff` shows diff of what is staged and what is modified but unstaged
* `branch` list, create, or delete branches
* `checkout` switch branches or restore working tree files
* `pull` fetch from a remote repo and try to merge into the current branch
* `push` push your new branches and data to a remote repository
* `clone` clone a repository into a new directory
* `init` create an empty Git repository or reinitialize an existing one
* `reset` reset current HEAD to the specified state
* `merge` join two or more development histories together
* `log` show commit logs
* `help [command]` get help info about a particular command

# Add and commit a file
The first time we ask a file to be tracked, and every time before we commit a file, we must add it to the staging area:
```
git add Hello.java Goodbye.java
```
 * Takes a snapshot of these files, adds them to the staging area.
 * In older VCS, "add" means "start tracking this file." In Git, "add"
means "add to staging area" so it will be part of the next commit.

To move staged changes into the repo, we commit:
```
git commit –m "Fixing bug #22"
```

To undo changes on a file before you have committed it:
```
git reset HEAD -- filename (unstages the file)
git checkout -- filename (undoes your changes)
```
All these commands are acting on your local version of repo.

# Viewing/undoing changes
To view status of files in working directory and staging area:
```
git status
git status –s (short version)
```
To see what is modified but unstaged:
```
git diff
```
To see a list of staged changes:
```
git diff --cached
```
To see a log of all changes in your local repo:
```
git log
git log --oneline (shorter version)
git log -5 (to show only the 5 most recent updates)
```

# Branching and merging
Git uses branching heavily to switch between multiple tasks.

To create a new local branch:
```
git branch name
```
To list all local branches: (* = current branch)
```
git branch
```
To switch to a given local branch:
```
git checkout branchname
```
To merge changes from a branch into the local master:
```
git checkout master
git merge branchname
```

# Interaction w/ remote repo
To fetch the most recent updates from the remote repo into your local repo, and put them into your working directory:
```
git pull origin master
```
To put your changes from your local repo in the remote repo:
```
git push origin master
```

# Creating a repo

* Create a new local Git repo in your existing directory
```
git init
git add .
git commit -m "Initial commit"
```
* Clone a remote repo to your current directory (will create the given local directory, containing a working copy of
the files from the repo)
```
git clone url
```
# Git configuration

Set the name and email for Git to use when you commit:
```
git config --global user.name "Bugs Bunny"
git config --global user.email bugs@gmail.com
```
Set the editor that is used for writing commit messages (default vi):
```
git config --global core.editor nano
```
