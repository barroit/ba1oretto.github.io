---
title: 在discord上显示ide的状态
tags:
  - 日常
---

<br>

# Aljoscha Grebe的 `discord integration` 是一款可以让discord识别当前你所使用的jet brains公司下的ide状态的一款插件
![](/assets/image/posts/2022-01-02-DiscordIntegration/edit.png) ![](/assets/image/posts/2022-01-02-DiscordIntegration/prepare.png) ![](/assets/image/posts/2022-01-02-DiscordIntegration/home.png)

# 你可以在jet brains旗下的ide的插件市场中找到它
## 不过你也许会需要进行一些配置, 以便使其更加的自定义化

<br><br><br>

# 1.安装插件
> <br>
> 
> ## 在插件市场搜索 `discord integration` 你可以看到它
> ### (由于我之前安装过了, 所以是在installed里面显示的)
> ## 通常安装完会要求你重启ide
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/plugininmarket.png)

<br><br><br>

# 2.转至位于ide中的discord设置
> <br>
>
> ## 它通常位于 _其他设置_ 中
> ### (File -> Settings -> Other Settings -> Discord)
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/pluginsettingslocation.png)

<br><br><br>

# 3.初始化
> <br>
>
> ## 一开始你看到的可能是下面这样的
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/originsettings.png)
> ## 很显然, 他在discord的表现并不是很好, 我们可以通过添加一些官方给定的模板变量来使其变得更加形象
> ## 官方列举了所有可用的模板变量在他们的 [插件模板文档](https://github.com/Almighty-Alpaca/JetBrains-Discord-Integration/blob/v1.8.0/plugin/templates.adoc) 中
> ## 在每个变量的后面, 都有使用的介绍, 甚至每个变量可以使用它自己的简写, 灵活地运用简写可以让你的排版更加清晰
> ## 并且你需要在 _First line_ , _Second line_ , _Text_ 中选择 _Custom_ 以开启自定义模板变量
> ## 需要注意的是, 这个插件对文本编辑的支持似乎不是很好, 可以看到, 你的文本编辑框只有很小的一块, 而你有时候可能需要写很长的代码来完成你的逻辑
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/customsettings.png)
> ## 这时候需要你在其他的文本编辑器像是notepad++先进行编辑再复制粘贴到文本框中以实现功能
> ## 当你不想在触发idle时显示idle并重置运行时间, 可以取消勾选 _reset open time when returning_, 并在 _while idle_ 中选择 _keep showing rich presence_
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/idle.png)
> ## 有个小问题, 在自定义文本中 _双引号(")_ 不被生效, 不过你依然可以用两个 _单引号(')_ 来代替双引号的效果, 它们所占的字体空间在discord上是相同的

<br><br><br>

# 我自己的模板
> <br>
> 
> ## Application
> > ### First line: `当前版本${ApplicationVersion}`
> > ### Second line: `https://baioretto.com`
> > ### Large icon: `WebShit`
> 
> <br>
> 
> ## Project
> > ### First line: `Baioretto同学马上就要`
> > ### Second line: `构建项目''${ProjectName}''啦`
> > ### Large icon: `WebShit`
> 
> <br>
> 
> ## File
> > ### First line: (由于正则表达式会使github page编译失败, 所以由图片形式展示)
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/firstline.png)
> > ### Second line: (由于正则表达式会使github page编译失败, 所以由图片形式展示)
> ![](/assets/image/posts/2022-01-02-DiscordIntegration/secondline.png)
> > ### Large icon: `WebShit`
> > ### Small icon: `${Language}`