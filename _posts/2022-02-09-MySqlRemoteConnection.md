---
title: mysql远程连接数据库
tags:
  - 日常
---
  
### 配置好你的mysql并登录后, 使用`use mysql`切换数据库至mysql
### 使用`update user set host = "%" where host = "localhost"`修user改表中字段为host的数值
### 使用`flush privileges`刷新