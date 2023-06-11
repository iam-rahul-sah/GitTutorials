# GIT Tutorials

**Index**
1. Git introduction
    - Why is GIT around?
    - Features of GIT
    - History of VCS
    - Distinctive features of GIT from other VCS
2. Setting GIT for usage
3. GIT - Three stage architecture
4. Getting started - Tracking your file(Basic and most common git command)
5. GIT file status lifecycle
6. .gitignore file
7. GIT diff
8. Moving and Renaming files
9. Viewing(logging) commit history and difference between the commits.
10. All about git commit
11. Unstaging or unmodifying files
12. Setting alias in git
13. Working with remote repositories
14. All about branches in GIT.
15. Merge
16. Merge conflict
17. Git squash
18. Interactive rebase
19. Cherry picking 
20. Reflog
21. Submodules
22. git revert reset
23. git tag
24. git stash
25. git blame
26. git bisect
27. git diff-tree

---

## 1. GIT introduction

**Why is GIT around?**  
It is a version control system. It is used to track changes in files and directories. 
 
**Features of GIT:**
1. Easily recoverable.
1. Who introduced an issue and when?
1. Roll back to previously working state.

**History of VCS:**  
- *Local VCS*:Uses DB and keep track of files, locally on the computer.
    - Pros: Can track files and rollback to previous versions.
    - Cons: Files are stored locally, so there are chances of losing data.
- *Centralized VCS*:Uses a central server to store all files and enables team collaboration.
    - Pros: Can track files and rollback to previous versions. Can collaborate with team members.
    - Cons: If the central server goes down, then no one can collaborate or track files.
- *Distributed VCS*: Each and every person contributing to the source code has a copy of the version of the source code. Also storing the history  of the codebase.

**Distinctive features of GIT from other VCS:**
1. It captures snapshot and not the file differences.
1. Almost all operations are local.
1. Integrity of data.
1. GIT has three main states that your files can reside in: committed, modified, and staged.
1. Git generally only adds data to the repository.

---

## 2. Setting GIT for usage.

- `git config --global user.name "John Doe"`
    - Setting the user name to be displayed in the commit.
- `git config --global user.email = "johndoe@gmail.com"`
    - setting the user email address to be displayed in the commit.
- `git config --list`
    - To display the list of configuration option for the user either globally or for a particualar directory.

---
## 3. GIT - Three stage architecutre

*commit* - It is the process of saving the changes to the local repository through means of capturing a snapshot of the project.

![img](/images/threeStageArch.png)

- *Working directory* - It is the directory where the files are stored and the changes are made.
- *Stagging area* - It is the area where the files are staged for commit.
- *Local repository* - It is the area where the files are stored after commit.

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

---

## 5. GIT file status lifecycle

- *Untracked* - The file is not tracked by GIT.
- *Unmodified* - The file is tracked by GIT and is not modified.
- *Modified* - The file is tracked by GIT and is modified.
- *Staged* - The file is tracked by GIT and is staged for commit.
- *committed* - The file is tracked by GIT and is committed to the local repository.

Once a git repository is initialized all the files inside it are untracked. Using `git add` we can add the files to the staging area. Once the files are added to the staging area, the files are tracked by GIT and are in the staged state. Once the files are committed, the files are in the unmodified state. If a file is in staging area and is modified, then the file co-exits in the staging area as well as the modified area. Commiting the file will capture the snapshot of the file in the staging area.

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

---
## 6. Unstaging or unmodifying files

- `git restore --staged <file>` - This command is used to move file from staging are back to modified file section(i.e. for unstaging the files)
- `git checkout -- <file>` - This is another commit used to unstage the file
- `git restore <file>` - This command is used to discard any changes in the file. It moves files from modified file section to unmodified file section. The changes to the unstaged files(modified file) is discarded and the files is restored to the version of the file from the previous commit.

**Note**: We can use "." flag with the `git restore` command to specify all the file at once, and the "-f" flag with `git checkout` command to specify all the file at once.

**Deleting a file from being tracked**

