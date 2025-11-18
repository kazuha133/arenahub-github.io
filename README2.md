Here's how to use the Git commands listed in your notes, with practical examples for each one:

1. Basic Git Commands

git clone <repository>

Usage: Clones a remote repository to your local machine.

Example:

git clone https://github.com/username/repository.git


This copies the repository from GitHub to your local computer, creating a new folder with the repository's files.

git status

Usage: Shows the status of the working directory and staging area.

Example:

git status


This will tell you which files are staged, which are modified, and which are untracked.

git add <file>

Usage: Stages a file for commit.

Example:

git add index.html


This stages the index.html file for commit.

To add all modified files:

git add .


This adds all modified files in the current directory to the staging area.

git commit -m "message"

Usage: Commits the staged changes with a message describing the changes.

Example:

git commit -m "Fix header layout"


This commits your staged changes with the message "Fix header layout."

git push

Usage: Pushes committed changes to the remote repository.

Example:

git push origin main


This pushes your changes to the main branch on the remote repository (e.g., GitHub).

git checkout <branch>

Usage: Switches to the specified branch.

Example:

git checkout feature-branch


This switches your working directory to the feature-branch.

git merge <branch>

Usage: Merges the specified branch into the current branch.

Example:

git merge feature-branch


This merges feature-branch into your current branch (e.g., main).

2. Git Configuration

git config --global user.name "Your Name"

Usage: Sets your global Git username, which will appear in your commits.

Example:

git config --global user.name "John Doe"


git config --global user.email "youremail@example.com"

Usage: Sets your global Git email address, which will be associated with your commits.

Example:

git config --global user.email "johndoe@example.com"

3. Git Key Setup

ssh-keygen -t rsa -C "email@example.com"

Usage: Generates an SSH key pair (public and private) to securely authenticate with remote Git servers (like GitHub).

Example:

ssh-keygen -t rsa -C "johndoe@example.com"


After running this, follow the prompts to save the key. Once done, you need to add the SSH key to GitHub (or another Git service).

4. Reset Commands

git reset --soft <commit>

Usage: Resets the HEAD to a specified commit, but leaves the working directory and staging area unchanged. You can recommit the changes.

Example:

git reset --soft HEAD~1


This command will reset the HEAD to the previous commit (1 commit back) but leave the changes in your working directory.

git reset --mixed <commit>

Usage: Resets the HEAD and staging area, but keeps the working directory unchanged.

Example:

git reset --mixed HEAD~1


This resets the HEAD to the previous commit and removes the changes from the staging area, but keeps them in your working directory.

git reset --hard <commit>

Usage: Resets the HEAD, staging area, and working directory to a specific commit, discarding all changes.

Example:

git reset --hard HEAD~1


This command resets everything (HEAD, staging area, and working directory) to the previous commit and discards any uncommitted changes.

5. Rebase Command

git rebase <branch>

Usage: Re-applies commits from your current branch on top of another branch. It's useful for keeping a clean history.

Example:

git rebase main


This will rebase your current branch on top of the main branch, applying your commits after all the commits in main.

6. Cherry-pick Command

git cherry-pick <commit>

Usage: Applies a specific commit from another branch to the current branch without merging the entire branch.

Example:

git cherry-pick a1b2c3d4


This applies the commit with the hash a1b2c3d4 to your current branch.

Summary:

Add and commit changes to your local repository.

Push changes to the remote repository.

Branch management (checkout, merge, rebase, cherry-pick) for clean and efficient workflows.

Reset commands to undo changes and control history.

SSH key generation for secure Git operations.

Understanding these commands and how they interact with your repository will help you navigate version control and collaborate more effectively during your exam and in real-world projects.
