# Essential Git Commands Cheatsheet
git commit -am "Update file1 and remove file2"

## `git config`

*   **Description:** Configure Git settings (user name, email, editor, etc.) either globally (for all projects) or locally (for the current project).
*   **Example (Global Setup):**
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "your_email@example.com"
    ```

---

## `git init`

*   **Description:** Initializes a new, empty Git repository in the current directory or creates one in a specified new directory.
*   **Example (In current folder):**
    ```bash
    git init
    ```

---

## `git clone`

*   **Description:** Creates a local copy (clone) of a remote repository (like one from GitHub, GitLab, etc.).
*   **Example:**
    ```bash
    git clone https://github.com/user/repository.git
    ```

---

## `git status`

*   **Description:** Shows the current state of your working directory and staging area – what files are modified, staged, or untracked.
*   **Example:**
    ```bash
    git status
    ```

---

## `git add`

*   **Description:** Adds changes from the working directory to the staging area (also called the "index"), preparing them to be included in the next commit.
*   **Example (Add a specific file):**
    ```bash
    git add filename.txt
    ```
*   **Example (Add all changes in the current directory and subdirectories):**
    ```bash
    git add .
    ```

---

## `git commit`

*   **Description:** Records the changes currently in the staging area into the repository's history with a descriptive message.
*   **Example:**
    ```bash
    git commit -m "Add feature X documentation"
    ```

---

## `git log`

*   **Description:** Displays the commit history, showing commit hashes, authors, dates, and messages.
*   **Example (Basic log):**
    ```bash
    git log
    ```
*   **Example (Compact log):**
    ```bash
    git log --oneline --graph --decorate
    ```

---

## `git branch`

*   **Description:** Lists existing branches, creates new branches, or deletes branches. The current branch is marked with an asterisk (`*`).
*   **Example (List branches):**
    ```bash
    git branch
    ```
*   **Example (Create a new branch):**
    ```bash
    git branch new-feature
    ```

---

## `git checkout` (or `git switch`)

*   **Description:** Switches between branches or restores working tree files. The modern command `git switch` is preferred for *only* switching branches.
*   **Example (Switch to an existing branch):**
    ```bash
    git checkout existing-branch-name
    ```
*   **Example (Create and switch to a new branch):**
    ```bash
    git checkout -b newer-feature-branch
    ```
*   **Example (Using modern `git switch`):**
    ```bash
    # Switch to main branch
    git switch main

    # Create and switch to newest-feature
    git switch -c newest-feature
    ```

---

## `git merge`

*   **Description:** Joins two or more development histories (branches) together. Typically used to integrate changes from a feature branch into the main branch.
*   **Example (Merge 'feature-branch' into the current branch, e.g., 'main'):**
    ```bash
    # First, make sure you are on the branch you want to merge INTO
    git checkout main

    # Then, merge the other branch
    git merge feature-branch
    ```

---

## `git remote`

*   **Description:** Manage the set of tracked remote repositories. Used to view, add, or remove remote connections.
*   **Example (List remote connections):**
    ```bash
    git remote -v
    ```
*   **Example (Add a new remote named 'origin'):**
    ```bash
    git remote add origin https://github.com/user/repository.git
    ```

---

## `git fetch`

*   **Description:** Downloads commits, files, and refs from a remote repository into your local repo, but *does not* merge them into your working branch. It updates your remote-tracking branches (like `origin/main`).
*   **Example (Fetch all updates from 'origin'):**
    ```bash
    git fetch origin
    ```

---

## `git pull`

*   **Description:** Fetches changes from a remote repository *and* merges them into your current local branch. It's essentially a `git fetch` followed by a `git merge` of the corresponding remote branch.
*   **Example (Fetch and merge changes from origin's main branch into your current branch):**
    ```bash
    git pull origin main
    ```
*   **Example (Often just works if upstream is set):**
    ```bash
    git pull
    ```

---

## `git push`

*   **Description:** Uploads local repository content (commits and branches) to a remote repository.
*   **Example (Push the 'main' branch to the 'origin' remote):**
    ```bash
    git push origin main
    ```
*   **Example (Push the current branch, setting upstream tracking):**
    ```bash
    git push -u origin feature-branch
    ```

---

## `git diff`

*   **Description:** Shows changes between commits, commit and working tree, etc. By default, shows changes in the working directory that are *not yet staged*.
*   **Example (Show unstaged changes):**
    ```bash
    git diff
    ```
*   **Example (Show staged changes - changes added but not committed):**
    ```bash
    git diff --staged
    ```

---


You can copy and paste this directly into a file named README.md. It uses Markdown headings (#, ##), bullet points (*), bold text (**Description:**), and fenced code blocks (bash ...) for proper formatting.