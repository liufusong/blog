---
title: github
date: 2017-04-08
tags:
---
摘要: github
<!--more-->

## git使用ssh方式上传代码与github
  - git生成公钥和私钥
    + 命令:`ssh-keygen -t rsa`生成的公钥与私钥文件会在当用户目录的.ssh目录下.


### 把代码push到服务器时需要先pull一下
  - 在pull之后如果远程的代码与本地的代码有冲突，git会先自动合并冲突，如果不能自动合并，就必需我们手动去处理冲突。

### 从服务器上pull代码到本地
  - 如果本地没有.git目录，需要先初始化一下。
  - 命令:`git pull [远程服务器地址] [远程的分支]`

### gh-pages分支-搭建博客.
  - 需要把自已博客的网页代码上传到github上的gh-pages分支
  - 然后就直接访问了
    + 访问的url形式: [github用户名].github.io/[仓库的名字]/[具体的页面]


### sourceTree , tortoiseGit


### npm
  - 官网[https://www.npmjs.com]
  - node package manager
  - 命令:
    + 初始化:`npm init`
    + 安装指定包:`npm install jquery --save`
    + 删除指定包:`npm remove jquery --save`
    + 下载安装package.json中dependencies属性对的文件:`npm install --production`

### browser-sync
  - 更改代码之后自动刷新浏览器
  - 需要使用npm进行全局安装:`npm install browser-sync -g`,-g表示安装到全局
  - 使用:`browser-sync start --server --files "./index.html,app.css,./css/*.css,*.*" `
  - --files参数指定要监视的文件，后面跟要监视的文件的文件路径以逗号分隔。

## gulp
  [官网](http://www.gulpjs.com)
  [中文网](http://www.gulpjs.com.cn)

- 前端自动化构建工具
  js压缩,var x,xname，混淆
  合并.
  css压缩
  html压压缩

- grunt ,webpack...


### 核心就5个方法
  - task,gulp中是一个个任务的形式来实现功能。
    + task('任务名',function(){
      .....
    });
  - src
    + src('./*.js')
  - dest('./minjs/')// 指定处理后的文件的输出路径.
  - watch('./*.js',['任务名1','任务名2']);
  - run('任务名');//执行指定的任务.

### gulp的安装
  - 使用npm 进行安装
  - `npm install gulp-cli -g`;

### gulp 使用

#### 使用时还需要在项目中通过npm非全局安装gulp
  - `npm install gulp --save-dev`


#### 还需要在当前项目根目录添加一个gulpfile.js文件来写具体的任务代码.

### gulp的一些插件
  - 也是使用npm安装
  - 对js代码进行压缩 gulp-uglify
  - 对代码进行合并 gulp-concat
  - 对css进行压缩 gulp-cssnano
  - 对html进行压缩 gulp-htmlmin