**Note**: `git restore` command cannot be used to move a file from "staged files" to "untracked files". To move a file from "staged file" to "untracked files" we need to use '`git rm --cached <filename>`'. Though in order to use "." to specify all the file we need to use "-r" flag to specify files to be deleted recursively. `git rm --cached -r .`.

--- 

## 7. .gitignore file

".gitignore" file is used to ignore the files that are not required to be tracked by GIT. These files are not shown in the `git status` command.

**.gitignore file syntax**

`<filename with extension>`  
`<directoryname>`  
`<pattern>`  
`!` - To unignore the file.  
`*.ext` - To ignore all files in the directory. With the specified extension.  
`*` - To ignore all files in the directory.  
`**` - To ignore all files in the directory and subdirectories.  
`/` - To ignore the directory.  
`#` - To add comments.  
`dir/` - To ignore the directory.  
`/dir/` - only ignores the 'dir' in the root folder, rest 'dir' within directories and sub-directories will be tracked.  

**Note**: `Blank folder` or folder only containing igonred files are by default ignored by GIT.

**Note**: If a file is already tracked by GIT and is added to the .gitignore file, then the file will still be tracked by GIT. To stop tracking the file, we need to remove the file from the git repository using `git rm --cached <filename>` and commit the changes.

---
## 8. GIT diff

- `git diff` - Shows the difference between the modified version(there should be a modified verison of the file or it does not yield any result) of a file and the staged version of the file(if one exists or the committed version of the file)
- `git diff --staged` - Shows the difference between the staging area and the local repository.


---
## 9. Moving and Renaming files

- `git mv <filename> <newfilename>` - Moves the file to the new file name. This command is equivalent to `mv <filename> <newfilename>` 
- `git rm <filename>` - Removes the file from the working directory. This command is equivalent to `rm <filename>`

**Note**: These command are equivalent to there linux commands. The only difference is that the git command autoamatically tracks the changes and add these changes to the staging area to be commited.

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

**Author** - The one user who has created the file is the author of the file.  
**Commit** - The one who has made changes and commited the file.

**Filtering commit history using days**

- `git log  --since = 2 days` - This command display the commit from the last two days. We can also use 2 months, 2 weeks, 2 years.

**Displaying commit history in a particular format**
- `git log --pretty=format:"%h -- %an"` - This command will show the log in a format specified by the user after (:) using format pattern

Refer official git documentation for the format pattern

---

### 11. All about git commit

- `git commit` - Commits the files in the staging area to the local repository. We can also use `git commit -m "message"` to add a message to the commit in the terminal itself or else it will open the default editor to add the message. 

**Amending a git commit(changing your last commit)**
- `git commit --amend` - This command will help us to commit new made changes to the previous commit. We can also change the message of the commit.
- `git commit --amend -m "messaage"` - This will change the message and the commited files in the terminal itself.

**Skipping the staging area**

- `git commit -a -m "message"` - This command skips the stagging area and directly commits all the files from the modified section to the local repository. This command does not add the untracked files to the staging area. This command does not work for new files. This command is not recommended as it does not give a chance to review the changes before commiting.

**The perfect commit**

1. Add only the right changes to the commit(i.e. changes that are specific to that commit)
1. Compose a good commit message

- Not to do - Not just cram everything into one single commit.

**Note** - Once commit should only include change to a specific topic.

- Use staging are to select files that are related to changes for a specific topic and then do a commit. We can consequently make other commit for other changes.

**Adding a patch of code to the stagging area:**

Patch: A part or small chunck of code that you have changed.

- `git add -p <filename>`

Now git ask if we want to add the patch to staging area or not for each patch consecutively. Press 'Y' for yes or 'n' for no.

**The perfect commit message**
1. Subject = Concise summary of what happened.
1. Body = More detailed explanation(what is now different than before)

**Creating a commit message with a subject and a body**

When we commit a message in our code editor. The first line of commit is the subject then we have to leave one line after that and now we can add a body to the commit.


---

## 12. Setting alias in git

