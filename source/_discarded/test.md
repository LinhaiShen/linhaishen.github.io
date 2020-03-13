title: test
author: Linhai Shen
date: 2020-03-12 11:14:11
tags:
---
\|*. Date \|*. Who \|\_. What \|\
\| 2020/03/02 \| Linhai \| 变更Reporter Role权限，allow "Edit own
issues" \|\
\| 2020/03/05 \| Linhai \| Disable "Use current date as start date for
new issues"\|\
\| 2020/03/05 \| Linhai \| 24 to 48 of "Maximum number of months
displayed on the gantt chart"\|\
\| 2020/03/09 \| Linhai \| update
/redmine/redmine-4.1.0/config/configuration.yml

    <code class="yaml">
    production:
      email_delivery:
        delivery_method: :smtp
        smtp_settings:
          enable_starttls_auto: true
          address: "smtp.office365.com"
          port: 587
          domain: "outlook.com"
          authentication: :login
          user_name: "gfscold_redmine@outlook.com"
          password: "Redmine87654321"
    </code>

\
\|
