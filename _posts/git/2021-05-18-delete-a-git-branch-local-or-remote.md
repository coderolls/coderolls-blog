---
layout: post
title: "How To Delete A Git Branch (Local or Remote)"
author: gaurav
categories: [Java, Array]
description: "In this article, we will see how to delete a Git Branch both locally or remotely."
---
In this article, we will see how to delete a GIT branch both locally or remotely.

Short Snippet

```git
// if you finished working on branch, and merged
git branch -d <the-local-branch>

// delete local branch without checking merged status
git branch -D <the-local-branch>

// delete remote branch (Git v1.7.0 and above)
git push origin --delete <the-remote-branch>

// delete remote branch (old syntax)
git push origin :<the-remote-branch>

```

## Introduction

GIT is one of the most used software for version control. In GIT, branches are part of the day-to-day development process. A Git branch represents an independent line of development.

If you are beginner I would recommend you to have a look at [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/) .

Usually, all repositories have a `main/master` branch for the main code and team members create a feature or bug fix branches from the `main/master` branch.

You add your feature or adds a bug-fix to your branch and commit the changes and push it to the remote branch. You will create a pull request and your team lead will review your code and merged it to the `main/master` .

Since you have finished working on your branch you can choose to delete it.

## How To Delete A Local Git Branch?

When you finished working on the feature or bug fix and your branch is merged to the master, you can use the following command to delete a local GIT branch

```git
git branch -d <the-local-branch>
```
**For example**, If I need to delete my local Git branch `fetaure/add-profile`, I will hit the following command 

```git
git branch -d fetaure/add-profile
```
When you want to delete a GIT branch without checking the merged status, hit the command given below 
```git
git branch -D <the-local-branch>
```
**For example**, If I need to delete my local Git branch `fetaure/add-profile` without checking its merged status, I will hit the following command

```git
git branch -D fetaure/add-profile
```

## How To Delete A Remote Git Branch

If you are using the GIT v1.7.0 and above, hit the following command to delete the remote git branch

```
 git push <remote_name> --delete <branch_name>
```

**Note:** In most of the case the `<remote_name>` is `origin`.

**For example** If I want to delete my remote `feature/add-profile` branch, i will hit the following command.

```
git push origin --delete feature/add-profile
```

## Conclusion

We have seen how we can delete the local and remote branches in GIT.

If you want to delete the **local branch**
```
 git branch -d <branch_name>
```
If you want to delete the **remote branch**

```
$ git push -d <remote_name> <branch_name>
```
In most of the cases `<remote_name` is `origin`.

That's it for now, we will see more GIT related articles in the future.

You can check my YouTube channel [here](https://www.youtube.com/channel/UCl31HHUdQbSHOQfc9L-wo3w)

### Related Articles

-   [8 Basic GIT Commands Every Newbie Developer Must Know](https://coderolls.com/basic-git-commands/)

-   [How To Get Current Timestamp In Java?](https://coderolls.com/how-to-get-current-timestamps-in-java/)

-   [How To Convert An Integer To String In Java](https://coderolls.com/convert-int-to-string/)
    
-   [How to convert String to Integer in Java](https://coderolls.com/convert-string-to-int/)
    
-   [How To Convert StringBuilder To String In Java?](https://coderolls.com/convert-stringbuilder-to-string-in-java/)
    
-   [How Do I Compare Strings In Java](https://coderolls.com/compare-strings-in-java/)
    
-   [How To Reverse A String In Java (5 ways)](https://coderolls.com/reverse-a-string-in-java/)

