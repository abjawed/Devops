# Version Control System Using GIT

**GitHub**: An open-source remote source code management tool.

- **Repository**: A collection of folders and files, below are the some popular repository
  - [GitHub](www.github.com)
  - Azure Repos
  - Bitbucket
  - AWS CodeCommit
  - GitLab

## Version Control System (VCS)

- Used to version control the source code.
- Tracks source code changes.

### Developer Workflow Example

1. Initial file:
    ```html
    <html>
    func1
    ---
    ---
    --
    -
    -
    --
    --
    </html>
    ```
   Save as `mywebapp.html`.

2. After modifications:
    ```html
    <html>
    func1
    ---
    ---
    --
    Welcome
    -
    --
    --
    To 
    The 
    Devops
    func2
    Hello 
    Devops World!
    </html>
    ```
   Save as `mywebapp.html`.

3. Versions saved:
    - `mywebapp.html_v1.0`
    - `mywebapp.html_v1.1`
    - `mywebapp.html_v1.2`
    - `mywebapp.html_v1.3`

### Types of Version Control Systems

1. Local Version Control System
2. Centralized Version Control System
3. Distributed Version Control System

### GIT

- An open-source distributed version control system.
- Used to version control changes and track changes.
- Supports parallel development using branching techniques.

### GitHub

- An open-source remote source code management tool.
- Hosts repositories (collections of folders and files) online.
- Other similar tools: Azure Repos, Bitbucket, AWS CodeCommit, GitLab.

## Working with GIT

1. **Install GIT CLI**:
   - [Download GIT](https://git-scm.com/downloads)
   - On Windows: GIT BASH, GIT CMD, GIT GUI

2. **GIT File Workflow**:

   Local Machine | Staging Area | Local Repository | Remote Repository
   --------------|--------------|------------------|-------------------
   `mywebapp.html` | `mywebapp.html` | `mywebapp.html_v1.0` | `mywebapp.html_v1.0`
   - `git add` | - `git commit` | - `git push`

### GIT Commands

- `git init`: Initialize a local repository.
- `git clone`: Copy/clone a remote repository to the local machine.
- `git add`: Add changes from the working directory to the staging area.
- `git commit`: Commit changes from the staging area to the local repository.
- `git push`: Push changes from the local repository to the remote repository.
- `git fetch`: Check for incremental changes in the remote repository.
- `git pull`: Fetch and merge changes from the remote repository to the working directory and local repository.
- `git fork`: Copy a remote repository to another remote repository.
- `git status`: Get the current status of the repository.
- `git log`: Get the list of commits.
- `git reset`: Undo commits.
- `git revert`: Undo specific commits.
- `git config`: Configure user information.
- `git commit --amend`: Amend the commit message.
- `git ignore`: Ignore files from tracking.
- `git branch`: Manage branches.
- `git switch`: Switch branches.
- `git merge`: Merge changes from one branch to another.
- `git rebase`: Keep the current branch in sync with the target branch.
- `git stash`: Temporarily save changes without committing.

### Branching Strategies

- **Feature Branching**: Create feature branches for new features or bug fixes.
- **Release Branching**: Create release branches for preparing a release.
- **Hotfix Branching**: Create hotfix branches for urgent bug fixes in production.

### Example Branching Scenarios

1. **Scenario 1**:
    - **Master**: cm1, cm2, cm3
    - **Feature1**: cm1, cm2, cm3, f1cm1, f1cm2
    - Merge Feature1 into Master.

2. **Scenario 2**:
    - **Master**: cm1, cm2, cm3
    - **Developer Branch1**: cm1, cm2, cm3, f1cm1, f1cm2, f2cm1, f2cm2
    - Merge Feature1 and Feature2 into Developer Branch1.

3. **Scenario 3**:
    - **Master**: cm1, cm2, cm3
    - **Integration Branch**: cm1, cm2, cm3, developer1_Changes, developer2_Changes
    - Merge Developer Branch1 and Developer Branch2 into Integration Branch.

4. **Scenario 4**:
    - **Master**: cm1, cm2, cm3
    - **Release Branch**: cm1, cm2, cm3, Team1_Changes, Team2_Changes
    - Merge Integration Branch1 and Integration Branch2 into Release Branch.

### GIT Merge Conflicts

- Occurs when a file at a record level gets updated by more than one user/feature.
- Fix by identifying the conflicting file, reviewing content, deciding which changes to retain, and updating the file in the target branch.

### GIT Rebase

- Keeps the current branch in sync with the target branch.
- Maintains linear commit history.
- Recommended before merging to the target branch to avoid conflicts.

### GIT Squash

- Combine multiple commits into a single commit during merge.
- Useful for maintaining a clean commit history.

---

This guide covers the basics of working with GIT, managing repositories on GitHub, and implementing branching strategies for effective version control in development projects.
