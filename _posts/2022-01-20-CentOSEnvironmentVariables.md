---
title: 新应用环境变量配置
tags:
  - Linux
---

## 大多数时候, 在你安装好软件后, 你需要配置环境变量才可以用bash调用它们


# profile路径一般在 /etc/profile
## 添加应用至环境
> ### 临时的(重启后失效)
> > 在Bash输入 `export PATH=<应用程序的bin路径>:$PATH`
> ### 持久的
> > 编辑profile文件, 在结尾换行添加`export PATH=<应用程序的bin路径>:$PATH`

# 配置完一定要重启或重载profile !!!
## 重载环境(立即生效)
> 在Bash输入 `source <profile路径>`