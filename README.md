# GIT Tutorials

**Index**
1. [Git introduction](https://github.com/iam-rahul-sah/GitTutorials#1-git-introduction)
2. [Setting GIT for usage](https://github.com/iam-rahul-sah/GitTutorials#2-setting-git-for-usage)
3. [GIT - Three stage architecture](https://github.com/iam-rahul-sah/GitTutorials#3-git---three-stage-architecutre)
4. [Getting started - Tracking your file(Basic and most common git command)](https://github.com/iam-rahul-sah/GitTutorials#3-git---three-stage-architecutre)
5. [GIT file status lifecycle](https://github.com/iam-rahul-sah/GitTutorials#5-git-file-status-lifecycle)
1. [Unstaging and Unmodifying file](https://github.com/iam-rahul-sah/GitTutorials#6-unstaging-or-unmodifying-files)
1. [.gitignore file](https://github.com/iam-rahul-sah/GitTutorials#7-gitignore-file)
1. [GIT diff](https://github.com/iam-rahul-sah/GitTutorials#8-git-diff)
1. [Moving and Renaming files](https://github.com/iam-rahul-sah/GitTutorials#9-moving-and-renaming-files)
1. [Viewing(logging) commit history and difference between the commits.](https://github.com/iam-rahul-sah/GitTutorials#10-viewinglogging-commit-history-and-difference-between-the-commits)
1. [All about git commit](https://github.com/iam-rahul-sah/GitTutorials#11-all-about-git-commit)
1. [Setting alias in git](https://github.com/iam-rahul-sah/GitTutorials#12-setting-alias-in-git)
1. [Working with remote repositories](https://github.com/iam-rahul-sah/GitTutorials#13-working-with-remote-repositories)
1. [All about branches in GIT.](https://github.com/iam-rahul-sah/GitTutorials#14-all-about-branches-in-git)
1. [Git merge and squash](https://github.com/iam-rahul-sah/GitTutorials#15-git-merge-and-squash)
1. [Merge conflict](https://github.com/iam-rahul-sah/GitTutorials-#16merge-conflict)
1. [Git rebase](https://github.com/iam-rahul-sah/GitTutorials#17git-rebase)
1. [Interactive rebasing](https://github.com/iam-rahul-sah/GitTutorials#18-interactive-rebase)
1. [Cherry picking ](https://github.com/iam-rahul-sah/GitTutorials#19-cherry-picking)
1. [Reflog](https://github.com/iam-rahul-sah/GitTutorials#20-reflog)
1. [Submodules](https://github.com/iam-rahul-sah/GitTutorials#21-submodules)
1. [git revert reset](https://github.com/iam-rahul-sah/GitTutorials#22-git-revert-reset-and-checking-out)
1. [git tag](https://github.com/iam-rahul-sah/GitTutorials#23-git-tag)
1. [git stash](https://github.com/iam-rahul-sah/GitTutorials#24-git-stash)
1. [git blame](https://github.com/iam-rahul-sah/GitTutorials#25-git-blame)
1. [git bisect](https://github.com/iam-rahul-sah/GitTutorials#26-git-bisect)

---

## 1. GIT introduction

**Why is GIT around?**  
It is a version control system. It is used to track changes in files and directories. 
 
**Features of GIT:**
1. Easily recoverable.
1. Who, when introduced an issue?
1. Roll back to previously working state.

**History of VCS:**  
- *Local VCS*: Uses DB and keep track of files, locally on the computer.
    - Pros: Can track files and rollback to previous versions.
    - Cons: Files are stored locally, so there are chances of losing data.
    
- *Centralized VCS*: Uses a central server to store all files and enables team collaboration.
    - Pros: Can track files and rollback to previous versions. Can collaborate with team members.
    - Cons: If the central server goes down, then no one can collaborate or track files.
    
- *Distributed VCS*: Each and every person contributing to the source code has a copy of the version of the source code. Also storing the history  of the codebase.

**Distinctive features of GIT from other VCS:**
1. It captures snapshot and not the file differences.
1. Almost all operations are local.
1. Integrity of data.
1. GIT has three main states that your files can reside in: committed, modified, and staged.
1. Git generally only adds data to the repository.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 2. Setting GIT for usage.

- `git config --global user.name "John Doe"`: Setting the user name to be displayed in the commit.
- `git config --global user.email = "johndoe@gmail.com"`: Setting the user email address to be displayed in the commit.
- `git config --list`: To display the list of configuration option for the user either globally or for a particular directory.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 3. GIT - Three stage architecutre

*commit* - It is the process of saving the changes to the local repository through means of capturing a snapshot of the project.

![img](/images/threeStageArch.png)

- *Working directory* - It is the directory where the files are stored and the changes are made.
- *Stagging area* - It is the area where the files are staged for commit.
- *Local repository* - It is the area where the files are stored after commit.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 4. Getting started - Tracking your file

- `git init` - Initializes the git repository.

- `git status` - Shows the status of the files in the working directory.

- `git add <file>` - Adds the file to the staging area. Multiple file names are seperated by comma. We can also use `git add .`  or `git add --a` to add all the files in the working directory to the staging area.

- `git commit` - Commits the files in the staging area to the local repository. We can also use `git commit -m "message"` to add a message to the commit in the terminal itself or else it will open the default editor to add the message.  

**Note**: A commit message should specify "WHAT" are the changes and "WHY" you have made the changes. 

- `git log` - Shows the commit history.
 
- `rm -rf .git` - Removes the git repository.

- `git clone <url>` - Clones the repository from the url to the local machine.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 5. GIT file status lifecycle

- *Untracked* - The file is not being tracked by GIT.
- *Unmodified* - The file is being tracked and is not modified(i.e. same as the initial file).
- *Modified* - The tracked file is modified.
- *Staged* - The tracked file is modified and is now staged for commiting.
- *commited* - The changes in the staged files are captured as snapshot and the file is again moved to unmodified section.

Once a git repository is initialized all the files inside it are untracked. Using `git add` we can add the files to the staging area. Once the files are added to the staging area, the files are tracked by GIT and are in the staged state. Once the files are committed, the files are in the unmodified state. If a file is in staging area and is modified, then the file co-exits in the staging area as well as the modified area. Commiting the file will capture the snapshot of the file in the staging area.

**File status lifecycle**  

![File status lifecycle](/images/fileStatusLifecycle.png)

*Example Step*:(To demonstrate a file existing in both stagging and modified file section)

1. A git repository is initialized(with name.md file) and the file is untracked.
1. The file is added to the staging area using `git add name.md` and the file is in the staged state.
1. The file is committed using `git commit` and the file is in the unmodified state.
1. The file is modified and the file is in the modified state.
1. The file is added to the staging area using `git add name.md` and the file is in the staged state.
1. The name.md file is again modified instead of commiting the file.
1. The file is in the modified state and the staged state(both co-exist).
1. The file is committed using `git commit` and the file in the staged state is captured in the local repository and the file in the modified state still exist in the modified state.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 6. Unstaging or unmodifying files

- `git restore --staged <file>` - This command is used to move file from staging area back to modified file section(i.e. for unstaging the files)
- `git checkout -- <file>` - This is another command used to unstage the file
- `git restore <file>` - This command is used to discard any changes in the file. It moves files from modified file section to unmodified file section. The changes to the unstaged files(modified file) is discarded and the files is restored to the version of the file from the previous commit.

**Note**: We can use "." flag with the `git restore` command to specify all the file at once, and the "-f" flag with `git checkout` command to specify all the file at once.

**Deleting a file from being tracked**

**Note**: `git restore` command cannot be used to move a file from "staged files" to "untracked files". To move a file from "staged file" to "untracked files" we need to use '`git rm --cached <filename>`'. Though in order to use "." to specify all the file we need to use "-r" flag to specify files to be deleted recursively. `git rm --cached -r .`.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

--- 

## 7. .gitignore file

".gitignore" file is used to ignore the files that are not required to be tracked by GIT. These files are not shown in the `git status` command.

**.gitignore file syntax**

`<filename with extension>`  
`<directoryname>`  
`<pattern>`  
`!<filename>` - To unignore the file.  
`*.ext` - To ignore all files in the directory. With the specified extension.  
`*` - To ignore all files in the directory.  
`**` - To ignore all files in the directory and subdirectories.  
`/` - To ignore the directory.  
`#` - To add comments.  
`dir/` - To ignore the directory.  
`/dir/` - only ignores the 'dir' in the root folder, rest 'dir' within directories and sub-directories will be tracked.  

**Note**: `Blank folder` or folder only containing igonred files are by default ignored by GIT.

**Note**: If a file is already tracked by GIT and is added to the .gitignore file, then the file will still be tracked by GIT. To stop tracking the file, we need to remove the file from the git repository using `git rm --cached <filename>` and commit the changes.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 8. GIT diff

- `git diff` - Shows the difference between the modified version(there should be a modified verison of the file or else it does not yield any result) of a file and the staged version of the file(if one exists or the committed version of the file)
- `git diff --staged` - Shows the difference between the staging area and the perviously commited files.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 9. Moving and Renaming files

- `git mv <filename> <newfilename>` - Moves the file to the new file name. This command is equivalent to `mv <filename> <newfilename>` 
- `git rm <filename>` - Removes the file from the working directory. This command is equivalent to `rm <filename>`

**Note**: These command are equivalent to there linux commands. The only difference is that the git command automatically tracks the changes and add these changes to the staging area to be commited.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 10. Viewing(logging) commit history and difference between the commits.
- `git log` - to display the commit history.
- `git log -p` - This command shows all the difference between the consecutive commits.

*Example*:
Consider there are three commits initial commit, second commit and third commit, then this command will display

```
third commit, details
    difference between the third and second commit
second commit, details
    difference between the second and initial commit
Initial commit
    all the code of the commited files
```

- `git log -p -3` -  This command will show the difference between only the last three commit   
- `git log --stat` - This command gives a short summary about the difference between the commits
- `git log --pretty=online` - This command gives an organized commit history, each commit only taking one line of space
- `git log --pretty=short` - Give the commit history is short
- `git log --pretty=full`

**Searching and finding a commit**

1. By date - commits after or before a particular dates
```dotnetcli
$ git log --after="YYYY-MM-DD"
$ git log --before="YYYY-MM-DD"
```
2. By commit message - commits containing a certain word or sentence in the commit message.  
`git log --grep="word/expression"`  
'grep' flag can also use regex.

3. By author  
`git log --author="Author name"`

4. By file -  Filtering the commits where a specific file was changes  
`git log --Readme.md`

5. By branch - Filtering the commits that are in main branch but not in the feature branch  
`git log feature..main`

**Note**: We can use these flag in combination for advance searches.

**Difference between author and commit**

**Author** - The user who has created the file is the author of the file.  
**Commit** - The use who has made changes and commited the file.

**Filtering commit history using days**

- `git log  --since = 2 days` - This command display the commit from the last two days. We can also use 2 months, 2 weeks, 2 years.

**Displaying commit history in a particular format**
- `git log --pretty=format:"%h -- %an"` - This command will show the log in a format specified by the user after (:) using format pattern

Refer official git documentation for the format pattern

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

### 11. All about git commit

- `git commit` - Commits the files in the staging area to the local repository. We can also use `git commit -m "message"` to add a message to the commit in the terminal itself or else it will open the default editor to add the message. 

**Amending a git commit(changing your last commit)**
- `git commit --amend` - This command will help us to commit new made changes to the previous commit. We can also change the message of the commit.
- `git commit --amend -m "messaage"` - This will change the message and the commited files in the terminal itself.

**Skipping the staging area**

- `git commit -a -m "message"` - This command skips the stagging area and directly commits all the files from the modified section to the local repository. This command does not add the untracked files to the staging area(i.e. this command does not work for new files). This command is not recommended as it does not give a chance to review the changes before commiting.

**The perfect commit**

1. Add only the right changes to the commit(i.e. changes that are specific to that commit)
1. Compose a good commit message

- Not to do - Not just cram everything into one single commit.

**Note** - One commit should only include change to a specific topic.

- Use staging area to select files that are related to changes for a specific topic and then do a commit. We can consequently make other commit for other changes.

**Adding a patch of code to the stagging area:**

Patch: A "patch" is a part or small chunck of code that you have changed.

- `git add -p <filename>`

Now git ask if we want to add the patch to staging area or not for each patch consecutively. Press 'Y' for yes, 'n' for no or 'e' for manually selecting the patch.

**The perfect commit message**
1. Subject = Concise summary of what happened.
1. Body = More detailed explanation(what is now different than before)

**Note**: Body is note displayed in log when we want the summary or a brief of the commit history.

**Creating a commit message with a subject and a body**  
When we commit a message in our code editor. The first line of commit is the subject then we have to leave one line after that and now we can add a body to the commit.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 12. Setting alias in git

- `git config --global alias.shortcut_key git_command` - This command is used to set alias for a git command

**Example** - `git config --global alias.st status` - Command to create 'st' as a shortcut for status.

**Note** - For a command with multiple word we need to enclose it within quotes.

**Example** - `git config --global alias.unstage 'restore --staged --'` - Here "--" is necessary as it take additional argument as file name or else it won't work.

**Example** - `git config --global alias.last 'log -p -1'`

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 13. Working with remote repositories

1. Click on the "+" icon in the top-right corner
1. Click on 'New repository'
1. Enter the details like name, description, etc.
1. Click on create repository

A new window for quick setup appears

A remote server is a server hosting your git project somewhere on the internet.
- `git remote` - This command is used to setup and view the remote servers.
- `git remote add origin "your repository url"` - This command is used to add an url for the remote repository.
- `git remote -v` - This command is used to display all the url for the remote repository.


*Pull* - Pull command is used to fetch any changes made on the remote server to your local version. A pull command does a `git fetch` followed by a `git merge`.   
*Push* - It is just and incremental push. This command update the remote repository with any changes made on our local git.

**Note**: Push command requires access from the remote server to upload the data.

**Step to get access to your git account from your PC.**

1. Setting > SSH and GPG keys > New SSH key
1. Add title to SSH key
1. We need to add the SSH keys but first we need to generate a SSH key

**Steps for creating SSH key in your PC**

1. `ssh-keygen -t ed25519 -c "your email address"` - To generate the SSH key. 
1. `eval $ (ssh-agent -s)` - To ensure if the ssh agent is running.
1. `ssh-add ~/.ssh/id_rsa` - Adding ssh private key to the SSH agent.
1. `tail ~/.ssh/idrsa.pub` - Command to display ssh key

Now we can add this generated SSH key to our git account.

**Useful command for working with remote repositories**

- `git fetch` - This command is used to update or fetch any changes in the remote repository.
- `git pull` - This command is used to update your git repository similar to the remote repository. This command does a `git fetch` followed by a `git commit`.
- `git push` - This command is used to update remote repository version similar to your PC's git version.

**Pull request**
- A pull request invites reviewers to provide feedback before merging
- Contributing code to other repositories

**Fork**:
A fork is a personal copy of a git repository. By creating a "fork" of the original repository, you can make changes, and then you can suggest those changes to be included via pull request to the main repository.

**--set-upstream flag**

`git push --set-upstream origin <branchname>`

--set-upstream  flag sets a default branch for you local branch. Every branch can have an upstream/default branch on the remote. So whenever they push or pull they do not need to specify the branch like `git push origin master` they can just use `git push`. These(i.e. setting upstream) also keep your branch in sync with the remote repository.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 14. All about branches in GIT.

A branch is a local copy of your code base where you can make changes without affecting your original code. These changes can later be integrated into your main workflow if everything goes well.

**Branching startegies**

A written convention - Agree on a branching workflow in your team.

**Why to do this -** 

1. Git allows you to create branches - but it doesn't tell you how to use them.
1. You need a written best practice of how to work, that is idealy structured for your team to avoid mistakes and collisions.
1. It highly depends on your team, team size, on your project and how you handle releases.
1. It helps to onboard new team member.


**Startegies for integrating changes and structuring releases.**

1. *Mainline development*("Always be integrating")
    - Few branches
    - Relatively small commits
    - High - quality testing and QA standards(since the commit are directly added to main branch)

2. *state, release and feature Branches*  
Branches enhance structures and workflows of the development. Different type of branches, fulfil different types of jobs.

**Types of branches**

1. Long running branches - Exist through the complete lifetime of the project. Often, they mirror "stages" in your dev life cycles.

*Common convention*: No direct commit(generally through merge)

2. Short lived branches - For new features, bug fixes, refactoring, experiments. Branches are deleted after integration.

**Github flow - very simple, very lean: only one long-running branch("main") + feature branches.**

**How to work with branches.**

- "Head" branch - Currently 'active' branch

1. Creating new branch(based on current) "Head" branch
- `git branch <new branch name>`
- `git checkout -b <branchname>` - This command creates a branch and then switches to the newly created branch. If a branch already exist then it gives an error.
- `git checkout <branchname>` - This command switches to the specified branch(if one exists) or else throws an error if one does not exist.
- `git branch` - shows a list of branch

**Note** - Changing branches have no effect on ignored files.

2. Creating a branch from particular commit as the common ancestor  
`git branch <branchname> '<commithash>'`

3. Switching branches.
```dotnetcli
$ git checkout <branchname>

    or we can use

$ git switch <branchname>
```

4. Renaming a branch(Renaming current head branch)  
`git branch -m <newname>`

5. Renaming a non-head branch(i.e. some other branch)  
`git branch -m <branchname> <newname>`

6. Pushing to a remote branches  
`git push -u origin <local branch>`
-u specifies to keep track of remote branch, so next time we can use "git push" simply.

7. Tracking branches(connecting branches with each other)
```
$ git branch --track <new-branch> origin/<base-branch>

    or 

$ git branch --track origin/<base-branch>
```

8. Checking status(last commit) of your branches  
`git branch -v`

9. Deleting branches

- `git branch -d <branchname>` - This command is used to delete a branch

**Note** - This git command gives an error if the branch that we are deleting is not yet merged to any branch.

- `git branch -D <branchname>` - "-D" flag is used to enforce deletion of the branch even if it is not merged to any other branch.

**Note** - Always make sure all you branches are merged before deleting.

10. Deleting remote branch  
```
git push origin --delete <branchname>
            or
git push -d origin <remote_branch_name>
```

11. Merging branch(Integrating into your current active branch)  
`git merge <branch name>`

12. Comparing branches
```
$ git log main..feature
```
Note: This command shows the commit that are in the feature branch but are not in the main branch.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 15. Git merge and squash

"Git merge" is used to integrate changes from one branch into another branch. `git merge` command is used to merge branches.

**How a git merge workds**

- git looks for three things before merging a branch:
    - Common ancestor
    - last commit on the current branch
    - last commit on the branch to be merged

1. A simplified scenario(Fast-forward merge).
![fast-forward merge](/images/fast_forward_merge.png)

2. A more realistic scenario
![simple merge commit example](/images/simple_merge_commit_example.png)

**When is a git squash used**

- Squash is used to create a single commit from multiple commits.
- Squash is used to create a clean and straight commit history

**Squash commit scenario**  
*commit history of a code base*

![commit history of a code base](/images/branching_workflow.png)

- Git merge - using only `git merge <branchname>`, will do something like this.

![simple merge command](/images/merging_using_simple_merge.png)

- To achieve a simple straight commit history we need to use `git merge --squash <branchname> -m "message"`

![merge using squash](/images/merge_using_squash_flag.png)

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 16. Merge conflict

**How and when conflicts occur**  
When integrating commits from different branches, git tries to merge them automatically. If there are no conflicts, git will create a new merge commit and you are done. If there are conflicts, git will stop and tell you that there are conflicts. You have to resolve them manually and then commit the result. Conflicts can also occur when rebasing, cherry-picking, pull or stash apply.

**Merging changes that are completely different from each other is a flawless process.**

![Simple merge process](/images/simple_merge_commit_example.png)

**Merge conflict occures when contradictory changes are made to the same line of the same file.**

![merge conflict example](/images/merge_conflict_example.png)

Here in the commit C2 and C4 the exact same line of code(i.e. `<div>one</div>`) was modified. So git doesn't know which one to keep and which one to discard. So it asks us to resolve the conflict manually.

**Undoing a conflict and start over**

We can always undo a merge conflict and start over again by using.

- `git merge --abort` - This command aborts the merge process and restores the state of the branch to the state before the merge process started.
- `git reset --merge` - This command is used to undo a merge conflict and start over again.
- `git rebase --abort` - This command aborts the rebase process and restores the state of the branch to the state before the rebase process started.

**What does a merge conflict looks like in the code?**

| symbol | meaning |
|---|---|
|<<<<<<< HEAD|Everything below this line is the content of the current branch.|
|=======| This symbol seprates the changes from both the branches.|
|>>>>>>> branchname|Everything below this line is the content of the branch that we are merging in the current branch.|


**How to solve a conflict**
simply solve the conflict in one of the files and keep only the changes that you wish to keep. Then add the file to the staging area and commit it. After that you can continue the merge process by running `git merge --continue`.

- We can also use mergetool to solve a conflict. To use mergetool we need to install it first. To install mergetool we need to run `git config --global merge.tool <toolname>`. After installing mergetool we can run `git mergetool` to solve the conflict. 

**Some useful git commands for checking the status of the branches in regars to the merge process**
- `git branch -v` - This command returns the commit hash along with the message for the last commit in all the branch. It is useful to check if our commit are in unison or not.
- `git branch --merged` - This command returns the list of branches that have been already merged to your current branch.
- `git branch --no-merged`

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 17. Git rebase

**What is git rebase?**
When a user wants his commit to be a single line(without squashing) even when multiple branches have been integrated into the repository, then he can use git rebase. 

`git rebase branch-b` - This command will take all the commits from branch-b and put them on top of the current branch. This will make the commit history a single line.

**Rebase step by step**

*Our git structure*  
![git structure](/images/simple_branch_structure.png)

The user wants to merge both the branches but without creating a "merge commit". So we can use rebase.

**Step 1**  
Commit C3 is removed and saved somewhere else temporarily.
![git rebase step1](/images/rebase_Step1.png)

**Step 2**  
It does a fast forward commit by the time the C3 commit is parked somewhere else.
![git rebase step2](/images/rebase_step2.png)

**Step 3**
It adds the parked commit to the head of the branch.
![git rebase step3](/images/rebase_step3.png)


**Note**: Rebasing rewrite commit history, ex C3 commit has changed its commit hash as its parent commit has changed.

**Warning**: Do not use rebase on commits that you've already pushed/shared on a remote repository. Instead use it for cleaning up your local commit history before merging them it into shared team branch.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 18. Interactive rebase
Interactive rebase is a tool fo optimizing and cleaning up your commit history. With the help of interactive rebasing we can perfrom the following operation.
- Change a commit's message
- deletes commits
- reorder commits
- combine multiple commits into one
- edit/split an existing commit into multiple new ones.

**Interactive rebasing step by step**

**Step 1**: Figure out how far back do you want to go. What should be the "base" commit for your rebasing

**Step 2**: `git rebase -i HEAD~3`, here  
![git head structure](/images/interactive_rebasing.png)
- HEAD~3 specifies that we want the last third commit to be the base, commit starting from HEAD, HEAD~1, HEAD~2 and so on.
- `-i` flag is used to specify interactive rebasing

**Step3**  
When we use the rebase interactive command, it show/opens the code editor with all the commits on top of our base commit(i.e. commit on top of HEAD~3). Alogn with all the 'action' command.

*Action* command lets us specify what action we want to perfrom(like reword, edit, squash, etc). The first editor is only to specify the action to be performed on a commit.

**Some action command**  
*Reword* - It is used to edit the commit message.
*Squash* - This action command combines the commits with the commit above it.

Afer making/specifying the action in the first code editor, when we close this editor. It opens a new editor for making the changes.

**Note**  
- If we wish to make changes to the last commit we should use `git merge --amend` command instead.
**Note**  
- To make changes to a commit we need to atleast specify commit's parent as the base in the command. So for making changes to the HEAD~2 commit, we need to specify HEAD~3 as the base commit in the command like `git rebase -i HEAD~3`

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 19. Cherry picking
`git merge` integrates the last commit on the branch to be merged with the current branch. But "cherry picking" allows us to select a particular commit and merge the current branch till that commit. It allows us to integrate branches by picking up selective commits.

**Simple merge example**
[simple merge commit example](/images/simple_merge_commit_example.png)

**Cherry-pick**
[Cherry picking image demonstration](/images/cherry_picking.png)

**Use case scenario**
- One use case scenario of cherry picking is when you were supposed to commit of feature-x branch but you made it on the main branch.
[Cherry picking use case](/images/cherryp_picking_use_case.png)
- Now, we casn checkout to "feature-x" branch and use `git cherry-pick commit#`.
- Now we can go back to 'master' branch and delete the lastest branch using `git reset --hard HEAD~1`.



[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 20. Reflog
*Reflog* is a diary/log where git keep track of every movement of the head pointer. It stores the "commit hash" of the commit when our head pointer was in the branch.

A very important use of *reflog* is for recovering deleted commit, branches. As reflog keep track of all the commit hash. We can copy the "commit-hash" of the commit that we wish to retrieve and create new branch using `git branch <branch-name> commit#`

**Use case scenario**
1. We think we need to get rid of some commit.  
![git reflog](/images/git_reflog.png)
2. We used `git reset --hard HEAD~2`  
![After resetting](/images/After_resetting.png)
3. Later we realized it was a bad idea. Now we can use the commit hash from the reflog `git reflog` to reset the branch to its previous state `git reset --hard commit#`. We can also create a new branch based on the deleted commit that we want to retrieve by using `git branch <branch-name> commit#`. 

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---

## 21. Submodules
Git submodules allows us to keep a git repository as a sub-directory of another git repository. Git sub modules are simply a reference to another repository at a particular snapshot(commit) in time. Sudmodules do not track git refs or branches and are not automatically updated when the host repository is updated. When adding a submodule to a repository a new .gitmodules file is createde. The .gitmodule file contains meta data about the mapping between the submoudule project's URL and local directory. In case of multiple submodule, the .gitmodule file has a entry for all the submodules.

`git add submodule [url]`: This command is used to add a submodule to an existing repository.
`git submodule init`: This command is used to copy the mapping from the .gitmoudles file into the local file. Initialize submodule configuration(this command is necessary after creating a submodule)

**Note**: Submodules have their own branches and history.
**Submodule workflow**  
Whem making changes to a submodule it is important to publish submodule changes and them update the parent repositories reference to the submoudles.(i.e. if we have made some changes in the submodule and commited this changes then it is important for us to make our main repository aware of this changes be creating a new commit and updating the reference to submodule in our main repository. When working in team environment it is update to push the changes from the submodule and the update the main repository accordingly).

`git clone  --recursive [url]`: This command is used to clone a repository including its submodules.

`git submodule update --init`: This command is used if we have already clone a repository and now we want to load it's submodules.

`git pull --recurse-submodules`: Pull all changes in the repo including chantes in the submodules

`git submodule update --remote`: Pull all chantes for the submodules

**Creating a repository with subodules**
1. Adding a submodule to a git repository and tracking a branch.
    - `git submoudle add -b master [url]`: This command is used to add submodule and define the master branch as the one we want to track. If we track branches in our submodules, we can update them wiva the --remote paramater of the `git submodule udpate` command.
2. Adding a submodule and tracking commit.
    - Alternatively to tracking of a branch, we can also control which commit of the submoudle should be used. In this case git parent repository tracks the commit that should be checked out in each configured submodule.
3. `rm -rf .git/modules/mymodule`: This command is used to delete the git submodule.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)
---
## 22. git revert reset and checking out
`git reset`, `git revert` and `git checkout` let us undo some kind of changes in our repository. 
**Note:** "git reset" and "git checkout" can be used to manipulate either commit or indiviual files. Whereas "git revert" can only be used for manipulation commits.

- commit-level: It means undoing changes to the whole commit to a specific commit.
- file-level: It means undoing changes of the file's content to those of the specific commit.

| Command | scope | common use cases |
|---|---|---|
| `git reset` | commit-level | Discard commits in a private branch or throws away uncommited changes(changes commit history)|
| `git reset` | file-level | unstage a file|
| `git checkout` | commit-level | Swith between branches or inspect old snapshots(also changes commit history)|
| `git checkout` | file-level | discard changes in the working directory |
| `git revert` | commit-level | undo commit in a public branch.|
| `git revert` | file-level | NA|

**Note:** the parameter that we pass to the `git checkout` and `git reset` determines the scope of command. Both of these command takes a file name as argument if a file name is passed it is a *"file-level"* command or else it is a *"commit-level"* command.

1. **git checkout:** A checkout is an operation that moves the `HEAD` ref pointer to a specified commit. When checkcout command moves the HEAD pointer to the specified commit this put us in a detached HEAD state. This can be potentially dangerous if we start adding new commit becuase there will be no way to get back to them.
```bash
git checout HEAD~2         #changes the state to HEAD~2 state this is useful for instpecting the code  
```
- file-level `git checkout` discard any changes to the specified file(i.e. it updates the working directory instead of the stagged snapshot)
```bash
git checkout HEAD~2 foo.py     # makes the foo.py in the working directory match the one from 2nd-to-last commit.
```

**Note:** since checkout only changes the state of the git repo. It has potential to overwrite local changes, git forces us to stash or commit any changes in the wokring directory that will be lost during the checkout operation. 

2. **git revert:** A revert is an operation that takes the specified commit and creates a new commit which inverse all the files to the specified commit(and thus resetting the files). git revert can only be run at a commit level scope and has no file level functionality.
```bash
git revert HEAD~2          # this create a new commit and matches the state of git repo to that commit.
git revert --no-edit       # when we don't want to edit the default commit message for the new commit or else it prompt a window for adding the message
git revert --no-commit    # this will revert the changes to the  specified commit will not commit it.
```
**Note:** Reverting a commit will take you to the version that the repo was before the specified commit(i.e. it will match the repo to the state of the commit before the specified commit.)

3. **git reset:** A reset is an operation that takes a specified commit and resets the *working directory, stagged snapshot and commit history(the three trees)* to match the state of the repository at that specified commit. When we reset our branch to a specific commit in the commit history all the commit perform afer it are left dangling (also known as orphaned commit i.e. the commits will be deleted next time when GIT perfroms garbage collection). 
`eg. git reset HEAD~2` // make our git branch to the state of HEAD~2 commit
- A reset can be invoked in three different modes which corresponds to the three trees.
    - `--soft`: The staged snapshot and working directory are not altered in any way.
    - `--mixed`(default): The staged snapshot is updated to match the specified commit, but the working directory is not affecteds in any way.
    - `--hard`: the staged snapshot and working directory are both updated to match the specified commit.
- file level `git reset` updates the staged snapshot to match the version from the specified commit.
```bash
git reset HEAD foo.py          # unstages the file, changes exist as unstaged.
```

**Note:** *"reset"* and *"checkout"* are generally used for making local and private "undos". They modify the history of a repository. *"revert"* is considered a safe option for "public undoes" as it creates new commit and does not overwrite the commit history.
[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 23. git tag
Tagging in GIT refers to creating specific points in history for your repository/date. This is usually done to mark release point.

**Creating tag**
`git tag <tagname>(v1.0)`: This command is used to create a tag at the current commit. This are know as lightwheight tag.

`git tag -a <tagname> -m "message"`: This command is used to create annoted tag. These are known as annotted tags.

`git tag <tagname> commit#`: This command is used to create a tag from a commit.

**Displaying tag**  
`git tag`: Display all the tag(only).

`git show v1.0`: Display the tag with the description.

`git tag -l "v.1.*`: `-l` flag is used to provide wildcard for search tags with a particulal pattern.

**Pushing tag to the remote**
`git push origin <tagname>`: This command is used to push the tag to the remote repo.

`git push origin --tags`: To push all the tag to the remote repo.

**Deleting the tags**  
`git tag -d <tagname>`: To delete the tag on your local system

`git push origin -d <tagname>`: To delete the tag on the remote repository. 

**Creating a branch from a particular commit**  
`git checkout -b <branchname> <tagname>`: This command create a branch with the tag commit as the last commit on the branch.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 24. git stash
[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 25. git blame
`git blame` command is used to examine the contents of a file line by line an see when each line was last modified and who the author of the modification was. git blame only operates on individual files(i.e. it only display changes for one file at a time).

`git blame <filename>`

`git blame -L 1,5 <filename>`: `-L` flag is used to restrict the output to the request line range only.

`git blame -e <filename>`: `-e` flag is used to display users email address instead on username.

`git blame -w <filename>`: `-w` flag ignore changes that only contains white space.

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---
## 26. git bisect
[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)

---


## 27. git describe
`git describe` shows the most recent tag that is reachable from a commit. If the tag points to the last commit, then only the tag is shown. Otherwise, it suffixes the tag name with the "number of additional commit on top of the tagged object and the abbreviated commit of the most recent commit". By default git describe ony shows annotated tags. Example of git describe output `1.0-24-g31cdd0f`.

`git describe`: Show the most recent tag that is reachable from a commit.

`git describe --tags`: Instead of only using annoted tag, use any tag found. These option enables matching a light weight(non-annotated tag).

[Index](https://github.com/iam-rahul-sah/GitTutorials#git-tutorials)