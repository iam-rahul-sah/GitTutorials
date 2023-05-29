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

Note: A commit message should specify "WHAT" are the changes and "WHY" you have made the changes. 

- `git log` - Shows the commit history.
 
- `rm -rf .git` - Removes the git repository.

- `git clone <url>` - Clones the repository from the url to the local machine.

## GIT file status lifecycle

- Untracked - The file is not tracked by GIT.
- Unmodified - The file is tracked by GIT and is not modified.
- Modified - The file is tracked by GIT and is modified.
- Staged - The file is tracked by GIT and is staged for commit.

Once a git repository is initialized all the files inside it are untracked. Using `git add` we can add the files to the staging area. Once the files are added to the staging area, the files are tracked by GIT and are in the staged state. Once the files are committed, the files are in the unmodified state. If a file is in staging area and is modified, then the file co-exits in the staging area as well as the modified area. Commiting the file will capture the snapshot of the file in the staging area.

Example Step

1. A git repository is initialized(with name.md file) and the file is untracked.
1. The file is added to the staging area using `git add name.md` and the file is in the staged state.
1. The file is committed using `git commit` and the file is in the unmodified state.
1. The file is modified and the file is in the modified state.
1. The file is added to the staging area using `git add name.md` and the file is in the staged state.
1. The name.md file is again modified instead of commiting the file.
1. The file is in the modified state and the staged state(both co-exist).
1. The file is committed using `git commit` and the file in the staged state is captured in the local repository and the file in the modified state still exist in the modified state.