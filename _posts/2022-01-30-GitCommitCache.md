---
title: Git将已提交的项目从版本库中移除
tags:
  - Git
---

<br>

## `git rm -r --cached <file name>`
> -r: Allow recursive removal when a leading directory name is given.
> 
> --cached: Use this option to unstage and remove paths only from the index. Working tree files, whether modified or not, will be left alone.

## 这个操作可以使你指定文件仅从index中移除, 而不影响工作区的本地文件
## 进而你可以重新对其进行add和commit
## 这样你可以对其开展一些操作, 比如添加其到gitignore文件中, 或者取消对其的关联
![](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)