- `git config --global alias.shortcut_key git_command` - This command is used to set alais for a git command

**Example** - `git config --global alias.st status` - Command to create 'st' as a shortcut for status.

**Note** - For a command with multiple word we need to enclose it within quotes.

**Example** - `git config --global alias.unstage 'restore --staged --'` - Here "--" is necessary as it take additional argument as file name or else it won't work.

**Example** - `git config --global alias.last 'log -p -1'`

---
## 13. Working with remote repositories

1. Click on the "+" icon in the top-right corner
1. Click on 'New repository'
1. Enter the details like name, description
1. Click on create repository

A new window for quick setup appears

A remote server is a server hosting your git project somewhere on the internet.
- `git remote` - This command is used to setup and view the remote servers.
- `git remote add origin "your repository url"` - This command is used to add an url for the remote repository.
- `git remote -v` - This command is used to display all the url for the remote repository.


*Pull* - Pull command is used to fetch any changes made on the remote server to your local version. A pull command does a `git fetch` followed by a `git commit`
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

**Fork**
A fork is a personal copy of a git repository. By creating a "fork" of the original repository, where you can make changes, and then you can suggest those changes to be included via pull request to the main repository.

**--set-upstream flag**

`git push --set-upstream origin <branchname>`

--set-upstream  flag sets a default branch for you local branch. Every branch can have an upstream/default branch on the remote. So whenever they push or pull they do not need to specify the branch like `git push origin master` they can just use `git push`. These(i.e. setting upstream) also keep your branch in sync with the remote repository.

---

## 14. All about branches in GIT.

A branch is a local copy of your code base where you can make changes without affecting your original code. These changes can later be integrated into your main workflow if everything goes well.

**Branching startegies**

A written convention - Agree on a branching workflow in your team.

**Why to do this -** 

1. Git allows you to create branches - but it doesn't tell you how to use them.
1. You need a written best practice of how to work that is idealy structured for your team to avoid mistakes and collisions.
1. It highly depends on your team, team size, on your project and how you handle releases.
1. It hels to onboard new team member.


**Startegies for integrating changes and structuring releases.**

*Mainline development*("Always be integrating")
- Few branches
- Relatively small commits
- High - quality testing and QA standards(since the commit are directly added to main branch)

*state, release and feature Branches*

Branches enhance structures and workflows of the development.
Different type of branches, fulfill differeent types of jobs

**Types of branches**

1. Long running branches - Exist through the complete lifetime of the project. Often, they mirror "stages" in your dev life cycles.

*Common convention*: No direct commit(only through merge and rebase)

2. Short lived branches - For new features, bug fixes, refactoring, experiments. Branches are deleted after integration.

**Github flow - very simple, very lean: only one long-running branch("main") + feature branches.**

**How to work with branches.**

- "Head" branch - Currently 'active' branch

1. Creating new branch(based on current) "Head" branch
- `git branch <new branch name>`
- `git checkout -b <branchname>` - This command switches a branch if one exits or else create a new branch and then switches to the new branch.
- `git checkout <branchname>` - This command switches to the specified branch(if one exists) or throws an error if one does not exist.
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
-u specifies to keep track of remotee branch, so next time we can use "git push" simply.

7. Tracking branches(connecting branches with each other)
```
$ git branch --track <new-branch> origin/<base-branch>

    or 

$ git branch --track origin/<base-branch>
```

8. Checking status of your branches  
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










## Git merge and squash

commit history of a code base

![commit history of a code base](/images/branching_workflow.png)

- Git merge - using only `git merge <branchname>`, will do something like this.

![simple merge command](/images/merging_using_simple_merge.png)

- To achieve a simple straight commit history we need to use `git merge --squash <branchname> -m "message"`

![merge using squash](/images/merge_using_squash_flag.png)


## Merge conflict

- `git branch -v` - This command returns the commit hash along with the message for the last commit in all the branch. It is useful to check if our commit are in unison or not.
- `git branch --merged` - This command returns the list of branches that have been already merged to your current branch.
- `git branch --no-merged`

