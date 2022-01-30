---
title: gitignore文件的
tags:
  - Git
---
  
## pattern就是你所指定忽略的文件，比如`a/b/*.yml`

# 名字
## gitignore - 指定忽略有意不被track的文件

# 概要
## $XDG_CONFIG_HOME/git/ignore, $GIT_DIR/info/exclude, .gitignore

# 描述
## 一个`gitignore`文件指定那些有意不被track的git应该忽略的文件，那些已经被git track的文件不会生效。
## 每一行在`gitignore`文件中指定一个pattern，在决定是否忽略一个路径时，git通常会检查多个`gitignore`源的pattern，具有以下优先顺序，从最高到最低(在一个优先级内，最后一个匹配pattern决定结果)。
+ patterns从命令行读取支持它们的那些指令。
+ 
+ patterns从一个在与path相同的目录中的`.gitignore`文件，或者在任意父类目录(直到work tree的顶级)中读取，高级文件中的pattern被低级文件中的pattern覆盖直到包含该文件的目录，这些patterns与`.gitignore`文件的位置相匹配。一个项目通常在它的repository中包含此类`.gitignore`文件，其中包含作为项目构建的一部分所生成的文件的pattern。
+ 
+ patterns从`$GIT_DIR/info/exclude`中读取。
+ 
+ patterns从被配置文件变量所指定的`core.excludesFile`文件中读取。

## 将pattern放入哪个文件取决于pattern的使用方式。
+ 应该被版本控制并且用过克隆来发布到其他repositories(例子：所有那些开发者们想要忽略的文件)应该写入进`.gitignore`文件。
+ 
+ 那些被指定到一个特定的repository 但是又不需要被共享到其他有关的repositories(例子：存在于repository中但特定于一个用户的工作流程的辅助文件)的patterns应该写入进`$GIT_DIR/info/exclude`文件。
+ 
+ 用户想要git在任何情况都忽略(例子：被用户选择的编辑器生成的备份或临时文件)的pattern一般会通过`core.excludesFile`写入到一个特定的文件在用户的`~/.gitconfig`。它的默认值为`$XDG_CONFIG_HOME/git/ignore`。如果`$XDG_CONFIG_HOME`未被设置或者为空，则`$HOME/.config/git/ignore`会被使用。

## 底层的git开发工具，像是`git ls-files`以及`git read-tree`，读取被命令行参数指定的`gitignore`或者来自被命令行参数指定文件的patterns。更高级的git工具，像是`git status`和`git add`， 使用上述来源指定的pattern。

# pattern格式
+ 一个空行匹配无文件，所以它可以作为提高可读性的分隔符
+ 
+ 一个在开始有#的一行作为一个注释，在第一个井号(hash)前放置一个反斜杠("`\`")来让pattern用井号开头。
+ 
+ 尾随的空格会被忽略除非他们被反斜杠("`\`")引用。
+ 
+ 一个可选的会排除pattern的前缀"`!`"；任何匹配先前被pattern排除的文件都会被重新包含。如果排除了该文件的父目录，则无法重新包含该文件。出于性能原因，Git不会列出排除的目录，所以在被包含的文件中的任何patterns都没有效果，无论它们在哪里被定义。在第一个"`!`"前插入一个反斜杠("`\`")来让pattern以文字处理"`!`"，例子，"`\!important!.txt`"。
+ 
+ 斜杠"`/`"被用作目录的分隔器。分隔符可以出现在`.gitignore`的pattern的开头，中间或结尾。
+ 
+ 如果有一个分隔器在pattern的开头，中间(或者两端)，这代表pattern是对于在`.gitignore`文件自身同级目录的相对路径。否则pattern也可能在`.gitignore`目录以下的任何子目录进行匹配。
+ 
+ 如果有一个分隔器在pattern的结尾则代表pattern将仅匹配目录，否则pattern可以同时匹配文件和目录。
+ 
+ 一个星号"`*`"匹配所有除了斜杠。字符"`?`"匹配任意一个字符除了"`/`"。范围符号，比如`[a-zA-Z]`，可以被用于匹配一个属于范围内的字符。

## 与完整路径名匹配的patterns中的两个连续星号("`**`")可能具有特殊含义：
+ 一个位于开头的"`**`"后跟随一个斜杠表示在所有的目录中匹配。比如，"`**/foo`"在任意位置匹配文件或者目录"`foo`"，与pattern"`foo`"相同。"`**/foo/bar`"匹配在任何目录名为"`foo`"下的"`bar`"文件或目录。
+ 
+ 一个尾随的"`/**`"匹配目录里的所有东西。比如，"`abc/**`"匹配所有在目录"`abc`"下的文件，相对于`.gitignore`的路径，具有无限的深度(.gitignore下的任意目录)。
+ 
+ 一个斜杠后面跟随两个连续的星号代表匹配零或多个目录。比如，"`a/**/b`"匹配"`a/b`"，"`a/x/b`"，"`a/x/y/b`"等等，不同于"`a/*/b`"，后者只能匹配其中的一级目录，比如"`a/x/b`"
+ 
+ 其他连续的星号被当做常规的星号并且会根据先前的规则匹配，比如"`***`"或"`****`"等效于"`**`"

# 配置
## 可选的配置变量`core.excludesFile`表示一个包含要排除的文件名的patterns的文件的路径，与`$GIT_DIR/info/exclude`相似。除了`$GIT_DIR/info/exclude`中的patterns之外，还使用了排除文件中的patterns。
