# Git and GitHub

**Agenda**

- Introduction to Version Control System and Git
- Starting with Git
- Making changes to the local repository
- Branching in Git
- Syncing with the central repository

## Version Control System (VCS)

Before the invention of VCS, people made copies of files to reflect the changes.

#### Issues with the manual version control system

- Difficult to identify the changes between files over time.
- Not efficient with projects that have thousands of files.
- Difficult to collaborate when multiple people work on the same files.
- Difficult to revert to the previous version.
- Difficult to store the metadata (such as who made the changes, date, and reason).

So, it isn't easy to maintain the file version manually. This is where VCS helps you.

#### What is a Version Control System :

A Version Control System (VCS) is a software development tool that tracks and manages changes made to files over time.

#### Why Version Control System :

1. **Collaboration**: Multiple users can work on the same project without conflicts.
2. **Version tracking**: Track changes and identify who made them and when.
3. **Backup and recovery**: Recover previous versions in case of errors or data loss.
4. **Branching and merging**: Work on new features or bug fixes without affecting the main project.

**Advantages:**

1. **Version history**: Track changes and revert if needed.
2. **Collaboration**: Multiple users can work together.
3. **Backup**: Regular backups ensure data safety.
4. **Flexibility**: Work on different branches and features.
5. **Scalability**: Manage large projects and teams.

**Disadvantages:**

1. **Learning curve**: Steep learning curve for beginners.
2. **Complexity**: Manage conflicts and merges.
3. **Storage**: Large repositories require significant storage.
4. **Security**: Ensure access control and data protection.
5. **Dependence**: Reliance on VCS for collaboration and versioning.

#### Basic keywords of Version Control System:

1. **Repository** (Repo): Central location for storing project files.
   1. **Remote**
   2. **Local**
2. **Commit**: Saving changes with a meaningful message.
3. **Branch**: Separate line of development, e.g., feature/new feature.
4. **Merge**: Combining changes from different branches.
5. **Push**: Uploading changes to a remote repository.
6. **Pull**: Downloading changes from a remote repository.

## What is Git?

Git is a free and open-source Version Control System (VCS). It's a distributed system, meaning every developer working on a project has a local copy of the entire project history.

Git was created by Linus Torvalds in 2005, Who is also a creator of Linux. Read More about [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds)

#### Benefits of Git:

- Widely used Version Control System
- Fast performance because it is a distributed system allows full local operations
- Multiple users can work together
- Data integrity through SHA-1 hashing

#### Popular platforms for Git:

- **GitHub**: Web-based Git repository hosting.
- **GitLab**: Web-based Git repository hosting with built-in CI/CD tools.
- **Bitbucket**: Web-based Git and Mercurial repository hosting.

#### Basic Git workflow:

- **Initialize**: Create a new repository with `git init`
- **Add**: Add files to the repository with `git add`
- **Commit**: Save changes with a meaningful message using `git commit`
- **Push**: Upload changes to a remote repository with `git push`
- **Pull**: Download changes from a remote repository with `git pull`
- **Merge**: Combine changes from different branches using `git merge`

### Git vs GitHub

The short answer is **NO**
Any **VCS** will have two parts:

1. **Local Repository**
   - Where Developers make changes on their laptop/Desktop.
   - Git is used in the local repository.
2. **Remote Repository**
   - Remote server where you will push the changes so others can access it.
   - GitHub is used in the remote repository

### Creating an account on GitHub and Creating a repository

### Git Configuration

`git config` is a command to configure Git settings, such as user information, repository settings, and behaviour. It allows you to customize Git to suit your needs.

`git config --global user.name "Your Name"`
`git config --global user.email "your@email.com"`

**To check the folder status**

`$git status`
![image](attachments/2d9813c9bd2032f4b7bb7886b8f5c84509092909.png)

**To initialize the repository**

`$git init`

![image](attachments/c35e3544a03b26e9afa66e5c1c6153263fa243ee.png)

Git will track this folder.

**What will happen if we check the status after initiating the Git?**
`$git status`
![image](attachments/c36b3c269f50ca823b168fa4d682b2195799cb42.png)

How to create a file inside the folder? You can use the `vi` editor on the terminal, or you can manually make a file inside the folder.

If you decide to create a folder through the `vi` editor in the terminal, you need to enter `$vi fileName.txt`
Once you enter the `vi` editor, you must enter insert mode by clicking `i` on your keyboard. Then only you can write.

Once you complete the writing, press `esc` and then press `:wq!` to save the notes you have written and exit.

To see the content inside the text file that you have created, use `$cat fileName.txt`

![image](attachments/71169e3f0926492ecd8219fe0403c2358736126d.png)

What does `.git` contain?
The `.git` directory, also known as the Git repository directory, is a hidden folder that Git uses to store metadata about a repository. It contains all the necessary information to manage the repository.

**What will happen if we check the status after creating a file?**
`$git status`

![image](attachments/6443fc82e5100eda2a0da7d01e3a2eae83d39f97.png)

