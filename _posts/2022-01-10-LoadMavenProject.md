---
title: 加载maven项目
tags:
  - JetBrains
---

<br>

## 有时, 我们从github或者gitee上上面直接clone的maven项目时, 开发者ignore了一些配置文件, 导致maven无法自动加载
## 这时, 需要我们手动的进行其相关的配置

<br><br><br>

# 1.配置项目maven环境
> <br>
> 
> ## 转至 _File -> Settings -> Build, Execution, Deployment -> Build Tools -> Maven_
> ## 确认以下为你想要的内容
> > ### Maven home path
> > ### User settings file
> > ### Local repository
> ![](/assets/image/posts/2022-01-10-LoadMavenProject/MavenConfigurations.png)
> ## 另外你还需要注意项目的SDK是否正确地进行了配置
> ## 项目的SDK位于 _File -> Project Structure -> Project Settings -> Project -> SDK_

# 2.配置父级pom
> <br>
> 
> ## 你需要将顶级pom文件添加至maven工程
> ## 右键你的顶级pom文件, 选择 _Add as Maven Project_
> ## 现在你的项目maven已经恢复正常了