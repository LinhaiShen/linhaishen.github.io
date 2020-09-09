title: Hide redmine issues' reposts for non-admin users
tags:
  - redmine
  - permission
  - admin
categories:
  - redmine
author: Linhai Shen
date: 2020-09-09 12:00:00
---
1. Add below lines to app/views/reports/issue_report.html.erb
```
<% if User.current.admin? %>
<!--- Original code here --->
<% end %>
```
1. Restart redmine daemon. Done!

Reference from:
1. https://www.redmine.org/boards/1/topics/55197