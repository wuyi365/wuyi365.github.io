---
layout: post
title: "一个jekyll在博客中插入图片的小问题"
description: ""
category: 技术
tags: [博客,Jekyll,Markdown]
---
{% include JB/setup %}
Markdown里插入图片的语法大概是这样的：  
 
     ![Test01](/assets/image/ruiou01.jpg)

或者直接用html语言：    

    <img src="/assets/image/ruiou01.jpg" alt="Test" />    

注意这里的路径就是你blog目录根目录下的路径，对于你的博客来说，这就是一个绝对路径。
我开始的时候，犯了一个错误，使用了这样的相对路径：   

     ![Test01](././assets/image/ruiou01.jpg)  
       
这样发布后文章图片在首页也可以显示，似乎没有问题，但是如果从归档(archiev)里进入这篇blog,图片就显示不出来了。
寻找原因，查看图片源地址，原来归档后，jekyll会按照日期建立目录,你所有的博客文章会放在_site/年/月/日这样的目录结构下。最开始发布博客后，首页里图片是这样的:    
  http://silentlake.me/assets/image/ruiou01.jpg   
没有问题。
归档后的文章图片呢，其地址会build成为：   
http://silentlake.me/assets/2014/06/27/assets/image/ruiou01.jpg   
解决方法就是最好不要使用相对路径，因为jekyll会自动build并归档文章，使用相对路径的图片可能会导致某些路径问题。

虽然大部分人都不会遇到这个问题，还是记录下吧。万一呢，我有个感觉，不管是jekyll建博客还是其他技术，对于新手来说，总是遇到各种问题，在网上搜寻google答案的时候，又总觉得别人的答案不够详细，后来解决后呢，你会发现这个问题其实很简单，你也懒得详细记录了。所以，我还是写点吧。   

以上。