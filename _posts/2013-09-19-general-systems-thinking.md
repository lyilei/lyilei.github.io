---
title: "一些常用的Git命令"
description: "由于日常工作中还是以SVN为主，所以有些Git命令会慢慢地被遗忘，这里权当做个查询的参考了"
layout: post
categories: Git
tags: Git
disqus_comments: true
---

Subversion 还是目前工作中的首选，原因是大部分的客户和公司内部的Repo都还是基于它的。由于博客是用 [ruhoh](http://ruhoh.com) 搭建的，还有就是平时随意写的一些code也托管在了 [GitHub](https://github.com) 上，所以需要一些Git的常用命令。正是由于不经常用的缘故，好多的命令都是用的时候一通的Google，随后就直接忘记了。

从服务器上 clone 代码库的命令比较简单，如下：  
{% highlight sh %}
    $ git clone https://github.com/lyilei/lyilei.toys.com.git1
{% endhighlight %}
本地编辑之后提交到本地库：  
{% highlight sh %}
$ git add edited_filename
$ git commit -m “the reason of modification”
{% endhighlight  %}
	
Push 到远程服务器：  
	{% highlight sh %}$ git push origin master{% endhighlight  %}

从远程服务器 Pull 别人的更新：  
	{% highlight sh %}$ git pull origin master{% endhighlight  %}
	
有些时候，需要将本地的一个 Project 的文件放到远程服务器已经创建好的一个 Blank Repo 里面：  
{% highlight sh %}
$ git init
$ git add .
$ git -a -m “comments”
$ git remote add origin https://github.com/lyilei/lyilei.toys.com.git
$ git push origin master
{% endhighlight  %}	

最后的两步可以合并成一步：
{% highlight sh %} $ git push git@lyilei:lyilei.toys.com.git master{% endhighlight  %}
上面的 Repo 是预先在服务器上面建好的，如果没有该 Repo，该命令则会自动创建。

如果在执行`git push origin master`是碰到`error: src refspec master does not match any`的错误，则是由于项目为空的原因，需要完成至少一次 add >> commit 的过程.


