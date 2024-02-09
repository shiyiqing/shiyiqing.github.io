---
title: Hexo系列1：为什么选择Hexo+GitHub Pages
urlname: Why-choose-Hexo+GitHub
tags:
  - Hexo
  - GitHub-Pages
categories:
  - Blog-Building
abbrlink: 39009
---

一篇介绍为什么选用Hexo+GitHub Pages的方式搭建个人博客的文章。

##  前言

### 为什么搭建个人博客

其实在大学期间就有写博客的想法，工作以后逐渐认识到文档沉淀的重要性，加上平时有用notion、印象笔记、小红书记录的习惯。建站的导火索就是在小红书发的一篇原创笔记，被判包含违规营销内容。于是下定决心自己搭一个博客。

个人博客好处：无需平台审核、没有外链限制、自定义主题等。

### 我的需求

- 支持markdown格式。
- 丰富的主题和插件。
- 社区成员多且活跃。
- 简单迅速成本低。

## 主流博客框架

- **博客三方平台**：博客园、CSDN、简书、掘金、知乎专栏、segmentFault、开源中国、腾讯云社区、阿里云云栖社区。
- **博客自建框架**：WordPress、Typecho、Ghost（动态框架）、Hexo、Jekyll、Hugo、vuepress、notion(静态框架)。
- **自己写**。
  
### 动态框架和静态框架的区别

**动态框架**，即用户每一次交互，都会从**数据库**获取数据来动态渲染网页。动态框架**需要一个云服务器**，不仅能实现个人博客，还可以搭建商用网站。

**静态框架**，即本地生成静态页面，然后托管到服务器上自动运行渲染网页。静态框架**不需要云服务器**。

### 博客框架市场占有率

美国博客框架排名前三为**WordPress、Blogger和Tumblr**。

国内博客框架排名前三为**WordPress、Hexo和Ghost**。

数据来源：[builtwith](https://pro.builtwith.com/)

更多内容详见：

[1)博客的发展简史和框架简介](https://justgoidea.com/posts/2023-056/)

[2)如何挑选博客框架、在线博客平台](https://ednovas.xyz/2021/07/03/blog/)

## WordPress or Hexo？

### WordPress

[WordPress](https://wordpress.org/)是一个基于 PHP 和 MysQL 的动态博客框架。

**WordPress**允许用户创建和管理自己的网站，是一个功能强大的内容管理系统（CMS）。它的动态展示分为3个阶段，初始化(资源加载)、准备数据和渲染。

**优点：**
- 具有很高的扩展性，适合做一些功能较为复杂的网站。
- 拥有**后台管理**界面，可以实现用户注册等功能。

**缺点：**
- 主题偏商业化。
- 需要有**云服务器**的支持，对云服务器的带宽有一定的要求。
- 相较于静态博客，动态博客更加**容易受到攻击和崩溃**。
  
### Hexo

[Hexo](https://hexo.io/zh-cn/)是一个基于Node.js的快速、简洁且高效的静态博客框架。

**Hexo** 的工作原理是将用户编写的 **Markdown** 文件转换为 **HTML** 文件，然后渲染生成静态网站。 

**优点：**
- 极速生成静态页面。
- **md文档格式**，方便备份和转移。
- 不需要云服务器，不用担心**数据库和空间的安全性**。

**缺点：**
- 评论、分享等功能依赖于第三方插件。
- 每次更新博客需要**重新部署至GitHub**。
- 配置都在本地，如果换电脑，需要**重新配置环境**。

参考：[wordpress和hexo哪个更适合用来搭建个人博客？](https://www.zhihu.com/question/53068081)
  
## GitHub Pages

静态博客的托管服务可用GitHub、Coding、Gitee、Netlify、Vercel等。这些服务都是基于 Git的，将博客源码存放在平台，托管服务自动拉取并构建网页。因为平时用github比较多，就选择了Github Pages来托管博客。

**Github Pages**：简称 pages 服务，每个仓库都有一个pages 服务，可用来展示项目，通过简单的设置项目的index.html，并以此做为入口供用户参观访问。

**缺点：**
- GitHub Pages 源存储库的建议限制为 **1 GB**。
- 已发布的 GitHub Pages 网站不得大于 **1 GB**。
- 如果 GitHub Pages 部署时间超过 **10 分钟**，则会超时。
- GitHub Pages 网站的软带宽限制为每月 **100 GB**。
- GitHub Pages 站点的软限制为每小时 **10 次**构建。

详见官方文档：[使用限制](help.github.com/en/articles/what-is-github-pages#usage-limits)

参考：[常见静态网站托管平台使用及多节点部署方案](https://hexo.fluid-dev.com/posts/hexo-static/)

## 总结

除了Hexo+GitHub Pages，还有许多其他的优秀的博客搭建方式。根据自己的需求和技术水平选择合适的工具就可以了。一定记住首先看官方文档。

