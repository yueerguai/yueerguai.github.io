---
title: Helio Blog
date: 2023-09-15 14:18:26
tags:
---

> 从13号下午3点开始搞博客，最终在12点11分初步建立
>
> 参考教程为https://godweiyang.com/2018/04/13/hexo-blog/
>
> 操作期间有时截了图，有些步骤忘了截图，为搭建完了之后去截的图





## 安装Node.js和Git

我是直接通过教程里的链接进入下载界面，没有在官网上搜索最新版下载。

然后通过指令分别检查是否安装成功

```
node -v
```

```
npm -v
```

```
git --version
```

结果如下

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914221409641.png" alt="image-20230914221409641" style="zoom:50%;" />

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914221345994.png" alt="image-20230914221345994" style="zoom:50%;" />

## 注册Github账号

首先，我打开官网https://github.com

此时，我还很幸运，打开得很顺利，然后成功注册了账号，验证了邮箱

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914222018737.png" alt="image-20230914222018737" style="zoom:50%;" />

然后，新建一个项目，再建立GitHub Pages

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914222352959.png" alt="image-20230914222352959" style="zoom: 33%;" />

上图是建好的，在这个过程中，我遇到了**第一个困难**，就是关于github pages的建立

教程上说：“点击Settings，向下拉到最后有个GitHub Pages，点击Choose a theme选择一个主题”

我点击了Settings,往下拉到了最后，但是最后不是GitHub Pages，而是

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914222800670.png" alt="image-20230914222800670" style="zoom:33%;" />

我到处都找不到GitHub Pages，这让我很恼火，卡了一些时间，让我怀疑是不是自己的账号注册不成功。

后来，我在侧边栏中找到了Pages,成功新建了一个pages。

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914223227872.png" alt="image-20230914223227872" style="zoom: 33%;" />

此时过程开始跟教程产生差异，我还是没能完全贴合教程步骤，决定先放放进行下一步

## 安装Hexo

> 在这一步我遇到了**第二个困难**，卡了相当长的时间

我在D盘中新建了一个文件夹，

![image-20230914223556688](image-20230914223556688.png)

然后按照教程，在该目录下右键点击Git Bash Here，打开git的控制台窗口

开始输入以下指令

```
npm i hexo-cli -g
```

```
hexo -v
```

```
hexo init
```

```
npm install
```

```
hexo g
```

```
hexo s
```

此时的我并不是很清楚这些指令都是在干什么的，也不知道控制面板返回来的信息是否是正确的。

教程如是说：“这样本地的网站配置也弄好啦，输入hexo g生成静态网页，然后输入hexo s打开本地服务器，然后浏览器打开http://localhost:4000/，就可以看到我们的博客啦”

然而我并没有看到这一行“http://localhost:4000/”，才知道这个过程出错了

当时太慌了，没想起来截屏。

然后我就开始重复操作，几遍过后没有成功，就想回github网站看看能不能有什么帮助。

然后我遇到了**第三个问题**，就是github.com死活进不去了！！！

我在多次尝试无果后选择上知乎询问。

方法一修改host文件，这个有的时候有用，然后隔了一会儿就没用了。

方法二国内镜像（没搞懂怎么设置）

方法三，偶然看到说在Microsoft Store上下载一个Watt Toolkit来加速非常有用，

我就打开了电脑Microsoft Store，下载Watt Toolkit。果然很高效，github官网一下子就进去了。

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914225426301.png" alt="image-20230914225426301" style="zoom: 33%;" />

解决了进入github.com的问题，我又回去着手解决hexo配置的问题。

我开始浏览大量知乎上关于如何建立博客的帖子，了解了很多东西，通过讨论区也看到了许多可能发生的问题。

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914225908974.png" alt="image-20230914225908974" style="zoom:25%;" />

虽然没有解决我的问题，但是我终于知道了我的问题出现在使用hexo init的时候，控制面板返回的信息开始出错了。所以我就复制了此时面板中的报错信息，直接百度搜索，果然找到了答案

[安装Hexo后，运行指令一直出现，ERR_CONSOLE_WRITABLE_STREAM，搜索wei'guo_编程语言-CSDN问答](https://ask.csdn.net/questions/1092767)

评论区第一条说“去官网下载升级你的node版本就可以了”

我才反应过来，连忙去看了看教程发表的日期，是2018年。明白了是我node,js版本太低，我就删掉了现有的node.js，去官网下载了最新版的node.js

<img src="C:\Users\月儿乖\AppData\Roaming\Typora\typora-user-images\image-20230914230856101.png" alt="image-20230914230856101" style="zoom: 50%;" />

现在终于快成功了。

然后我再次开始输入指令hexo init

控制面板返回报错

Error: EPERM: operation not permitted, mkdir ‘D:\‘

这次我直接复制粘贴到百度寻求帮助，搜集到了几种方法

方法一删掉C\用户\账户名下目录下多余的.npmrc文件。（试了没用）

方法二以管理员身份执行命令。（也没用）

方法三设置文件属性“完全控制”

（设置完成后，我试了一下也不行）

最后我结合二，三，设置完全控制后再以管理者身份执行命令，终于成功了。

此时已经是晚上12：11分

<img src="../../../../Typora/文件/image-20230915134107319.png" alt="image-20230915134107319" style="zoom:50%;" />

然后我进入http://localhost:4000/，页面如下

<img src="../../../../Typora/文件/image-20230915134210731.png" alt="image-20230915134210731" style="zoom: 50%;" />

## 连接Github与本地

按照网上教程成功得到了SSH，结果如下

<img src="../../../../Typora/文件/image-20230915134923754.png" alt="image-20230915134923754" style="zoom: 50%;" />

<img src="../../../../Typora/文件/image-20230915140813172.png" alt="image-20230915140813172" style="zoom:50%;" />

