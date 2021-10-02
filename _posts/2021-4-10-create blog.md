---
title: 博客搭建
tags:
  - 心得
---

## ***本站是基于Jekyll在windows上(非原生)配置了ruby和bundler后搭建的***
没用ubuntu因为被折腾吐了  
服务器用的是**github仓库**(完全免费)  
后期会考虑把站点移植到自己的vps上去

参考教程:
- [酒石酸的视频](https://b23.tv/BKmxVC)
- [jekyll配置](https://jekyllrb.com)
- [吴坎的模板](https://github.com/wu-kan/jekyll-theme-WuK)
- [atom入门](https://blog.csdn.net/u010494080/article/details/50372857)
- [汇编语言教程](https://www.runoob.com)
- [Live2D模型](https://github.com/imuncle/live2d)
- [菜蛇蛇の指导](https://caishangqi.github.io)

建议全程开代理
没有代理的可以去找你的朋友白嫖，或者参考[v2ray教程](https://ba1oretto.github.io/_posts/2021-05-10-v2ray)来搭一台代理服务器  
其实你也可以**不配置Jekyll**直接下载模板来进行修改，不过没有**本地调试**的话难度大增

### 避坑:  
打开***power shell***时一定要在你所克隆下来的**项目根目录**中进行。  
如果在调试阶段运行***jekyll server***时提示**(Gem::NotFound)**可以尝试
```bash
# Install the gems specified by the Gemfile or Gemfile.lock
bundle install
```
如果显示**(Gem::LoadError)**可以在***jekyll server***命令前添加
```bash
# Execute a script in the current bundle
bundle exec
```

报错了没必要慌，基本上所有**报错日志**里都会写解决方案，要好好读一下。实在找不到再去[google](https://www.google.com)上把报错信息复制到所搜栏查一下，这里不推荐[百度](https://www.baidu.com)因为相对于谷歌搜出来的东西并不是很靠谱。~~果然还是国外的大米香啊~~

<br>

最后，一定要  
**多用搜索引擎**  
**多用搜索引擎**  
**多用搜索引擎**
