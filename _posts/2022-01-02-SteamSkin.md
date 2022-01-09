---
title: 自定义steam皮肤
tags:
  - steam
---

<br>

# steam提供了自定义皮肤的功能, 让你可以修改那深灰色像混凝土一样的皮肤
![](/assets/image/posts/2022-01-02-SteamSkin/steamlibrarypage.png)

## 不过具体操作起来十分繁琐, 要配置大量的文件, 还会涉及到图片的转换, 非常的麻烦
## 好在市面上已经有比较成熟的皮肤自定义应用了

<br>

### 比如 _Jack-Myth_ 的 [_Threshold-Miku_](https://github.com/Jack-Myth/Threshold-Miku)
### 它提供了一个图形界面可以让你更方便地进行皮肤替换的操作, 并且会自动地将你的图片转换为steam需要的格式
### 并且它有两种主题可供选择, 分别是 _亮色调版本_ 与 _普通版本(暗色调)_ , 你甚至可以使用它去更改steam的字体

<br><br><br>

# 1.下载
> <br>
>
> ## Threshold-Miku的GitHub仓库主页: [Threshold-Miku](https://github.com/Jack-Myth/Threshold-Miku)
> ## 你也可以在这里进行查看版本并进行下载: [Releases](https://github.com/Jack-Myth/Threshold-Miku/releases)
> ![](/assets/image/posts/2022-01-02-SteamSkin/downloadskin.png)
> ## 需要注意的是, 你需要下载他的压缩包并解压
> ### 不要下载源码(source code)
> ![](/assets/image/posts/2022-01-02-SteamSkin/downloadlocate.png)
> ## 并确保它只有一级目录
> ![](/assets/image/posts/2022-01-02-SteamSkin/menulevel.png)

<br><br><br>

# 2.导入
> <br>
>
> ## 现在把你的文件导入到皮肤文件夹中, 它位于你steam的安装路径(非库路径)
> ###(../steam/skins/)
> ![](/assets/image/posts/2022-01-02-SteamSkin/skinlocation.png)

<br><br><br>

# 3.应用皮肤
> <br>
> 
> ## 打开你的steam界面, 在 _设置_ -> _界面_ -> _选择你希望被steam使用的皮肤_ 中选择 _Threshold-Miku_
> ### (settings -> interface -> select the skin you wish steam to use)
> ![](/assets/image/posts/2022-01-02-SteamSkin/enableskin.png)
> ## 然后重启你的steam, 你现在也许可以看到皮肤被正确地加载了
> ### 如果未生效, 确保在你的皮肤目录下它只有一级文件夹 _../steam/skins/Threshold-Miku/*_

<br><br><br>

# 4.修改皮肤
> <br>
> 
> ## 打开它自带的皮肤编辑软件
> ### (../steam/skins/Threshold-Miku/Threshold Miku Customizer 2.exe)
> ![](/assets/image/posts/2022-01-02-SteamSkin/applicationlocation.png)
> ## 你可以看到如下界面
> ![](/assets/image/posts/2022-01-02-SteamSkin/apppage.png)
> 
> > ## click to select an image: 下拉复选框, 你可以看到一个列表, 以选择你要更改背景的位置
> > ## set new background: 配合选择列表, 你可以更换当前被选择的背景的样子
> > ### 需要注意, 图片分辨率应严格按照其给定的数值进行设定(使用ps裁剪, 缩放), 且文件大小不能过大(大概为2m左右), 否则会失效
> > ![](/assets/image/posts/2022-01-02-SteamSkin/selectlist.png)
> 
> > ## customization(定制)
> > > ### collapsed sidebar: 折叠左侧的选项栏
> > > ![](/assets/image/posts/2022-01-02-SteamSkin/collapsedsidebaron.png) ![](/assets/image/posts/2022-01-02-SteamSkin/collapsedsidebaroff.png)
> > > ### new webpage without URL: 其他方案会导致背景图片错位
> > > ![](/assets/image/posts/2022-01-02-SteamSkin/hasurl.png)
> 
> > > ### library blur(库模糊度)
> > > > #### game list: 游戏列表的模糊度(由左到右, 模糊度递增)
> > > > ![](/assets/image/posts/2022-01-02-SteamSkin/gamelist.png)
> > > > #### main content: 主内容的模糊度(由左到右, 模糊度递增)
> > > > ![](/assets/image/posts/2022-01-02-SteamSkin/maincontent.png)
> 
> > > ### main content opacity: 意义不明
> > > ### web page brightness: 网页页面的亮度(典型的表现为商店页面)
> > > ### (从左到右, 亮度递增, 最亮时为背景原色)
> > > ![](/assets/image/posts/2022-01-02-SteamSkin/webpagebrightness.png)
> > > ### show library window divider: 显示游戏列表与主内容分割线
> > > ### main content underpainting: 意义不明
> 
> > > ### fonts setting: 设置字体
> > > > ![](/assets/image/posts/2022-01-02-SteamSkin/fontssetting.png)
> > > > #### VGUI: 貌似是改字体的, 但我没玩明白
> > > > #### SteamUI(steam的UI)
> > > > > ##### Global: 设置全局字体
> > > > #### game list font color(游戏列表的字体颜色)
> > > > > ##### uninstalled: 未安装
> > > > > ##### installed: 已安装
> > > > > ##### running: 正在运行
> > > > > ##### updating: 待更新
> > > > > ##### group section: 组标签
> 
> > > ## save settings: 保存设置(相当于导出配置文件)
> > > ## load settings: 加载设置(相当于导入配置文件)
> > > ## apply: 应用(使更改生效, 你需要重启steam)
> > > ## reset: 重置(将更改回滚到最初状态)