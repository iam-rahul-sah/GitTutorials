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

