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

# your hexo bases setup
1. Git clone git@github.com:your/your.github.io.git
1. Change dir to your cloned "hexo", install packages for hexo
```
cd your.github.io
npm install
```
1. Install theme if you are not using "landscape"
1. Make sure deploy branch in _config.yml is master
1. Write with hexo new post
1. Deploy to your.github.io master branch with hexo g -d

# Synchronize
1. git clone for inintial hexo base
1. git pull for synchronize
1. git add . after writing
1. git commit & push to your.github.io "hexo" branch

Reference from:
{% blockquote CrazyMilk https://www.zhihu.com/question/21193762 %}
使用hexo，如果换了电脑怎么更新博客？
{% endblockquote %}
