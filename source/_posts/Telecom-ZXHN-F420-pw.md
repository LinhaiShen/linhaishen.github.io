title: Telecom ZXHN F420 admin access
tags:
  - telecom
  - router
  - zhongxing
categories:
  - network
author: Linhai Shen
date: 2020-05-07 09:35:00
---
1. Export/downlaod device config.bin via http://192.168.1.1/manager_dev_config_t.gch
<!-- more -->
1. Prepare unzip tool `offzip` via http://aluigi.altervista.org/mytoolz/offzip.zip
1. unzip offzip and move config.bin to the same folder
1. Use command shell to unzip config.bin
```
./offzip -a config.bin ./ 0
```
1. Open `000000d8.xml` with text editor, find out what you need, it's done.

Reference from:
https://www.bihell.com/article/85