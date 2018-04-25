---
title: Hexo 1：利用Hexo+GitHub Pages开发自己的博客
date: 2017-12-30 22:29:42
tags:
- Github
- Pages
- Node.js
- Hexo
- Blog
- Git
categories: 
- Blog
- Hexo
---
![](https://i.loli.net/2018/01/13/5a5a26b754feb.jpg)

## 1 前言

本篇教程基于Windows10，Windows其他版本差异不大，可供参考。本人搜集整合网上的资料，以及坑坑坑，写出本篇文章，部分内容可能会与其他教程雷同，请不要介意。

<!-- more -->

## 2 资料

### 2.1 [Github](https://github.com/)

gitHub是一个面向[开源及私有软件项目的托管平台，因为只支持git 作为唯一的版本库格式进行托管，故名gitHub。

 gitHub于2008年4月10日正式上线，除了git代码仓库托管及基本的 Web管理界面以外，还提供了订阅、讨论组、文本渲染、在线文件编辑器、协作图谱（报表）、代码片段分享（Gist）等功能。目前，其注册用户已经超过350万，托管版本数量也是非常之多，其中不乏知名开源项目 Rubyon Rails、jQuery、python等

###  2.2 [Github Pages](https://pages.github.com/)

GitHub Pages是一个静态站点托管服务。

GitHub Pages设计用于直接从GitHub存储库托管您的个人，组织或项目页面。要详细了解GitHub Pages网站的不同类型，请参阅“[用户，组织和项目页面](https://help.github.com/articles/user-organization-and-project-pages/)“。

您可以在线创建和发布GitHub页面。如果您更喜欢在本地工作，则可以使用 [GitHub Desktop](http://desktop.github.com/) 或 [命令行](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line)。

GitHub Pages是一个静态网站托管服务，不支持服务器端代码，如PHP，Ruby或Python

### 2.3 [Git(分布式版本控制系统)](https://baike.baidu.com/item/GIT/12647237?fr=aladdin)  -[官网地址](https://git-scm.com/) （吐槽，页面太简陋）
Git是一款免费、开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。

Git是一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。

### 2.4 [Node.js](https://baike.baidu.com/item/node.js/7567977?fr=aladdin)  -[官网地址](https://nodejs.org/en/)

Node.js是一个Javascript运行环境(runtime)，发布于2009年5月，由Ryan Dahl开发，实质是对Chrome V8引擎进行了封装。Node.js对一些特殊用例进行优化，提供替代的API，使得V8在非浏览器环境下运行得更好。

V8引擎执行Javascript的速度非常快，性能非常好。Node.js是一个基于Chrome JavaScript运行时建立的平台， 用于方便地搭建响应速度快、易于扩展的网络应用。Node.js 使用事件驱动， 非阻塞I/O模型而得以轻量和高效，非常适合在分布式设备上运行数据密集型的实时应用。

### 2.5 <a href="https://hexo.io/" target="_blank" rel="noopener">Hexo</a>

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

## 3 正式搭建

讲了真么多，该实践了，就开始在萎软（滑稽）上开始搭建自己的Blog-Hexo。

### 3.1 配置环境

#### 3.1.1 安装Node.js

我已在资料中提供了网址，点击后在界面中会有两个模块，如下图：

![](https://i.loli.net/2018/01/13/5a5a273348688.jpg)

两个都可以选择，下载可能较慢，唯有等待，也可以参见网上的其他方法。下载下来后，打开.msi文件，一路next即可。

<div class="note info"><p>如若不是x64，在导航栏选择Download，在里面下载即可。附：[淘宝国内镜像的快速安装网址](https://npm.taobao.org/mirrors/node)</p></div>

#### 3.1.2 安装Git  [下载地址](https://git-scm.com/downloads)

点击，缓慢的等待即可（哭哭。。。哭）

### 3.2 搭建Hexo

经过长长长的等待，终于可以再来一次长长长的等待了！！！

![](https://i.loli.net/2018/01/13/5a5a27d46662b.jpg)

生气中。。。。。。

#### 3.2.1 安装Hexo

因为npm在国外，被天朝伟大的墙墙墙（**GFW**）挡住了，所以我们使用淘宝的镜像就好啦！

打开cmd，执行如下命令

```[] cmd
npm install -g cnpm --registry=https://registry.npm.taobao.org
```
一定要把360、腾讯电脑管家那些玩意儿给关掉，有几次我失败了，强制关机才干掉电脑。

正式安装，执行如下命令：

```[] cmd
cnpm install -g hexo-cli
```

（在默认路径即可）

#### 3.2.2 建立站点

现在任意一个盘符例建一个文件夹Blog，再在里边建一个文件夹（如your_name.github.io，这会用到Github，在后边介绍）。比如我要进入`D:\Blog\your_name.github.io`，那就输入 `D:`回车，然后再 
``` [] 所在目录：~/blog/
cd Blog\your_name.github.io
```
根据 Hexo 的官方文档，依次执行下面两条命令，建立我们的新网站：

``` [] 所在目录：~/blog/
hexo init
cnpm install（如果失败，试npm install）
```
现在，你在终端中输入`hexo g & hexo s`（确保路径不变），然后点开 http://localhost:4000/ ，恭喜你！已经在本地搭建好博客了(๑•̀ㅂ•́)و✧！距离成功只差下一步——部署博客到 Github Pages 了～

<div class="note danger"><p>如果文件夹不为空，会报错。</p></div>

#### 3.2.3  发布文章

本章不介绍，下一行将详细介绍，建议先配置，后码文。

#### 3.2.4 目录介绍

在你完成3.2.2节时，你会发现主文件夹下的目录是这样的：

``` [] 所在目录：~/blog/
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   └── _posts （文章）
├── public
├── node_modules
├── .deploy_git （没有没关系）
└── themes
```

- `_config.yml` 文件存放着网站的配置信息，可以在这里配置大部分的参数。
- `package.json` 文件存放着插件信息，从中可以查看那些插件已经安装。
- `scaffolds` 是模板文件夹，新建文章时，Hexo 会根据 scaffold 来建立文件，不过这个模板和后面的主题里指的模板不一样。
- `source` 是存放用户资源的地方的文件夹。Markdown 和 HTML 文件会被解析并放到 `public` 文件夹，其他文件会被拷贝过去。
- `themes` 主题文件夹，Hexo 会根据主题来生成静态页面，我们以后自己安装的主题也都会放在这个文件夹下面，默认的 landscape 主题（丑）已经在里面了。
- `public` 执行hexo generate命令，输出的静态网页内容目录
- `node_modules` 存放Hexo的一些插件等等（病句）。
- `.deploy_git` 执行hexo deploy命令部署到GitHub上的内容目录。

#### 3.2.5 小结

3.2节内容详细讲述了安装Hexo的方法，可能还会有一些问题，欢迎QAQ。

此外，有一些内容将在配置中介绍，可移步一观（点我）。

### 3.3 部署到Github上

我们已经将Hexo的雏形搭建完毕，为了能从外网访问到博客，所以我们将它托管到Github上。

| 问题                            |                                       解答 |
| ----------------------------- | ---------------------------------------: |
| 为什么要部署到 Github Pages 上？       |               首先免费，其次省心，最后可以学习使用 Github。 |
| Github Pages 有容量限制吗？          | 有，由 What is GitHub Pages? 可知：大小限制为 1 GB，一个月 100 GB 流量。 |
| 超出限制的容量怎么办？                   | 讲真，如果图片音乐视频等大文件都放在 七牛云 、阿里云OSS 或其它云存储上，那么压根不用担心，因为我的博客现在也才用了很少 ，所以无需担心。 |
| 国内访问速度行不行，有必要同时部署在 Coding 上吗？ | 个人感觉完全没必要，自己不用梯子时，感觉访问速度可以，毕竟站点的大文件都是放在了云存储上。 |
| 我可以用自己的域名吗？                   | 可以，在`~/blog/source/`目录下添加 CNAME 文件即可，教程自己 Google。 |

#### 3.3.1 登录Github

网上注册Github以及登录有很多教程，在此就不再赘述。

注：
1、Github注册为个人、企业等等都可以，只不过付费的可以设置私密，不让人家看到你的代  码，但也有不计其数的代码在Github上是开放的，除非你是公司机密，否则影响不太大。
2、如果嫌官网是英文，可以去下载Chrome的浏览器，它可以自动翻译，从官网下下来后，点安装程序，可能还要下载，等一会即可，如果长时间不行，那你就是被墙拦了（如需上官网下Chrome，请私信我QQ，获取谷歌访问助手，将它装在现有的浏览器上，然后就可以上Google了）。

<div class="note primary"><p>突然发现自己话好多：）</p></div>

#### 3.3.2 创建repository

登录Github后，点右上角的”+”号，会出现一栏，点击”New repository”，设置如下图：

![](https://i.loli.net/2018/01/13/5a5a25256d132.png)

`yourname`是你的Github的账户名。Description随便写即可。设置完毕后，点击那个绿色键”Create repository”。

到此，Github上到此结束，接下来，我们要把Git和Github连起来。

#### 3.3.3 Setting up Git

根据 Github 的官方文档  [Setting up Git](https://help.github.com/articles/set-up-git/#setting-up-git) ，这一操作的目的是 Tell Git your *name* so your commits will be properly labeled 和 Tell Git the *email address* that will be associated with your Git commits，也就是告诉版本控制软件 Git 接下来这台电脑上提交的文件是 E-mail 地址是什么的谁谁谁提交的。在 Git Bash 中执行如下代码即可：

``` [] Git Bash
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR EMAIL ADDRESS"
```

其中，`YOUR NAME` 是自己取的名字，`YOUR EMAIL ADDRESS` 是自己的邮箱。由于自己的博客网站就自己一个人提交，所以就都设置成跟 Github 用户名和邮箱相同了。但其实是可以不同的，因为对于很多项目，并不只有一个开发者，Github 允许多人向同一个 Repo 提交，这里提供用户名和邮箱，只是为了搞清楚哪些代码是谁谁谁提交的。

#### 3.3.4 Authenticating with GitHub from Git
这一整章，我们的最终目的是实现在终端中敲入 `hexo deploy` 后，Hexo 会将我们本地的 `public` 文件夹下的东西上传到 Github 服务器，这样我们就可以通过 `your_name.github.io` 这个域名（`your_name` 是你的 Github 用户名）看到我们已经上网的博客网站了。为了实现这个目的，首先我们先要让本地的电脑和 Github 服务器建立起某种联系，也就是让 Github 服务器信任由我这台电脑提交的东西，接受，并存放到 `your_name.github.io` 这个 Repo 下面，与 Github 服务器建立信任的这个环节就是身份认证（Authenticating ）。根据 Github 的官方文档 [Authenticating with GitHub from Git](https://help.github.com/articles/set-up-git/#next-steps-authenticating-with-github-from-git) 这里，我们选择 [Connecting over SSH](https://help.github.com/articles/set-up-git/#connecting-over-ssh) 这一种方式。在 Github 的官方文档 [Categories / SSH](https://help.github.com/categories/authenticating-to-github/) 下，我们能找到关于 Github 与 SSH 的资料。

##### 3.3.4.1 生成新的 SSH key

根据 Github 的官方文档 <a href="https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#generating-a-new-ssh-key" target="_blank" rel="noopener">Generating a new SSH key</a> ， 我们在 Git Bash 下执行如下命令，生成 SSH key

``` [] Git Bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

其中，`your_email@example.com` 是你的 Github 注册邮箱。然后，Git Bash 中会出现

``` [] Git Bash
Generating public/private rsa key pair.
```
表示新的 SSH 已经生成了。随后会出现

``` [] Git Bash
Enter a file in which to save the key
(/Users/you/.ssh/id_rsa): [Press enter]
```

这里 `id_rsa` 是生成的 key 文件的文件名，默认都是这个；如果不是，在后面用到 `id_rsa` 的地方请替换成出现的名字。这条信息是让你选择 SSH key 存放的地点，按回车选择默认的即可。回车后，还会出现

``` [] Git Bash
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```

让你设置使用 SSH 密钥时的密码，由于我们都是在自己个人的电脑上操作，所以仍然回车，不设置密码即可。

##### 3.3.4.2 将 SSH key 添加到 ssh-agent

根据 Wikipedia，ssh-agent 是一个在本地登录会话持续时间内，将未加密的密钥存储在内存中，并使用 Unix 域套接字与 SSH 客户端进行通信的程序。根据 Github 的官方文档 [Adding your SSH key to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#adding-your-ssh-key-to-the-ssh-agent) ， 我们在 Git Bash 下执行如下命令，开启 ssh-agent

``` [] Git Bash
eval "$(ssh-agent -s)"
```

然后我们要将这个 SSH key 添加到 ssh-agent 里去，运行如下命令，其中 `id_rsa` 是你的 key 文件的文件名：

``` [] Git Bash
ssh-add ~/.ssh/id_rsa
```

##### 3.3.4.3 将 SSH key 添加到 Github 账户
Github 的官方文档 [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/) 已经图文并茂将如何在 Github 帐号中添加 SSH 介绍的非常清楚了。先是在 Git Bash 中将 SSH Key 拷贝出来：

进入`C:\Users\your_name\.ssh`，`your_name`是你电脑的账户名。进去后，找到`id_rsa.pub`，用记事本打开，复制里面的内容。然后登录 Github 帐号，依次点击自己的头像，Settings，SSH and GPG keys，New SSH key 或者 Add SSH key， 在 Title 这里输入 Key 的label，比如 your_name - PC，然后在 Key 里面把 SSH Key 粘贴进去，点击 Add SSH key 大功告成。

<div class="note success"><p>这下我们就已经生成身份认证的凭证 SSH key，分别放在自己本地电脑和 Github 服务器上，以后向 Github 提交内容的时候，两者的 Key 匹配就可以了，省去了我们每次输密码的时间。</p></div>

##### 3.3.4.4 测试 SSH 连接

在大功告成之前，为了稳妥起见，我们来测试一下自己跟 Github 服务器 SSH 连接是否已经建立起来了。Github 的官方文档 [Testing your SSH connection](https://help.github.com/articles/testing-your-ssh-connection/) 已经将次环节介绍得非常详细了。我们要做得就是在 Git Bash 中敲入

``` [] Git Bash
ssh -T git@github.com
```

你可能会看到类似于

``` [] Git Bash
The authenticity of host 'github.com (192.30.252.1)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
```

输入 `yes` 敲回车，就可以看到如下的成功信息了

``` [] Git Bash
Hi username! You've successfully authenticated, but GitHub does not
provide shell access.
```
至此为止，我们已经建立起了跟 Github 服务器的连接。其实我们也可以用 `git push` 命令，提交 `public` 文件夹下面的内容，不过 Hexo 更我们提供了更方便的途径。

#### 3.3.5 Hexo部署
Hexo 提供了 `hexo deploy` 命令，可以方便地将整个 `public` 文件夹部署到 Github 服务器上去。根据 Hexo 的官方文档 [基本操作 — 部署](https://hexo.io/zh-cn/docs/deployment.html) 我们只需要做以下两步：

- **Step 1:** 在终端中运行如下命令，安装 `hexo-deployer-git` 插件：

``` [] 所在目录：~/blog/
npm install hexo-deployer-git --save
```

- **Step 2:** 在` _config.yml` 中修改参数，如下所示：

``` diff 文件位置：~/blog/_config.yml
deploy:
- type:
+ type: git
+ repo: https://github.com/your_name/your_name.github.io.git
+ branch: master
```

其中，your_name 是你的 Github 帐号名。`repo` 对应的是你 `your_name.github.io` 这个项目的库（Repository）地址，进入这个项目的主页，点击 **Clone or download** 下拉菜单也能看到。`branch` 是分支名称，如果使用的是 GitHub 或 GitCafe 的话，程序会尝试自动检测，通常都是 `master`。 

<div class="note warning"><p>注意，冒号后的空格非常重要，一定要有！</p></div>

<div class="note success"><p>至此，在终端执行 `hexo deploy` 命令，就可以把我们的网站部署到 Github 服务器上。在第一次部署的时候，Github 还会跳出来一个小窗口，让你输入 Github 帐号和密码，输入即可。根据不少网友的说法以及我之前搭站的经验，等待 15 分钟的样子（也可能更快），就可以通过 your_name.github.io （your_name 是你的 Github 用户名）来访问自己的网站了。</p></div>

### 3.4 小结
在这章中，我们成功搭建了Hexo，并部署了Github Pages。庆祝ヾ(◍°∇°◍)ﾉﾞ

## 4 预告
在下一章中我们会着重论述主题的配置和一些插件，并剖析代码，继续分析Hexo，再见！！！