Git is saying that there is an untracked file.

#### Statges of Git

- Untracked
  - Files that Git is not tracking.
  - Newly added files that haven't been staged or committed.
- Modified
  - Files that have been changed but have not yet been committed.
  - Files that are different from the last commit.
- Staged
  - Files that have been modified and added to the staging area.
  - Files ready to be committed.
- Committed
  - Files that have been safely stored in the local repository.
  - Files that have been committed and are part of the project history.
    ![image](attachments/3d5ed4dbd2c80a0a8c463eb0a5110af7198acdf8.png)

**To add file to staging area**
`$git add fileName.txt`
![image](attachments/0aebce7eaa4554842fcc64ce6094e9e8a5c28f2a.png)
No error means added successfully

**What will happen if we check the status after adding a file to the staging area?**
`$git status`
![image](attachments/86fdd9ca3f441d4c4afb31d2b707c8fba096d330.png)

**How do you unstage the file that has been staged?**

`$git rm --cached learningGit.txt`
![image](attachments/c84401896d48688422be654efb01d26b4c160f3b.png)

You can see the below image, which clearly shows that no file is staged.
![image](attachments/ed746b8c24d98369790ae202906893b28e26b8f6.png)

**How to add multiple files at a time?**

Before adding multiple files, let's check the status,

![image](attachments/306b9cc6607ea386e03518635ab2c790c16932cb.png)

`$git add .`

![image](attachments/070c36ebaec7cb64d7ed98f20f893c26a3ba6e3b.png)
If nothing is showing, it means git added all the files to the staging area. Let's check by using the status command

![image](attachments/d1a576ee0143255090e4c5e3cbc11c7e28b05951.png)

To unstage all the files at a time use,

`$git reset`
![image](attachments/d2794a722ee60eec7ef0589c879f3a184f13519c.png)
If nothing is showing, it means git removed all the files from the staging area. Let's check by using the status command
![image](attachments/306b9cc6607ea386e03518635ab2c790c16932cb.png)

VCS is basically used to have a version of the software. So `$git commit` records the changes made to the repository.
`$git commit` contains:

- Commit message
- Author information.
- Timestamp.
- Parent commit(s).

![image](attachments/dd410b2cb00b1ffd4e85100204a346b27e5e5ec2.png)

Once there is nothing to commit, the following message will be displayed.
![image](attachments/a21918127c9ea08d2cf8daf2ffe28946d8f0adb7.png)

How to see all the commits made to the repository?
`$git log`

![image](attachments/8e55cef4e8af44a217841e2515eb6b21fa0db9ea.png)

1. Show a log of all commits made to the repository.
2. View details about each commit, such as:

- Commit hash (ID)
- Author and date
- Commit message
- Changed files

If you want to see the details of the last n commits, then
`$git log -n 1`

![image](attachments/16fa495d2892e87e3a0b3e6e9f22a3fd1e2d2afb.png)

If you want to check the commits done by specific person then
`$git log --author=<author-name>`

![image](attachments/b25eb42a9681e4618d889e14b7ee813fa6ae63dd.png)

To see the commit details,
`$git show <commit-hash>`

It gives all the details of the particular commit.
![image](attachments/3464436e423b26c9d9c6e7b65ee3e5049fe4c5d6.png)

## Flow Diagram

![image](attachments/3c9f884dbc85ccc3be0acca2ad981bf71ff4555f.png)

## Branching

Branching allows developers to work on features and resolve bugs and/or experiment in isolation without disturbing the main codebase.

`$git branch`

1.  List branches
    The asterisk (\*) indicates the currently active branch.
    ![image](attachments/499be45409141dca20787e9d9c116af59bfd582c.png)

2.  Create a new branch
    ![image](attachments/dec13d18bb3c6ed1be40f81ed09a350b2bde2fdd.png)

        If we recheck the branches,

    ![image](attachments/062cef5469afef56a18432714a46958d335ab39d.png)

3.  Delete a branch
    ![image](attachments/318d3ec9d7e5406eceaf50c07d07b51178e04aa0.png)

        You can also force delete a branch `git branch -D branch-name`

4.  Renaming the current branch
    ![image](attachments/afc695cfbae83c33447c60f37cdb9cb61c71cde9.png)

5.  Show more information: To see the last commit on each branch
    ![image](attachments/3b6360aa0bf15b5b05a33b51d72f9c68548167fe.png)

6.  To change the branch
    ![image](attachments/0309f6adf36132dbcc65cb74dd28f09930088768.png)
    create and change the branch
    ![image](attachments/65510420357c3f1d1da8b3c4925a75e9bab7c0f9.png)

> When you create a new file in a different branch and commit it in the new branch will not affect the main branch
> ![image](attachments/69cba1c573abcdfaad5d29ca99104c6d9da4fffd.png)
> ![image](attachments/037762a02553f48cee3e1f51fd753fefd31d6808.png)

