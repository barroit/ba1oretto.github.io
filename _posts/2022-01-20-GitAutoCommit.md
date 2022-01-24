---
title: Linux实现Git自动提交
tags:
  - Git
---
  

## 衔接上一篇文章: [Linux实现Git补档](https://baioretto.com/_post/2022-01-20-GitDuplicates/), 有些内容看不懂的话就去看看上一篇文章
## Linux为我们提供了可以定期执行任务的方法, 具体实现为crontab(时程表)

## crontab可以用来定期执行业务
> ### 系统方面: 系统周期性所要执行的工作, 比如备份系统数据, 清理缓存
> ### 个人方面: 用户定期要做的工作, 例如每隔1天向github推送一次提交

<br>

## 具体用法
> ### `crontab [ -u user ] { -l | -r | -e }`
> ### `-u user` 作用为: 指设定指定 <user> 的时程表, 你必须拥有权限(例如root用户)才能指定其他用户的时程表, 它并不是必要的参数, 不声明则表示修改自己的时程表
> ### `-e` 作用为: 使用文本编辑器编辑时程表, 默认的文本编辑器是VIM, 你可以修改EDITOR变量来指定你想要使用的文本编辑器
> ### `-r` 作用为: 删除目前的时程表
> ### `-l` 作用为: 列出目前的时程表

<br>

## 格式
> ### .---------------- 第几分钟 (0 - 59)
> ### |  .------------- 第几小时 (0 - 23)
> ### |  |  .---------- 一个月中的第几天 (1 - 31)
> ### |  |  |  .------- 第几月 (1 - 12) 或者 jan,feb,mar,apr ...
> ### |  |  |  |  .---- 一周的第几天 (0 - 6) (星期日=0 or 7) 或者 sun,mon,tue,wed,thu,fri,sat
> ### |  |  |  |  |
> ### *  *  *  *  * [user-name]  command to be executed

<br>

## 设置时程表, 定时自动提交任务
> ### `00 12 * * * cd /root/Baioretto/workspace/auto-commit && /root/Baioretto/lib/git/bin/git pull && /root/Baioretto/lib/nodejs/node-v16.13.2-linux-x64/bin/node add.js && /root/Baioretto/lib/git/bin/git add records.txt && /root/Baioretto/lib/git/bin/git commit -a -m '打卡' && /root/Baioretto/lib/git/bin/git push origin master > /dev/null 2>&1`
> ### 00 12 * * * 为执行时间
> ### 你需要将目录`/root/Baioretto/workspace/auto-commit`替换成你自己的自动提交项目的根目录
> ### 为了确保正确执行, 将命令写成绝对路径, 比如`/root/Baioretto/lib/git/bin/git pull`而不是`git pull`
> ### `/dev/null 2>&1`的作用是在执行命令时不在命令行显示