# # Git Docs
## ## Basic Commands - Local Git Repository
### Git
- `git --version`,
- `git --help`

### Repository
- `git init`, 
  - run this command after navigaing to your folder, 
  - this will **initialize** a _git repository_
- `git status`,
  - status of the current git repository (files tracked and untracked, commits and so on)

### Staging
- `git add <file-name>`,
  - add only <file-name> file from the folder to the tracking logic of git, 
  - aka **staging a file**
- `git add .`,
  - add all files from the folder to the tracking logic of git,
  - aka **staging all files**

### Committing
- `git commit -m "<message>"`,
  - commit changes and name this commit with a <message> name
  - **the lastest** commit is the **HEAD** of the branch
- `git log`,
  - information about commits (hashes, branch, head and so on)
- `git checkout <commit-hash>`,
  - allows to **look** at previous state of the project under this particular commit and create a **detached HEAD**,
  - **to return back**: `git checkout <branch-name>` _(usually master)_
- `git reset --hard <commit-hash>`,
  - projects resets to a commit (a state) in the past, this commit becomes the HEAD of the branch, all changes and commits (project states) after this newly set HEAD are permanently lost,
- `git checkout -- .`,
  - discard all **unstaged** and **uncomitted** changes (revert state of the project)

**Sequence of events**:
1. Create changes
  - Working directory → Staging area (with _git add_)
1. Stage files with changes
1. Commit changes
  - Staging area → Git repository (with _git commit_)

### Branching
- `git branch`,
  - _master_ is created automatically after repository initialization,
- `git checkout -b <branch-name>`,
  - creates new branch with a <branch-name> name
- `git checkout <branch-name>`,
  - switch to the <branch-name> branch

### Merging 
To merge, we must be in a **master branch**.
- `git merge <branch-name>`