**How do you go to a particular commit ID? and create a new branch?**
![image](attachments/f262767a494be9a44e0ad8529b89d64ff798b18c.png)
![image](attachments/66ef2cedb8487794d4e8435ba7c1c0274ed50bd1.png)

## Merge and Merge Conflict

To merge files from different branches to the main
`$git merge branchName`
Once you give this command, an VI editor will open and write the meaningful merge message

### merge conflict

**Before resolving conflicts:**

- Run `git status` to identify conflicting files.
- Use `git log --merge` to understand the merge history.

**Resolving conflicts:**

- Open the conflicting file in a text editor.
- Identify conflict markers: `<<<<<<<`, `=======`, and `>>>>>>>`.
- Decide which changes to keep:
  - `<<<<<<<` indicates your local changes (current branch).
  - `=======` separates local and incoming changes.
  - `>>>>>>>` indicates incoming changes (merged branch).
- **Merge changes manually**
  - Keep or remove conflict markers.
  - Resolve overlapping changes.

**After resolving conflicts:**

- Run `git add <file>` to stage resolved files.
- Run `git commit` to commit resolved changes.
- Use `git log` to verify conflict resolution.

## Pull Request

A pull request (PR) is a way to propose changes to a repository's codebase by requesting that your changes be merged into the main branch.

#### Why Use Pull Requests?

1. **Improved Code Quality**: Peer review ensures that changes meet coding standards and are thoroughly tested.
2. **Collaboration**: Facilitates discussion and feedback among team members.
3. **Change Management**: Tracks changes, approvals, and merges.
4. **Testing**: Allows testing before merging into the main branch.

#### Pull Request Process

1. **Create a Branch**: Make changes in a new branch.
2. **Commit Changes**: Regularly commit changes with descriptive messages.
3. **Push Branch**: Push branch to remote repository.
4. **Create Pull Request**: Submit PR via GitHub/GitLab/Bitbucket.
5. **Review**: Team reviews and discusses changes.
6. **Approve**: Approved by maintainers or reviewers.
7. **Merge**: Changes merged into the main branch.

#### Key Elements of a Pull Request

1. **Title**: Clearly describes changes.
2. **Description**: Provides context and explains changes.
3. **Labels**: Categorizes PR (e.g., bug fix, feature).
4. **Assignees**: Designates reviewers or owners.
5. **Comments**: Facilitates discussion and feedback.

#### Pull Request States

1. **Open**: Waiting for review.
2. **Approved**: Ready to merge.
3. **Merged**: Changes merged into the main branch.
4. **Closed**: PR rejected or cancelled.

## git clone

Creates a local copy of a remote Git repository. Downloads all repository data, including branches, tags, and history.

**How `git clone` Works:**

- **Connects to remote repository**: Git connects to the remote repository using the provided URL.
- **Downloads data**: Git downloads all repository data, including branches, tags, and history.
- **Creates local directory**: Git creates a new local directory with the same name as the remote repository.
- **Initializes local repository**: Git initializes a new local repository in the created directory.
- **Checks out branch**: Git checks out the specified branch (default: main).
- **How to use `git clone`**

1. Open a terminal or command prompt.
2. Navigate to the directory where you want to create the local copy.
3. Run the command: `git clone <repository-url>`

**Common `git clone` Options:**

- `--branch <branch>`: Clones a specific branch.
- `--depth <n>`: Clones only the last n commits.
- `--single-branch`: Clones only one branch.
- `--mirror`: Creates a mirror repository.

**Example Usage:**

- `git clone https://github.com/user/repo.git`
- `git clone -b dev https://github.com/user/repo.git` (clones dev branch)
- `git clone --depth 1 https://github.com/user/repo.git` (clones only the last commit)

#### Adding a branch to a remote repository

**Step 1: Create a new branch**

- Run `git branch <new-branch-name>` to create a new branch.
- Run `git checkout <new-branch-name>` to switch to the new branch.

**Step 2: Make changes and commit**

- Make changes to your files.
- Run `git add <file-name>` to stage changes.
- Run `git commit -m "<commit-message>"` to commit changes.

**Step 3: Push the branch to a remote repository**

- Run `git push <remote-repo-name> <new-branch-name>` to push the branch to a remote repository.

**Example**

- `git branch feature`
- `git checkout feature`
- `git add .`
- `git commit -m "Add new feature"`
- `git push origin feature` (push to origin remote repo)

**Note**

- Replace `<new-branch-name>` with your desired branch name.
- Replace `<remote-repo-name>` with the name of your remote repository (e.g., origin).
- This will push the branch to the remote repository without merging it into the main branch.

**Pushing to a forked repository**

- If you want to push the branch to a forked repository, use `git push <forked-repo-name> <new-branch-name>`.
- Replace `<forked-repo-name>` with the name of your forked repository.

## git pull

`git pull` fetches changes from a remote repository and merges them into your local repository.

**What does `git pull` do?**

- **Fetches changes**: Downloads changes from the remote repository using `git fetch`
- **Merges changes**: Merges the downloaded changes into your local repository using `git merge`
