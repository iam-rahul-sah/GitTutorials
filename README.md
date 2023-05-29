# GIT tutorials

## GIT introduction

### Why is GIT around?

It is a version control system. It is used to track changes in files and directories. 
 
**Features of GIT:**
1. Easily recoverable.
1. Who introduced an issue and when?
1. Roll back to previously working state.

**History of VCS:**

- Local VCS:Uses DB and keep track of files, locally on the computer.
    - Pros: Can track files and rollback to previous versions.
    - Cons: Files are stored locally, so there are chances of losing data.
- Centralized VCS:Uses a central server to store all files and enables team collaboration.
    - Pros: Can track files and rollback to previous versions. Can collaborate with team members.
    - Cons: If the central server goes down, then no one can collaborate or track files.
- Distributed VCS: Each and every person contributing to the source code has a copy of the version of the source code. Also storing the history  of the codebase.

**Distinctive features of GIT for other VCS:**
1. It captures snapshot and not the file differences.
1. Almost all operations are local.
1. Integrity of data.
1. GIT has three main states that your files can reside in: committed, modified, and staged.
1. Git generally only adds data to the repository.


## Setting GIT for usage.

- `git config --global user.name "John Doe"`
- `git config --global user.email = "johndoe@gmail.com"`
- `git config --list`

## GIT - Three stage architecutre

commit - It is the process of saving the changes to the local repository through means of capturing a snapshot of the project.

![img](/threeStageArch.png)

- Working directory - It is the directory where the files are stored and the changes are made.
- Stagging area - It is the area where the files are staged for commit.
- Local repository - It is the area where the files are stored after commit.

## Getting started - Tracking your file

- `git init` - Initializes the git repository.

- `git status` - Shows the status of the files in the working directory.

- `git add <file>` - Adds the file to the staging area. Multiple file names are seperated by comma. We can also use `git add .`  or `git add --a` to add all the files in the working directory to the staging area.

- `git commit` - Commits the files in the staging area to the local repository. We can also use `git commit -m "message"` to add a message to the commit in the terminal itself or else it will open the default editor to add the message.  

**Note**: A commit message should specify "WHAT" are the changes and "WHY" you have made the changes. 

- `git log` - Shows the commit history.
 
- `rm -rf .git` - Removes the git repository.

- `git clone <url>` - Clones the repository from the url to the local machine.

## GIT file status lifecycle

- Untracked - The file is not tracked by GIT.
- Unmodified - The file is tracked by GIT and is not modified.
- Modified - The file is tracked by GIT and is modified.
- Staged - The file is tracked by GIT and is staged for commit.
- committed - The file is tracked by GIT and is committed to the local repository.

Once a git repository is initialized all the files inside it are untracked. Using `git add` we can add the files to the staging area. Once the files are added to the staging area, the files are tracked by GIT and are in the staged state. Once the files are committed, the files are in the unmodified state. If a file is in staging area and is modified, then the file co-exits in the staging area as well as the modified area. Commiting the file will capture the snapshot of the file in the staging area.

![File status lifecycle](/fileStatusLifecycle.png)

*Example Step*:

1. A git repository is initialized(with name.md file) and the file is untracked.
1. The file is added to the staging area using `git add name.md` and the file is in the staged state.
1. The file is committed using `git commit` and the file is in the unmodified state.
1. The file is modified and the file is in the modified state.
1. The file is added to the staging area using `git add name.md` and the file is in the staged state.
1. The name.md file is again modified instead of commiting the file.
1. The file is in the modified state and the staged state(both co-exist).
1. The file is committed using `git commit` and the file in the staged state is captured in the local repository and the file in the modified state still exist in the modified state.


## .gitignore file

.gitignore file is used to ignore the files that are not required to be tracked by GIT. The files that are ignored are not tracked by GIT and are not shown in the `git status` command.

### .gitignore file syntax
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

**Note**: `Blank folder` or folder only containing igonred files are by default igonred by GIT.

**Note**: If a file is already tracked by GIT and is added to the .gitignore file, then the file will still be tracked by GIT. To stop tracking the file, we need to remove the file from the staging area using `git rm --cached <filename>` and commit the changes.

## GIT diff

- `git diff` - Shows the difference between the modified version(there should be a modified verison of the file or it does not yield any result) of a file and the staged version of the file(if one exists or the committed version of the file)
- `git diff --staged` - Shows the difference between the staging area and the local repository.


## Skipping the staging area

- `git commit -a -m "message"` - This command skips the stagging area and directly commits all the files from the modified section to the local repository. This command does not add the untracked files to the staging area. This command does not work for new files. This command is not recommended as it does not give a chance to review the changes before commiting.

## Moving and Renaming files

- `git mv <filename> <newfilename>` - Moves the file to the new file name. This command is equivalent to `mv <filename> <newfilename>` 
- `git rm <filename>` - Removes the file from the working directory. This command is equivalent to `rm <filename>`

**Note**: These command are equivalent to there linux commands. The only difference is that the git command autoamatically tracks the changes and add these changes to the staging area to be commited.

## Viewing commit history and difference between the commits.

- `git log -p`  
This command shows all the difference between the consecutive commits.

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

### Difference between author and commit

**Author** - The one user who has created the file is the author of the file.  
**Commit** - The one who has made changes and commited the file.

### Filtering commit history using days

- `git log  --since = 2 days` - This command displa the commit from the last two days. We can also use 2 months, 2 weeks, 2 years.
- `git log --pretty=format:"%h -- %an"` - This command will show the log in a format specified by the user after (:) using format pattern

Refer official git documentation for the format pattern

### Amending a commit

- `git commit --amend` - This command will help us to commit new made changes to the previous commit. We can also change the message of the commit.
- `git commit --amend -m "messaage"` - This will change the message and the commited files in the terminal itself.


## Unstaging or unmodifying files

- `git restore --staged <file>` - This command is used to move file from staging are back to modified file section(i.e. for unstaging the files)
- `git checkout -- <file>` - This is another commit used to unstage the file
- `git restore <file>` - This command is used to discard any changes in the file. It moves files from modified file section to unmodified file section. The changes to the unstaged files(modified file) is discarded and the files is restored to the version of the file from the previous commit.

**Note**: We can use "." flag with the `git restore` command to specify all the file at once, and the "-f" flag with `git checkout` command to specify all the file at once.

## Working with remote repositories

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

### Step to get access to your git account from your PC.

1. Setting > SSH and GPG keys > New SSH key
1. Add title to SSH key
1. We need to add the SSH keys but first we need to generate a SSH key

### Steps for creating SSH key in your PC

1. `ssh-keygen -t ed25519 -c "your email address"` - To generate the SSH key. 
1. `eval $ (ssh-agent -s)` - To ensure if the ssh agent is running.
1. `ssh-add ~/.ssh/id_rsa` - Adding ssh private key to the SSH agent.
1. `tail ~/.ssh/idrsa.pub` - Command to display ssh key

Now we can add this generated SSH key to our git account.

- `git fetch` - This command is used to update or fetch any changes int he remote repository.
- `git pull` - This command is used to update your git version history similar to the remote repository.
- `git push` - This command is used to update remote repository version similar to your PC's git version.