---
layout: post
title: 8 Basic GIT Commands Every Newbie Developer Must Know
author: gaurav
image: assets/images/2019-12-20-basic-git-commands/blog-cover.jpg
categories: [ GIT ]
description: GIT is one of the most important parts of the developer's day to day work. So learning GIT is a must for a newbie developer. In this article, you are going to learn the 8 most important basic GIT commands.
featured: true
hidden: true
---

GIT is one of the most important parts of the developer's day to day work. So learning GIT is a must for a newbie developer. In this article, you are going to learn the 8 most important basic GIT commands.

Below, I have listed down all the 8 commands and then, we will have a look at them one by one.

1. [`git init`](#git-init)
2. [`git clone`](#git-clone)
3. [`git add`](#git-add)
4. [`git commit`](#git-commit)
5. [`git status`](#git-status)
6. [`git branch`](#git-branch)
7. [`git pull`](#git-pull)
8. [`git push`](#git-push)

## 1. `git init`
`git init` command initializes brand new GIT repository (locally) and begins tracking the existing directory.

When you hit the `git init` command, git adds a subfolder withing an existing directory that manages all required files for version controlling.

```
HP@Gaurav MINGW64 /e/example
$ git init
Initialized empty Git repository in E:/example/.git/

HP@Gaurav MINGW64 /e/example (master)
$
```

You are hitting `git init` means you want to initialize the current directory as GIT repository.
 
The following GIF show initializing a new repository and a hidden subfolder containing all data structure required for version control. 

![GIF showing git init command](/assets/images/2019-12-20-basic-git-commands/git-init.gif)
 
## 2. `git clone`

`git clone` creates a local copy of a repository that already exists remotely. The local copy is the exact copy of the remote repository, it contains the same files, history, and branches.

```
$ git clone <remote-repository-link>
```
```
HP@Gaurav MINGW64 /e/directory
$ git clone https://github.com/gauravkukade/example.git
Cloning into 'example'...
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 16 (delta 3), reused 7 (delta 2), pack-reused 0
Unpacking objects: 100% (16/16), done.

HP@Gaurav MINGW64 /e/directory
$
```

You can clone any public repository from the platforms like GitHub,  BitBucket, GitLab, and other GIT hosting platforms.

The following GIF shows the `git clone` command

![GIF showing git clone command](/assets/images/2019-12-20-basic-git-commands/git-clone.gif)

## 3. `git add`

`git add` stages a change.

If you are done with changes in your code then its necessary to stage that changes and take a snapshot of it to include it in the repository's history.

`git add` does the first step, it stages a change.

```
$ git add <path-of-the-file-you-made-changes-in>
```
If you made changes in the multiple files and you want to stage all files in the same command then add the file path of all files separated y a single space.

```
$ git add <first-filepath-you-want-to-stage> <second-filepath-you-want-to-stage> <nth-filepath-you-want-to-stage>
```
If you want to stage all the files, then write '.' (dot) after `git add`
```
$ git add .
``` 
Any staged changes will become the part of the next snapshot and a part of the repository's history.

You can stage and take a snapshot of the current changes in a single command also but is not recommended.

Staging your changes first and then taking snapshot gives you complete control over the repository's history. 

The following GIF shows the `git add` command

![GIF showing git add command](/assets/images/2019-12-20-basic-git-commands/git-add.gif)

## 4. `git commit`
 `git commit` save the snapshot to the repository's history.

`git add` does the first step i.e. staging the changes and `git commit` does the final step i.e. it saves the snapshot to the repository's history. In GIT these two-step completes the changes tracking process.

```
$ git commit -m "<meaningful-git-commit-message>
```

You can write a meaningful message to the commit. It is recommended to write a commit message in the 'Simple Present Tense'.

If you are committing a new feature to your project then your commit message should be `"Add <feature-name> feature"`.

The following GIF shows the `git commit` command

![GIF showing git commit command](/assets/images/2019-12-20-basic-git-commands/git-commit.gif)

It is the simple way to write the commit message but there is a more in-depth way to write a commit message with title and description. We will see that in a separate blogpost.

## 5. `git status`

`git status` shows the status of the changes as untracked, modified or staged.
```
HP@Gaurav MINGW64 /e/directory/example (master)
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        ex.txt


HP@Gaurav MINGW64 /e/directory/example (master)
$

```
The following GIF shows the `git status` command

![GIF showing git status command](/assets/images/2019-12-20-basic-git-commands/git-status.gif)

## 6. `git branch`
`git branch` list the existing branches from the local repository. The current branch will be highlighted in green and marked with an asterisk.

```
HP@Gaurav MINGW64 /e/directory/example (master)
$ git branch
* master
  new_branch

HP@Gaurav MINGW64 /e/directory/example (master)
$
```
The following GIF shows the `git branch` command

![GIF showing git branch command](/assets/images/2019-12-20-basic-git-commands/git-branch.gif)

## 7. `git pull`

`git pull` update the local repository with updates from its remote counterpart. i.e. remote repository.
```
HP@Gaurav MINGW64 /e/directory/example (master)
$ git pull
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/gauravkukade/example
   15e8755..d7aefb1  master     -> origin/master
Updating 15e8755..d7aefb1
Fast-forward
 new-file-added-to-remote-repository.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 new-file-added-to-remote-repository.txt

HP@Gaurav MINGW64 /e/directory/example (master)
$

```
If your teammate made commits to the remote branch and you want to reflect these changes in your local environment then you will hit the command `git pull`.

This command will check if there are any updates on the remote branch as compared to your local environment, if yes, then it will update your local environment with these changes. If no, then it will do nothing.

The following GIF shows the `git pull` command

![GIF showing git pull command](/assets/images/2019-12-20-basic-git-commands/git-pull.gif)

## 8. `git push`

`git push` updates the remote repository with any commits made locally to a branch

```
$ git push origin <branch-name-you-have made commits on>
```
If the branch does not exist on a remote repository then the whole branch with its commits will be pushed to the remote repository.
```
$ git push origin <newly-locally-created-branch-name>
```
```
HP@Gaurav MINGW64 /e/directory/example (master)
$ git push origin master
fatal: HttpRequestException encountered.
   An error occurred while sending the request.
Username for 'https://github.com': gauravkukade
Counting objects: 2, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 255 bytes | 255.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/gauravkukade/example.git
   d7aefb1..dc3d3ef  master -> master

HP@Gaurav MINGW64 /e/directory/example (master)
$
```
The following GIF shows the `git push` command

![GIF showing git push command](/assets/images/2019-12-20-basic-git-commands/git-push.gif)

You are here means you like the post and hence here is your bonus content.

### How to create a new branch locally

You can create a new branch locally using the following command
```
$ git checkout -b <your-new-branch-name>

```

![How to create new branch](/assets/images/2019-12-20-basic-git-commands/git-new-branch.gif)

If you found this article worth, please [Give me a cup of Coffee ☕](https://www.paypal.me/GauravKukade)

If you have queries please let me know in the comment section below.
