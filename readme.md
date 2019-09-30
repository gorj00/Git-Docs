# # Git Docs
## ## Basic Commands - Local Git Repository
### Git
- `git --version`,
- `git --help`

### Repository
- `git init`, 
  - run this command after navigaing to your folder, 
  - this will **initialize** a _git repository_ under **master** branch
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
  - information about commits (hashes, branch, head and so on),
  - opens an editor, press `q` to quit it
- `git checkout <commit-hash>`,
  - allows to **look** at previous state of the project under this particular commit and create a **detached HEAD**,
  - **to return back**: `git checkout <branch-name>` _(usually master)_
- `git reset --hard <commit-hash>`,
  - projects resets to a commit (a state) in the past, this commit becomes the HEAD of the branch, all changes and commits (project states) after this newly set HEAD are permanently lost
- `git checkout -- .`,
  - discard all **unstaged** and **uncomitted** changes (revert state of the project)

**Sequence of events**:
1. Create changes
    1. Working directory → Staging area (with _git add_)
1. Stage files with changes
1. Commit changes
    1. Staging area → Git repository (with _git commit_)

### Branching
- `git branch`,
  - lists the names of all branches and highlights the current branch
- `git checkout -b <branch-name>`,
  - creates new branch with a <branch-name> name
- `git checkout <branch-name>`,
  - switch to the <branch-name> branch
- `git branch -D <branch-name>`,
  - deletes branch from project permanently

### Merging 
To merge, we must be in a branch that will contain the merged two branches (usually master).
- `git checkout <branch-name-1>`, to switch to the branch wi want to make a merge upon,
- `git merge <branch-name-2>`, make a merge of branch-name-2 with branch-name-1

Merging can lead to conflicts, when resolved, commit the resolved change.

## ## GitHub - Remote Git Repository 
### Repositories Connection
- In GitHub, create a new repository,
- copy HTTPS .git address of the repository and insert it into the following command to **connect** the local and remote repository: 
- `git remote add origin <https-.git-address>`,
  - _origin_ is, by default, the name of the remote repository
- `git remote -v`,
  - lists the fetch and pull .git adress of _origin_ remote repository
- `git push -u origin master`,
  - pushes local branch to remote origin repository, master branch,
  - signing up to GitHub follows
- `git branch -r`,
  - lists remote branch in remote repository (usually _origin/remote_)
- `git branch -a`,
  - lists all branches - local and remote
- `git push`,
  - pushes commits to remote repository
- `git push --set-upstream origin <branch-name>`,
  - creates new upstream remote branch and pushes newly created local branch onto it
- `git push <remote-name> :<branch-name>`,
  - deletes remote branch,
  - _remote-name_ is usually _origin_

### Cloning & Syncing 
Cloning serves to another user (or computer) to join in on writing the code from another local repository.

- `git clone <https-.git-address>`,
  - creates a new local repository already synced with the remote repository
- `git pull`,
  - combination of commands: 
    - `git fetch`, fetches all of the branches of remote repository to the remote-tracking branch,
    - `git merge origin/master`, merges remote-tracking branch with local repository

**Repositories**: 
1. Remote repository
    1. with _git fetch_ (Remote → Remote-tracking)
1. In-between remote-tracking branches, connectors
1. Local repository
    1. with _git merge_ (Remote-tracking → Local)

