title: Discourse Bitnami Stack email SMTP configration
tags:
  - config
  - discourse
  - Bitnami
  - smtp
categories:
  - discourse
author: Linhai Shen
date: 2020-07-22 10:00:00
---
1. Download and run [Discourse Bitnami Stack VM](https://bitnami.com/stack/discourse/virtual-machine)
<!-- more -->
1. Follow [Bitnami Config Docs](https://docs.bitnami.com/installer/apps/discourse/configuration/configure-smtp/)
```
smtp_address = "smtp.gmail.com"
smtp_port = 587
smtp_domain = example.com
smtp_user_name = 'USERNAME@gmail.com'
smtp_password = 'PASSWORD'
smtp_enable_start_tls = true
smtp_authentication = login
```
1. Make sure Discourse's notification email setting is same as smtp_user_name, otherwise:

```
554 5.2.0 STOREDRV.Submission.Exception:SendAsDeniedException.MapiExceptionSendAsDenied; 
Failed to process message due to a permanent exception with message Cannot submit message.
```

That's it.

Reference from:
1. [Bitnami Config Docs](https://docs.bitnami.com/installer/apps/discourse/configuration/configure-smtp/)
1. [Troubleshooting email on a new Discourse install](https://meta.discourse.org/t/troubleshooting-email-on-a-new-discourse-install/16326/308)
1. [SMTP Sender Address Issue](https://community.quickfile.co.uk/t/smtp-sender-address-issue/23697)