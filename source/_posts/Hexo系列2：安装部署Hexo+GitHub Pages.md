---
title: Hexo系列2：安装部署 Hexo+GitHub Pages（MAC）
urlname: Install-and-Deploy-Hexo+GitHub(MAC)
tags:
  - Hexo
  - GitHub-Pages
  - Token
  - MAC
categories:
  - Blog-Building
abbrlink: 39009
---

一篇介绍如何在Mac上安装部署Hexo+GitHub Pages的文章。

## 前言

准备：
- 一台Mac
- 已安装Git
- 已安装Homebrew
- 已创建GitHub账号

## Hexo

安装Hexo的大致流程为：安装—＞初始化一＞启动一＞写博客一＞部署

### 安装依赖环境

``` 
brew install node
 ```
 
### 安装Hexo

```
npm install -g hexo-cli 
```

### 初始化

```
mkdir blog
cd blog //一定要在blog目录下
hexo init
```

### 启动

```
hexo s
```

在浏览器输入：[http://localhost:4000](http://localhost:4000)，可以看到一篇默认博客`Hello World`

### 写博客

ctrl + c 断开链接，新建博文：

```
创建新博客：hexo new "my first blog"
```

可以看到，在目录`blog/source/_posts`下生成了一个`my first blog.md`文件，这就是你的博客，编辑该文件

可以编写边调试看效果：

```
清理生成： hexo clean 
生成页面： hexo g
启动服务： hexo s
```

### 部署

本地博客部署到 GitHub Pages，需要先在 GitHub 建一个仓库，然后生成一个`Token`来保证本地的博客能推送到远端。

##  <span id="jump">GitHub Pages</span>

### 创建 yourname.github.io 仓库

进入[GitHub官网](https://github.com),新建一个公开的名为 `yourname.github.io`  的仓库(yourname为你的用户名)。例如：[我的仓库地址](https://github.com/shiyiqing/shiyiqing.github.io)

### GitHub生成Token

生成 Token 步骤为：

点击`账户右上角头像` —＞ `Settings` —＞ `Developer Settings` —＞ `Personal Access Tokens(classic)` —＞ `Generate New Token(classic)` —＞ 设置`Token名称`、`到期时间`、`权限`（repo勾上） —＞ `Generate Token` —＞ 复制`Token`（**离开当前页面，将无法再看到它！！！**）

## 部署到GitHub Pages

### 安装部署插件

`ctrl + c` 断开链接，在`blog`目录下：

```
npm install hexo-deployer-git --save
```

### 修改 hexo 配置

- 打开 Hexo 配置文件 : `_config.yml`

- 修改 repo 为[2.  GitHub Pages](#jump)创建的仓库地址

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/yourname/yourname.github.io.git //将yourname替换成你的用户名
  branch: master
```
### 部署到远端

```
hexo d
```

中间会让输入 `github 用户名和密码`，密码用[2.  GitHub Pages](#jump)生成的`Token`代替。

### 访问博客

博客网址：`https://github.com/yourname/yourname.github.io` 

## 遇到的问题

### Error: Cannot download non-corrupt https://formulae.brew.sh/api/formula.json!

解决：`export HOMEBREW_NO_INSTALL_FROM_API=1`

参考：[brew upgrade error #14516](https://github.com/Homebrew/brew/issues/14516)

### Github pages 报错404无法打开

解决：清除缓存

- 清除Google 浏览器缓存

```
快捷键：Ctrl+Shift+Del 
```

- 清除Hexo本地缓存

```
hexo clean
```

参考：[官方文档](https://docs.github.com/zh/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites#githubs-status-page)

### dyld[69655]: Library not loaded: /usr/local/opt/icu4c/lib/libicuio.72.dylib

这个不是搭建博客遇到的问题，而是第二天在工作项目中arc diff时出现的问题。

参考网上教程，进行了一通操作，才解决。

解决步骤：
```
brew upgrade //没用

brew reinstall icu4c //没用

brew upgrade node //没用

brew switch icu4c <version>  //没用 （switch → link）
```

参考：[arc diff报错](https://stackoverflow.com/questions/53828891/dyld-library-not-loaded-usr-local-opt-icu4c-lib-libicui18n-62-dylib-error-run)

再仔细看了一下报错，发现问题原因是php的版本不匹配，需要升级到8.0。

于是：`brew install php@8.0`

报错：`Error: php@8.0 has been disabled because it is a versioned formula!`

解决：`brew install shivammathur/php/php@8.0`

参考：[brew install php@8.0报错](https://blog.csdn.net/tekin_cn/article/details/135318376)

## 总结

解决问题步骤：

1. **读懂问题**：学会看报错；

2. **搜索引擎**：Google > Baidu，官方文档 > github > stackoverflow > 国内博客；

3. **请求帮助**：网上文章下留言，或者问认识的朋友。

## 参考资料

[1]  笑胖仔 , (2020-04-18) , GitHub Pages + Hexo免费搭建个人博客_Mac , [知乎专栏] , https://zhuanlan.zhihu.com/p/114195340

