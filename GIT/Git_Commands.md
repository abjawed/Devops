# Git and GitHub Guide

## 1. Introduction
### 1.1 What is Git
- Git is a version control system that helps you keep track of code changes, collaborate on code, and manage different versions of your projects.

### 1.2 Why Git
- Git allows developers to work together from anywhere in the world, see the full history of a project, and revert to earlier versions if needed. Over 70% of developers use Git.

### 1.3 Features of Git
- Tracks changes in files
- Stages modified files
- Commits snapshots of staged files
- Maintains a detailed history of commits
- Allows reverting to previous commits
- Optimizes storage by tracking changes rather than storing multiple copies of files

### 1.4 What is GitHub
- GitHub is a platform that hosts Git repositories, enabling developers to collaborate on projects. It's the largest host of source code globally and has been owned by Microsoft since 2018.

## 2. Configuring Git for the First Time
```bash
$ git config --global user.name "<Enter your username here>"
$ git config --global user.email "<Enter your email here>"
```

## 3. General Git Features

### 3.1 Initializing Git
- To start tracking a project with Git, initialize a repository:
```bash
$ git init
```
### 3.2 Clone the Repository
- "Clone the repository to get a copy of the project's code on your local machine."
```bash
$ git clone
```

### 3.3 Staging Files
- To stage files for commit:
```bash
$ git add <filename>
$ git add --all
$ git add -A
```

### 3.4 Making a Commit
- To commit staged files:
```bash
$ git commit -m "<Enter your message here>"
```
- To commit changes directly, skipping the staging area:
```bash
$ git commit -a -m "<Enter your message here>"
```

### 3.5 Status of Files and Log
- To check the status of files:
```bash
$ git status
$ git status --short
```
- To view commit history:
```bash
$ git log
$ git log --oneline
```

## 4. Git Help
- For command help:
```bash
$ git <command> --help
$ git help --all
```

## 5. Git Branching

### 5.1 Making a New Git Branch
```bash
$ git branch <name of branch>
```

### 5.2 Checking All Available Branches
```bash
$ git branch
```

### 5.3 Switching to Other Branches
```bash
$ git checkout <branch name>
```

### 5.4 Making a New Branch and Directly Switching to It
```bash
$ git checkout -b <branch name>
```

### 5.5 Deleting a Branch
```bash
$ git branch -d <branch name>
```

### 5.6 Merging Two Branches
- Ensure you are on the branch you want to merge into (e.g., `master`):
```bash
$ git merge <branch name>
```

## 6. Working with GitHub

### 6.1 Push Local Repo to GitHub
- Add a remote repository and push your code:
```bash
$ git remote add origin <paste copied URL here>
$ git push --set-upstream origin master
```

### 6.2 Pull Local Repo from GitHub
```bash
$ git pull origin
```

### 6.3 Pull Branch from GitHub
```bash
$ git branch -a
$ git branch -r
$ git checkout <branch name>
$ git pull
```

### 6.4 Push Branch to GitHub
```bash
$ git checkout -b <branch name>
$ git commit -a -m "<Message>"
$ git push origin <branch name>
```

### Git Clone from GitHub
```bash
$ git clone <copied URL>
$ git clone <copied URL> <folder name>
```

## 7. Git Undo

### 7.1 Git Revert
- To revert the latest commit:
```bash
$ git revert HEAD --no-edit
```
- To revert to a specific commit:
```bash
$ git revert HEAD~x
```

### 7.2 Git Reset
- To reset the repository to a specific commit:
```bash
$ git reset <commithash>
```

### 7.3 Git Amend
- To amend the most recent commit:
```bash
$ git commit --amend -m "<Commit Message>"
```
### Git Amend Files
- Add files to the staging environment before amending:
```bash
$ git add <file>
$ git commit --amend
```

### 7.4 Git Amend
- To Show changes between working directory and staging area:
```bash
$ git diff
```


## Git Commands Overview

### Basic Commands

- **`git clone`**: Used to copy/clone the entire remote repository to a local machine.
  ```sh
  git clone <repository_url>
  ```

- **`git add`**: Adds changes from the working directory to the staging area.
  ```sh
  git add <file>
  ```

- **`git commit`**: Commits the changes from the staging area to the local repository.
  ```sh
  git commit -m "commit message"
  ```

- **`git push`**: Pushes the changes from the local repository to the remote repository.
  ```sh
  git push <remote> <branch>
  ```

### Fetching and Pulling

- **`git fetch`**: Checks for any incremental changes in the remote repository and updates only the local repository without affecting the working directory.
  ```sh
  git fetch
  ```

