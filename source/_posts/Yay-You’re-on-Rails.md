title: Yay! You’re on Rails!
author: Linhai Shen
tags:
  - rails
  - yarn
  - bundle
  - gem
categories:
  - rails
date: 2020-03-15 11:03:00
---
1. create my 1st rails appliaction
```
rails new blog
```
got stuck during `bundle install` running
<!--more-->
ctrl+c exit
1. Change local gem source and run `bundle install` again
```
cd blog
vim Gemfile
source 'https://gems.ruby-china.com'
#source 'https://rubygems.org'
bundle install
...
Bundle complete! 17 Gemfile dependencies, 75 gems now installed.
```
1. Install Yarn and webpacker
try `rails server` got webpacker missing error
```
/var/lib/gems/2.5.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:95:in `rescue in load': Webpacker configuration file not found /home/ubuntu/rails-blog/config/webpacker.yml. Please run rails webpacker:install Error: No such file or directory @ rb_sysopen - /home/ubuntu/rails-blog/config/webpacker.yml (RuntimeError)
```
try `rails webpacker:install` got
```
Yarn not installed.
```
 - install Yarn
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
```
 - install webpacker
```
rails webpacker:install
...
Webpacker successfully installed
```
1. Yay! You’re on Rails!
```
rails server
```
---
change gem and bundle source
```
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
bundle config mirror.https://rubygems.org https://gems.ruby-china.com
```

Reference from:
1. {% blockquote rubyonrails.org https://guides.rubyonrails.org/getting_started.html %}
Getting Started with Rails
{% endblockquote %}
1. {% blockquote yarnpkg.com https://classic.yarnpkg.com/en/docs/install/#debian-stable %}
On Debian or Ubuntu Linux, you can install Yarn via our Debian package repository. 
{% endblockquote %}
1. https://gems.ruby-china.com/
1. https://bundler.io/v1.16/bundle_config.html