title: Add terms of use to redmine
author: Linhai Shen
tags:
  - redmine
  - terms
  - authorization
  - plugins
  - additionals
categories:
  - redmine
date: 2020-04-24 11:03:00
---
1. Install "Privacy & Terms plugin for Redmine" 
<!--more-->
```
cd $REDMINE_ROOT
git clone git://github.com/alphanodes/redmine_privacy_terms.git plugins/redmine_privacy_terms
git clone git://github.com/alphanodes/additionals.git plugins/additionals
bundle install --without development test
bundle exec rake redmine:plugins:migrate RAILS_ENV=production
```
By above codes, you've also installed redmine plugin "additionals" which is also very useful.
1. Create a project to host wiki page of terms where everyone can access
1. Create wiki page of terms, optionally you can create a wiki page for users who reject the terms
"the two macros must be implemented in it."
```
{{terms_accept}}
{{terms_reject}}
```
1. Config `/settings/plugin/redmine_privacy_terms?tab=terms` 
URL of the wiki with the terms: `wiki/`
URL of the wiki for users who reject the terms: external url or a wiki page (didnot work in my setting)
tick 'Enable terms'
1. Check result in user profile page `/users/user-id`, and test accept/reject action.
    * Terms of use
        * Show
        * not acccepted yet
1. Optionally you can re-trigger request users to read and accept terms `/settings/plugin/redmine_privacy_terms?tab=tools` 
It's done!

Referenced from:
1. https://github.com/AlphaNodes/redmine_privacy_terms/blob/master/README.md