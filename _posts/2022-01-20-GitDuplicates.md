---
title: git补档
tags:
  - Git
---
  
## 准备一台装有CentOS 8的服务器或虚拟机 (后文统称服务器)

## 在服务器中安装nodejs以及git环境
### NodeJS
> 用我的路径`/root/Baioretto/lib/nodejs`举例(你可以将其换成你自己的)
> 下载地址: [https://nodejs.org/en/download/](https://nodejs.org/en/download/)
> 下载Linux Binaries (x64) 后, 将文件上传到服务器 (/root/Baioretto/lib/node-<version>-<distro>.tar.xz)
> 用 `tar -xJvf node-<version>-<distro>.tar.xz -C /root/Baioretto/lib/nodejs` 解压到lib下的nodejs文件夹中
> 接下来你应当配置环境变量, 教程: [新应用环境变量配置](https://baioretto.com/_posts/2022-01-20-CentOSEnvironmentVariables/)
> 我的是 "PATH=/root/Baioretto/lib/nodejs/node-v16.13.2-linux-x64/bin:$PATH"
> 输入`node -v`, `npm --version`, `npx -v` 来查看版本以检查是否正确安装

### Git
> 用我的路径`/root/Baioretto/lib/git`举例(你可以将其换成你自己的)
> 下载地址: [https://git-scm.com/download/linux](https://git-scm.com/download/linux)
> 下载后, 将文件上传到服务器 (/root/Baioretto/lib/git-<version>.tar.gz)
> 用 `tar -xzvf git-$VERSION.tar.gz -C /root/Baioretto/lib/git` 解压到lib下的git文件夹中
> 进入安装包路径 `cd git-<version>/`
> 配置安装路径 `./configure --prefix=<where you install to>`
> 我的是 "/root/Baioretto/lib/git"
> 生成可执行文件 `make`
> 生成完毕后的可执行文件安装到目录 `make install`
> 接下来你应当配置环境变量, 教程: [新应用环境变量配置](https://baioretto.com/_posts/2022-01-20-CentOSEnvironmentVariables/)
> 我的是 "PATH=/root/Baioretto/lib/git/bin:$PATH"
> 输入`git --version` 来查看版本以检查是否正确安装

## 回到你的工作环境
### 克隆我的项目并发布到你的仓库(一定要发布在你自己的仓库)
> 克隆我的项目 `git clone https://github.com/Ba1oretto/auto-commit.git`
> 删掉隐藏文件夹 *.git*
> 重新初始化并提交, 发布到你自己的仓库中

## 回到服务器
### 你需要用ssh的方式clone
> 首先查看服务器的ssh密钥 `cd ~/.ssh`, `ls`
> 如果没有看到私钥 *id_rsa* 和公钥 *id_rsa.pub* 这两个密钥, 则执行生成密钥指令 `ssh-keygen -t rsa`
> 将公钥拷贝到你的github keys`cat id_rsa.pub`
> 打开github, 位于 *Settings* 中的 *account settings*, 在 *SSH and GPG keys* 中 *New SSH key*, 将你的密钥拷贝到 *Key* 中, *Title* 自定
> 测试链接 `ssh git@github.com`, 如果看到 `Hi xxx! You've successfully authenticated, but GitHub does not provide shell access.` 那么则连接成功
### 调通后将你仓库的项目克隆到你想要的目录中
> 克隆我的项目到你想要的目录中`git clone git@github.com:Ba1oretto/auto-commit.git`
> 修改 *loop.sh* 中的 `bash /root/Baioretto/workspace/auto-commit/push.sh` 成你自己的 `bash <your path>/push.sh` (一定要保证路径正确)
> 修改 *push.sh* 中的 `bash /root/Baioretto/workspace/auto-commit/write.sh` 成你自己的 `bash <your path>/write.sh` (一定要保证路径正确)

## 开始补档
### 运行loop.sh
> `bash loop.sh <times>`
> <times>为你循环的次数, 每次循环会 push 九个 commit
> 第一次运行会让你配置邮箱与用户名
> 可以在write中修改每次循环的 commit 的次数
> *node add.js && git add records.txt && git commit -a -m '补档'* 为一次 commit