title: Config redmine email smtp with outlook.com mail service
tags:
  - config
  - redmine
  - outlook.com
  - smtp
categories:
  - redmine
author: Linhai Shen
date: 2020-03-09 16:23:00
---
1. edit redmine-root/config/configuration.yml
<!-- more -->
```
production:
  email_delivery:
    delivery_method: :smtp
    smtp_settings:
      enable_starttls_auto: true
      address: "smtp.office365.com"
      port: 587
      domain: "outlook.com"
      authentication: :login
      user_name: "username@outlook.com"
      password: "password"
```
1. Restart your redmine daemon, options of "Administration : Email Notification" will be available.
1. Send a test email via redmine Administration : Email Notification tab
 If you got error like "WASCL UserAction verdict is not None. Actual verdict is HipNotify, ShowTierUpgrade.",
 please check your outlook.com inbox and follow the guide to validate your Outlook.com account.
 And try again.
1. Check your receiving email inbox or junk email, it's done.

Reference from:
{% blockquote redmine, redmine.org https://www.redmine.org/projects/redmine/wiki/EmailConfiguration#Office-365-Exchange-Online "Email Configuration" %}
Here is an example for Office 365 users (Exchange online).
{% endblockquote %}