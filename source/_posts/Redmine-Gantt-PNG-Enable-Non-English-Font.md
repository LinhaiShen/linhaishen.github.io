title: Enable Non-English Font when export Redmine Gantt PNG
tags:
  - config
  - redmine
  - ImageMagick
  - CentOS
categories:
  - redmine
author: Linhai Shen
date: 2020-05-27 15:00:00
---
1. Install ImageMagick
<!-- more -->
```
yum install ImageMagick ImageMagick-devel
```
1. Gem install rmagick
Gemfile:
```
gem 'rmagick', '~> 2.15', '>= 2.15.4'
```
Run:
```
bundle install
```

1. Find out which fonts support non-English Language you expected:
```
fc-list :lang=zh
```

1. Add the font path to config/configuration.yml
```
minimagick_font_path: /usr/share/fonts/wqy-microhei/wqy-microhei.ttc
```

1. Restart your redmine, It's done!