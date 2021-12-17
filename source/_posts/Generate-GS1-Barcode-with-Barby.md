title: Generate GS1 Barcode with Barby
author: Linhai Shen
tags:
  - logistics
  - GS1
  - barcode
  - ruby
categories:
  - logistics
date: 2021-12-14 09:00:00
---
```
gs1 = Barby::Code128.new("#{Barby::Code128::FNC1}0012345")
```
