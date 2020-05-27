title: Enable Chinese,Japanese,Korean Font when exporting Redmine Gantt PNG
tags:
  - config
  - redmine
  - ImageMagick
  - CentOS
  - font
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

1. Find out which fonts support CJK Language you expected:
```
fc-list :lang=zh
```

1. Add the font path to config/configuration.yml
```
minimagick_font_path: /usr/share/fonts/wqy-microhei/wqy-microhei.ttc
```

1. Restart your redmine, It's done!

1. BONUS
user-profile set to English, export pdf in CJK
modify config/locales/en.yml
```
#general_csv_encoding: ISO-8859-1
general_csv_encoding: UTF-8
#general_pdf_fontname: freesans
general_pdf_fontname: stsongstdlight
```