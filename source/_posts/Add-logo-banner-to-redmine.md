title: Add logo / banner to redmine
tags:
  - config
  - redmine
categories:
  - redmine
author: Linhai Shen
date: 2020-03-24 08:27:00
---
1. Edit your base.html.erb file, add pic above redmine title
<!-- more -->
```
vim {$redmine-root}/app/views/layouts/base.html.erb
<img src="<%= Redmine::Utils.relative_url_root %>/images/logoscts.png" style="margin-top: 15px; margin-left: 15px;"/> #line to add
<h1><%= page_header_title %></h1> #redmine original line
```
1. upload you logo / banner pic to the directory, my prefernce is using FileZilla
```
{$redmine-root}/public/images
```
I forgot to "chown the uploaded" pic, but it still works.
1. restart your redmine daemon, which I made it as a service
```
sudo service redmined restart
```
1. check your redmine via browser, it's done.

Reference from:
{% blockquote redmine, redmine.org https://redmine.org/projects/redmine/wiki/Howto_add_a_logo_to_your_Redmine_banner "Redmine banner" %}
HowTo add a logo to your Redmine banner.
{% endblockquote %}