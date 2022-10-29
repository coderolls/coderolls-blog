---
layout: post  
title: "GIT Cheat Sheet"  
author: gaurav
categories: [GIT, Cheat Sheet, GIT Basic]
toc: true
description: "A cheat sheet for GIT, a free and open source software for distributed version control."
---

A cheat sheet for [GIT](https://git-scm.com/), a free and open source software for distributed version control.

## Create Repository

Clone an existing repository

```bash
git clone https://github.com/username/repository-name.git
```

Create a new local repository

```bash
git init
```



## Local Changes

See changed files in your working directory

```bash
git diff
```

See changes in a particular file in your working directory

```bash
git diff <complete-file-path>
```

### Stage Changes

Add local changes of a file to next commit (Stage changes from a file)

```bash
git add <complete-file-path>
```

Add all local changes to next commit (Stage all changes from all files)

```bash
git add .
```

### Commit Changes

Commit (commit previously staged changes)

```bash
git commit
```

Above command will open a vim prompt to add a commit message title and commit message description. 

If you want to commit without entering the vim prompt, use below command.

```bash
git commit -m "<commit-messaege-title>"
```

How to commit all local changes ( even if they are not staged)

```bash
git commit -a
```

How to make changes in last commit

```bash
git commit --amend
```

> **Note**: The above command will not amend published commits.



### Stash Changes

Stash local changes

```bash
git stash
```

Stash local changes with a message

```bash
git stash save "<message>"
```

List all stashes

```bash
git stash list
```

Reapply previously stashed changes

```bash
git stash apply
```

Reapply a particular stash from the list

```bash
git stash apply stash@{2}
```

> `stash@{2}` is stash identifier

Reapply the latest stashed changes and removes it from your stashes

```bash
git stash pop
```

Reapply a particular stash and removes it from your stashes

```bash
git stash pop stash@{2}
```

> `stash@{2}` is stash identifier

View a summary of a stash

```bash
git stash show
```

Delete all of your stashes

```bash
git stash clear
```



## Commit History

Show all commits of a repository , newest first

```bash
git log
```

Show changes over time for a specific file

```bash
git log <file-path>
```

Check who changed what and when in a specific file

```bash
git blame <file-path>
```



## Branches and Tags

### Branches

List all local branches

```bash
git branch
```

List all local and remote branches

```
git branch -a
```

Switch HEAD branch

```bash
git checkout <branch-name>
```

Create a new branch from the current HEAD branch

```bash
git branch <branch-name>
```

Create a new branch from the current HEAD branch and Switch to new branch

```bash
git checkout -b <branch-name>
```

Create a new tracking branch based on a remote branch

```
git checkout --track <remote/branch> 
```

[Delete a local git branch](/delete-a-git-branch-local-or-remote/#how-to-delete-a-local-git-branch)

```bash
git branch -d <local-branch-name>
```

[Delete a remote git branch](/delete-a-git-branch-local-or-remote/#how-to-delete-a-remote-git-branch)

```bash
git push <remote> --delete <branch-name>
```

>**Note:** In most of the cases the `<remote>` is `origin`.

### Tag

Mark a current commit with tag

```bash
git tag <tag-name>
```



## Update and Publish

List all currently configured remotes
```bash
git remote -v
```


Show information about a remote
```bash
git remote show <remote>
```


Add new remote repository
```bash
git remote add <remote> <url>
```

Change the url of an existing remote repository:

```bash
git remote set-url <remote> <url>
```

Download all changes from <remote>, but don't integrate into HEAD

```bash
git fetch <remote>
```

Download changes and directly merge/integrate into HEAD
```bash
git pull <remote> <branch>
```

Publish local changes on a remote
```bash
git push <remote> <branch>
```

Delete a branch on the remote
```bash
glt branch -dr <remote/branch>
```

Publish your tags
```bash
git push tags
```

>  **Note:** In most of the cases the `<remote>` is `origin`.



## Merge and Rebase

Merge <branch> into your current HEAD
```bash
git merge <branch>
```

Rebase your current HEAD onto <branch>
```bash
git rebase <branch>
```

Abort a rebase
```bash
git rebase --abort
```

Continue a rebase after resolving conflicts
```bash
git rebase --continue
```

Use your configured merge tool to solve conflicts
```bash
git mergetool
```

Use your editor to manually solve conflicts and (after resolving) mark file as resolved

In case of adding file

```bash
git add <resolved-file>
```

In case of removing file
```bash
git rm <resolved-file>
```



## Undo

Discard all local changes in your working directory

```bash
git reset --hard HEAD
```

Discard local changes in a specific file
```bash
git checkout HEAD <file>
```

Revert a commit (by producing a new commit with contrary changes)
```bash
git revert <commit>
```

Reset your HEAD pointer to a previous commit
...and discard all changes since then

```bash
git reset --hard <commit>
```

...and preserve all changes as unstaged changes
```bash
git reset <commit>
```

..and preserve uncommitted local changes
```bash
git reset --keep <commit>
```