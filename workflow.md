# # Development Workflow

**RULES**: 
- Never make commits to master or dev branch (development related).

## ## Workflow:
1. Create branches ONLY from dev branch, never master or any other!
1. All branches names must be **lower case**, words separated by a **dash**, example `bugfix/password-input-not-validating`.
1. All branches must start with either `feature` or `bugfix`, followed by a slash `/` and the name of the branch: 
    - feature/name-of-branch
    - bugfix/name-of-branch
4. After work is done on a feature or bugfix branch, it is better that all possible conflicts are resolved before merging with **dev** branch, therefore:
    - After you are **done**, merge dev branch with your feature or bugfix branch locally, resolve conflicts and commit.
    - Only after that, you may create a pull request to a dev branch, see **CREATE NEW PULL REQUEST** section for more information.

## ## Create NEW feature or bugfix remote branch...
1. **OPEN YOUR PROJECT**: Open the folder with Sportify project in your editor.
1. **GO TO DEV BRANCH**: Checkout to dev branch with `git checkout dev`
1. **UPDATE DEV BRANCH**: Update the dev branch locally with `git pull`
1. **CREATE NEW BRANCH LOCALLY**: Create new branch from dev branch with `git checkout -b feature/sign-in-page` (example)
1. **CREATE NEW BRANCH REMOTELY**: Create remote branch on GitHub with `pit push -u origin feature/sign-in-page` (example)

## ## ... or continue working on already EXISTING remote branch:
    - for example, when you continue somebody else's work, 
    - or you continue your work on another computer and so on... 

1. **OPEN YOUR PROJECT**: Open the folder with Sportify project in your editor.
1. **GO TO DEV BRANCH**: Checkout to dev branch with `git checkout dev`
1. **UPDATE DEV BRANCH**: Update the dev branch locally with `git pull`
1. **CREATE CONNECTION**: Create local branch and connect it to the remote branch with `git checkout --track origin/feature/sign-in-page` (example)

## ## Create new pull request:
### Pull requests rules:  
- Every pull request to dev branch must have two reviewers other than yourself, one of them must be Jan Gorol. 
- Every pull request to master branch must have Dominik Šnýdr as a reviewer.
- Every pull request's labels must match labels in trello.
- Every pull request's milestone must match the current sprint.

### Steps:
1. Make sure everything is working the way it is supposed to, go through your code and check it.
1. Check, whether your branch would be in conflict with dev branch:
    - go to dev branch with `git checkout dev`, merge updates with `git pull`
    - go back to your feature or bugfix branch with `git checkout feature/your-branch-name`, 
    - merge dev branch into your feature or bugfix branch with `git merge dev`
    - resolve possible conflicts
1. Go to [our pull request page](https://github.com/jaroslavVeverka/Sportify_9/pulls), create new pull request
1. TODO: !!!! FINISH 