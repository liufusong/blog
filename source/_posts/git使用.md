---
title: git工具
date: 2017-04-08
tags:
---
摘要: Git是一款源代码管理工具(版本控制工具)
<!--more-->
正文:

## Git

### 什么是Git?
  - Git是一款源代码管理工具(版本控制工具)
    - 我们写的代码需要使用Git进行管理。
  1.0是稳定
  2.0加了新功能
  - 源代码有必要管理起吗？
  - 有必要，因为人工的去处理不同的版本，做相应备份会很麻烦。
  - svn,vss,vcs,tfs.....
  -Git是linux之父当年为了维护linux---linus之前也是手动维护合并把文件发给Linus
  - BitKeeper(收费)
  - 有人想破解(不给提供免费使用)
  - linus自己写了一个版本管理的工具（Git）


### 分布式版本管理工具，集中式
  - git属于分布式
  - svn集中式

### git安装

### git初始化一个仓库
  - 其实就是创建了一个.git隐藏目录
  - 命令:` git init `;
    + 想在哪个目录创建.git目录，就是哪个目录打开工具然后写命令.
    + 一般是在项目的根目录执行这个命令.


### 自报家门
  - 配置用户名 : `git config user.name "testName"`
  - 配置邮箱   : `git config user.email "test@sina.com"`
  - 查看配置信息: `git config --list`


### 把代码提交到仓库中
  - 1.先把代码添加到暂存区(就相当于放到仓库门口)
    + 命令:`git add 文件路径`
    + 示例:`git add ./reademe.md`
    + 可以使用`git add .`这个命令，批量把当前目录下所有修改过的文件添加到暂存区。

  - 2.把暂存区的文件提交仓库里
    + 命令: `git commit -m "注释" `
    + 示例: `git commit -m "我们添加了一个新的功能"`
    + -m 表示指定一个字符串，作为提交的说明(相当于注释);

  - 合并add 与commit 命令
    + `git commit -a -m "这是使用合并添加与提交的操作"`;
    + 这里-a参数表明把所有修改后的文件一起添加到暂存区.(只是对修改后的文件有效，对于新添加的文件没有作用)


### 查看工作区状态
  - 命令:`git status`


### 添加忽略文件
  - 在项目中有一些文件是不需要提交的,我们需要把它忽略掉
  - 需要在.git文件夹所在目录新建一个名为.gitignore的文件
    然后在这个文件中写上需要被忽略的文件的路径。
    示例: /css/a.css
        : /css/*.css
        : /a.html


### 比对文件差异
  - 命令: `git diff`
    + 用来比较工作区内容与最近一次提交的内容的区别
    + 如果暂存区没有文件，就会将工作与代码与最近一次提交对比
  - 命令：`git diff --cached`  比较暂存区的文件和仓库中文件的区别
  - 对比之前某两次提交的文件的差异
    + 命令:`git diff [版本号1] [版本号2] [想比较的文件路径]`

### 查看日志
  - 命令:`git log`,可以查看每一次提交的日志
  - 命令:`git log --oneline` 表示使用简洁的形式输出提交日志


### 版本回退
  - 命令:`git reset --hard Head~1`
    + 这是将代码回退到上上一次提交时的状态
  - 命令:`git reset --hard Head~2`
    + 回退到上上上次
  - 命令:`git reset --hard Head~0`
    + 回退到上次提交时的状态,~0可以省略

  - 命令:`git reset --hard 版本号`
    + 通过每次提交时生成的版本号来回退版本

  - 通过`git reflog`命令可以查看之前所有版本切换的操作记录，可以通过这个命令得到的版本号回退到指定的版本。

### 创建分支
  - 命令:`git branch [分支名]`
    + 创建一个新分支
  - 命令:`git branch`
    + 查看当前所有的分支

### 切换分支
  - 命令:`git checkout [分支名]`
    + 切换分支后可以在切换后的分支中进行正常的操作

### 合并分支
  - 命令:`git merge [分支名]`
    + git会将指定的分支合并到当前分支.

### 删除分支
  - 命令:`git branch -d [分支名]`
    + 删除指定分支，-d参数表示要执行删除操作

### git提交中的冲突
  - 如果git不能自动合并分支，就会有冲突，我们需要手动解决冲突，然后再次提交


## github
### github与git
  - git 版本管理工具
  - github 就是一个网站，只是这个网站提供git服务器的功能


### 上传代码到git服务器(push)
  - 命令:`git push [远程服务器地址] [远程服务器的分支]`
     + 示例:`git push https://github.com/huoqishi/test002.git master`

  - 上传时可以使用一些简化的命令
    + 将远程服务器地址写成变量的形式
      * `git remote add [变量名]  [远程服务器地址]`
      * 示例:`git remote add origin https://github.com/huoqishi/test002.git`
      * 这样之后就可以直接使用origin来代替git push 后面写的地址了
        `git push origin master`
  - 还可以尽一步简化
    + 在push时加上-u参数，就会默认建立本地当前分支与远程指定分支的关联,下一次push时就不需要输入分支名了`git push origin`;

### 

