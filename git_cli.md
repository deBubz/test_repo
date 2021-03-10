
# git

first `git` and `github` are 2 **separated tools**

- (local) `git` tool for version control
- (remote) `github` **cloud based repository/database** for your git projects

other cloud based code repositories
- bitbucket (atlassian)
- gitlab
- sourceforge

each offer different extra features but let just stick with github for now, general interaction with each platform through `git` is identical
> you could also host your own git server

- [git](#git)
  - [workflows](#workflows)
    - [setting up git](#setting-up-git)
    - [saving new changes](#saving-new-changes)
    - [updating local with new remote changes](#updating-local-with-new-remote-changes)
    - [branches](#branches)
    - [merging](#merging)
  - [advanced?? stuff?](#advanced-stuff)

##  workflows

> ofc theres more nuances in these commands, so just google `any git command` to learn more.
>
> this is all the stuff i use

### setting up git

Theres 2 ways of setting up a project to work on your local machine

- clone an existing project on a repo
```
git clone <repo_url>
```

- create a new project *locally* and link it to a new repo
  ```bash
  # either `cd` into your project folder and run
  git init
  # or do this
  git init <new_project folder>

  # NEXT link to remote repo
  # note you can have multiple remote repo linked to 1 project
  git remote add origin <path_to_remote_git_repo>
  # set default branch to master
  git branch -M master
  # set upstream branch (first ever push)
  git push --set-upstream origin master
  ```

### saving new changes

- to check the status of the project, while anywhere in the project folder
  ```bash
  # compare your work with the latest commit, showing
  ## any new changes
  ## anything not staged
  ## last push
  git status
  ```
- commit(take a snapshot) new changes
  ```bash
  # add individual file into staging
  git add <filename>
  # or add everything
  git add *

  # THEN commit with a message
  ## each commit requires a message to state what it is
  ## also commit often
  git commit -m "message"
  ```
- push changes to remote (cloud repo)
  ```bash
  # theres no need to push every commit
  # think of this as uploading your code into github
  # all your previous commits will also be uploaded
  git push
  ```

### updating local with new remote changes

simply running `git status` will not work, as it is just comparing your files against the latest commit

so to check if you have any remote changes in the same branch

```bash
git fetch -a

# then run status to check status
git status

# if theres any new changes, grab it with
git pull
```

### branches

> I recommend to use GUI tools such as `GitKraken` to visualize the branches, and see what is happening

- creating a new branch then switch to it
  ```bash
  git checkout -b <new_branch_name>
  # this just create another branch LOCALLY
  # to push it into the remote repo
  git push --set-upstream origin <new_branch_name>
  ```
- list all branches
  ```bash 
  git branch
  # this brings you into another program listing all the branch
  # the branch you are currently on is marked with a *
  # press q to exit
  ```
- swapping to another branch
  ```bash
  git checkout <branch_name>
  ```

### merging

> ill do this *later*, remind me if i forgot
>
> easiest way is just make a pull request on github, or google it

## advanced?? stuff?

If youre gonna use CLI alot, set up some `alias` or script to reduce the keystrokes

heres my `alias` (maybe different for windows)
```bash
alias gst="git status"
alias gfa="git fetch -a"
alias gaa="git add *"
alias gcam="git commit -m"
alias gp="git push"
alias gpl="git pull"
alias gqa="git add * && git commit -m"
```