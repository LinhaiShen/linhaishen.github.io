---
title: Synchronize between multiple hexo bases
date: 2020-03-08 07:27:52
tags: 
- hexo
- git
- branch
---

# your.github.io setup

1. Initial your.github.io with hexo deployment
1. Create a branch named "hexo" from your.github.io master branch
1. Set "hexo" as your default branch of your.github.io

<!-- more -->
# your new hexo bases setup
1. Git clone git@github.com:your/your.github.io.git
1. Change dir to your cloned "hexo", install packages for hexo
```
cd your.github.io
npm install
```
1. Make sure deploy branch in _config.yml is master

# Synchronize
1. git clone for inintial hexo base
1. Install theme if you are not using "landscape"
## themes/next example
1. On your up to date hexo base: Copy your "themes/next/_config.yml" to your "hexo" branch root
```
cp themes/next/_config.yml next-config.yml
git add .
git commit -m "sync theme config"
git push
```
1. On your new hexo base: git pull to get the latest theme's config
```
git pull
cp next-config.yml themes/next/_config.yml
```
# Writing
1. hexo new post to start writing
1. after writing commit source to your.github.io "hexo" branch
```
git add .
git commit
git push
```
1. hexo g -d to deploy to your.github.io master branch

Reference from:
{% blockquote CrazyMilk https://www.zhihu.com/question/21193762 %}
使用hexo，如果换了电脑怎么更新博客？
{% endblockquote %}
