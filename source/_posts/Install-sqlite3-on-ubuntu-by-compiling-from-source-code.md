title: Install sqlite3 on ubuntu by compiling from source code
author: Linhai Shen
tags:
  - sqlite
  - ubuntu
  - make
  - compile
  - build-essential
  - build
  - install
categories:
  - linux
date: 2020-03-13 10:43:00
---
1. prepare build tools if tools not ready
<!-- more -->
```
sudo apt-get install build-essential
```
1. download source code package from https://www.sqlite.org/download.html
```
curl -O https://www.sqlite.org/snapshot/sqlite-snapshot-202003121754.tar.gz
```
1. unzip and enter the dir
```
tar xvzf sqlite...tar.gz
cd sqlite...
```
1. compile, build and install
```
./configure
make
#if failed, try "make clean" and run "make" again
sudo make install
```

Reference from:
1. https://stackoverflow.com/questions/19816275/no-acceptable-c-compiler-found-in-path-when-installing-python
1. INSTALL doc in the package
1. {% blockquote runoob.com https://www.runoob.com/sqlite/sqlite-installation.html %}
SQLite 安装
{% endblockquote %}