---
layout: post
title:  "How to use git"
date:   2018-01-13 18:43:31 +0800
categories: jekyll update
---

```
git clone
git init
git add . git add FILENAME
git commit -m "modify"
git config --global user.name "USERNAME"
git config --global user.mail "EMAIL"
git push
git config --global --edit
git pull

```
- `git config --global user.name "USERNAME"`
show and change my git username
- git-bash environment variable
[1](http://www.cnblogs.com/xunzhiyou/p/5028789.html),[2](https://stackoverflow.com/questions/34169721/set-an-environment-variable-in-git-bash)

- `gitk` can see each record of commit
[git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)

![gitdiagram](/pictures/gitdiagram.png)

## How to download a repository
1. create a file and `cd` to the directory
2. `git init`
3. copy the repository url
4. `git clone url`

## proxy
- [Set up proxy for your working environment](http://zhenfisher.xyz/geek/set-up-proxy-for-your-working-environment/)




## Additional reading
- [How to upload local project to Github using linux](http://blog.51cto.com/1568397/1675493)
- [How to configue ssh key to Github](https://www.jianshu.com/p/9317a927e844)

## Problems
1. can not git push
`git push --force`
[git  push  problems](http://www.cnblogs.com/renkangke/archive/2013/05/31/conquerAndroid.html)
2. [progit](file:///media/zhen/datascience/progit.pdf)
