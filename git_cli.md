
# git

theres alot of nuanced not explained if I just list a bunch of commands, so this made instead

first `git` and `github` are 2 **separated tools**

- (local) `git` tool for version control
- (remote) `github` **cloud based repository/database** for your git projects

other cloud based code repositories
- bitbucket (atlassian)
- gitlab
- sourceforge
each offer different extra features but let just stick with github for now, general interaction with each platform through `git` is identical
> you could also host your own git server

##  workflows

### setting up

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

  # then link it to a remote repo
  ```
  

