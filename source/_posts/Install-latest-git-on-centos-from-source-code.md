title: Install latest git on CentOS from source code
author: Linhai Shen
tags:
  - git
  - centos
  - make
  - compile
  - build
  - install
categories:
  - linux
date: 2020-03-19 14:34:00
---
1. prepare build tools if tools not ready
<!-- more -->
```
yum install perl-ExtUtils-CBuilder perl-ExtUtils-MakeMaker
```
1. remove old version git
```
yum remove git
```
1. download latest version git from https://mirrors.edge.kernel.org/pub/software/scm/git/
```
wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.9.5.tar.gz
tar zxvf git-2.9.5.tar.gz
cd git-2.9.5
```
1. complie and install
```
./configure --prefix=/usr/local/git
make
make install
```
1. set env path
```
echo 'export PATH=$PATH:/usr/local/git/bin' >> /etc/bashrc
source /etc/bashrc
```
1. it's done, check git version
```
git --version
```

Reference from 
1. https://stackoverflow.com/questions/21820715/how-to-install-latest-version-of-git-on-centos-7-x-6-x
1. https://www.jianshu.com/p/729f4f313642