- **`git pull`**: Fetches and merges changes from the remote repository into the local repository and updates the working directory. Equivalent to `git fetch` + `git merge`.
  ```sh
  git pull
  ```

### Other Basic Commands

- **`fork`**: Used to copy a remote repository to another remote repository.

- **`git init`**: Initializes a new local repository.
  ```sh
  git init
  ```

### Logging

- **`git log`**: Displays the commit history.
  ```sh
  git log
  ```

- **`git log --oneline`**: Displays the commit history in a compact format.
  ```sh
  git log --oneline
  ```

- **`git log -2`**: Shows the last two commits.
  ```sh
  git log -2
  ```

- **`git log --stat -2`**: Shows the last two commits with their statistics.
  ```sh
  git log --stat -2
  ```

- **`git show <commit_id>`**: Displays detailed information about a specific commit.
  ```sh
  git show <commit_id>
  ```

### Example Workflow

```sh
# Navigate to D drive and create a project directory
cd d:
mkdir DCP-May20-Projects
cd DCP-May20-Projects/
ls

# Create and initialize two repositories
mkdir repo1
cd repo1
git init
ls -a

# Create a file and commit it
echo "record1" >> file1.txt
git add file1.txt
git commit -m "Created file1.txt"
git log

# Navigate back and create another repository
cd ..
mkdir repo2
cd repo2
git init
echo "record1" >> file1.txt
git add file1.txt
git commit -m "Created File1.txt"
git log

# Configure user details
git config --global user.name "jawed"
git config --global user.email "jawed@abcd.com"

# Create another file and commit it
echo "rec1" >> f2.txt
git add f2.txt
git commit -m "created f2.txt"
git log

# Add more files, check status, and commit them
echo "rec1" >> s1.txt
echo "rec1" >> s2.txt
echo "rec1" >> s3.txt
echo "rec1" >> a1.java
echo "rec1" >> a2.java
echo "rec1" >> a3.java
echo "rec1" >> q1.doc
echo "rec1" >> q1.md
echo "rec1" >> q2.md
git add a1.java a2.java
git add *.md
git add .
git commit -m "Created few files"
git log --oneline
```

### Reset and Revert

- **`git reset`**: Undoes changes by resetting the current branch to a specified state.
  ```sh
  git reset --soft <commit>
  git reset --mixed <commit>
  git reset --hard <commit>
  ```

- **`git revert`**: Creates a new commit that undoes the changes of a specified commit.
  ```sh
  git revert <commit>
  ```

### Ignoring Files

- **`.gitignore`**: Specifies files and directories to be ignored by Git.
  ```sh
  echo "node_modules/" >> .gitignore
  ```

### Branching and Merging

- **`git branch`**: Lists branches or creates a new branch.
  ```sh
  git branch
  git branch <branch_name>
  ```

- **`git switch`**: Switches to a specified branch.
  ```sh
  git switch <branch_name>
  ```

- **`git merge`**: Merges a specified branch into the current branch.
  ```sh
  git merge <branch_name>
  ```

- **`git rebase`**: Reapplies commits on top of another base commit.
  ```sh
  git rebase <branch>
  ```

### Example of Stashing

```sh
# Create and initialize a repository
mkdir testrepo1
cd testrepo1/
git init

# Create files, add, and commit them
echo "rec1" >> a1.txt
git add .
echo "rec1" >> a2.txt
git add .
echo "rec1" >> a3.txt
git add .
git commit -m "create txtfiles"
git log --oneline

# Make changes and stash them
echo "rec1" >> w1.txt
git add .
git stash save "created for w1.txt"

# Apply, drop, and pop stashes
git stash list
git stash apply stash@{0}
git commit -m "Created w1.txt"
git stash drop stash@{0}
git stash pop
```

### Remote Operations

```sh
# Initialize a repository, add a remote, and push
mkdir testremoterepo1
cd testremoterepo1/
git init
echo "rec1" >> l1.txt
git add .
git commit -m "created l1.txt"
git remote add origin https://github.com/Edu-DCP-May20/mytestrepo1.git
git push -u origin master

# Clone a remote repository and create a new branch
cd ..
mkdir remoterepos
cd remoterepos/
git clone https://github.com/Edu-DCP-May20/MyTestRemoteRepo1.git
cd MyTestRemoteRepo1/
git switch -c local-feature1
echo "rec1" >> localfile1.txt
git add .
git commit -m "Created local file1.txt"
git push -u origin local-feature1
```
