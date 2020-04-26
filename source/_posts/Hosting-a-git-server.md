title: Hosting a GIT server
author: Linhai Shen
tags:
  - git
  - server
  - authorization
  - host
  - additionals
categories:
  - git
date: 2020-04-26 09:50:00
---
1. Install git on the server
see detail steps [here](https://linhaishen.github.io/2020/03/19/Install-latest-git-on-centos-from-source-code/) 
<!--more-->
1. First, you create a git user account and a .ssh directory for that user.
```
$ sudo adduser git
$ su git
$ cd
$ mkdir .ssh && chmod 700 .ssh
$ touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
```
Next, you need to add some developer SSH public keys to the authorized_keys file for the git user. Let’s assume you have some trusted public keys and have saved them to temporary files.
You just append them to the git user’s authorized_keys file in its .ssh directory:
```
$ cat /tmp/id_rsa.john.pub >> ~/.ssh/authorized_keys
$ cat /tmp/id_rsa.josie.pub >> ~/.ssh/authorized_keys
$ cat /tmp/id_rsa.jessica.pub >> ~/.ssh/authorized_keys
```
1. Now, you can set up an empty repository for them by running git init with the --bare option, which initializes the repository without a working directory:
```
$ cd
$ mkdir repo1
$ cd repo1
$ git init --bare
Initialized empty Git repository in /home/git/repo1/
```
1. Then, John, Josie, or Jessica can push the first version of their project into that repository by adding it as a remote and pushing up a branch. Note that someone must shell onto the machine and create a bare repository every time you want to add a project. Let’s use gitserver as the hostname of the server on which you’ve set up your git user and repository. If you’re running it internally, and you set up DNS for gitserver to point to that server, then you can use the commands pretty much as is (assuming that myproject is an existing project with files in it):
```
# on John's computer
$ mkdir repo1
$ git init
$ touch file1.md
$ git add .
$ git commit -m 'Initial commit'
$ git remote add origin git@serverdns:/home/git/repo1
$ git push origin master
```
It's done.


Reference from:
1. https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server