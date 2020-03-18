title: Install rails on ubuntu
author: Linhai Shen
tags:
  - ruby
  - sqlite3
  - rails
  - nokogiri
  - gem
  - zlib
categories:
  - rails
date: 2020-03-14 15:39:00
---
1. Install Ruby and SQLite3
1. Install Rails with gem
<!--more-->
```
sudo gem install rails
```
got below error:
```
ERROR:  Error installing rails:
        ERROR: Failed to build gem native extension.

    current directory: /var/lib/gems/2.5.0/gems/nokogiri-1.10.9/ext/nokogiri
/usr/bin/ruby2.5 -r ./siteconf20200314-38-xxyy88.rb extconf.rb
checking if the C compiler accepts ... yes
Building nokogiri using packaged libraries.
Using mini_portile version 2.4.0
checking for gzdopen() in -lz... no
zlib is missing; necessary for building libxml2
*** extconf.rb failed ***
```
After try install nokogiri
```
sudo gem install nokogiri
```
Error:
```
ERROR:  Error installing nokogiri:
        ERROR: Failed to build gem native extension.

    current directory: /var/lib/gems/2.5.0/gems/nokogiri-1.10.9/ext/nokogiri
/usr/bin/ruby2.5 -r ./siteconf20200314-78-1wo5kzo.rb extconf.rb
checking if the C compiler accepts ... yes
Building nokogiri using packaged libraries.
Using mini_portile version 2.4.0
checking for gzdopen() in -lz... no
zlib is missing; necessary for building libxml2
```
checked log and found the cause, install libz-dev and then install nokogiri
```
vim /var/lib/gems/2.5.0/extensions/x86_64-linux/2.5.0/nokogiri-1.10.9/mkmf.log
sudo apt-get install libz-dev
sudo gem install nokogiri
```
1. try install rails again
```
sudo gem install rails
```
Check result with `rails -v`.
It's done.

Reference from:
1. {% blockquote rubyonrails.org https://guides.rubyonrails.org/getting_started.html %}
Getting Started with Rails
{% endblockquote %}
1. {% blockquote kenorb https://stackoverflow.com/questions/36374267/how-to-fix-fatal-error-zlib-h-no-such-file-or-directory %}
How to fix fatal error: zlib.h: no such file or directory?
{% endblockquote %}