---
layout: post
title:  Node模块开发及发布
date:   2016-03-12 16:49:16
description: 一个简单的Node模块开发以及发布
---


使用Node很长时间了，都知道NPM是Node的包模块管理工具，也会经常通过NPM来安装一些模块。例如：

{% highlight ruby %}
sudo npm install -g bower
sudo npm install -g yo
sudo npm install -g grunt-cli
{% endhighlight %}

在[NPM官网](https://www.npmjs.com/)上，可以搜索到很多别人写好的模块。

这些都是已经存在的模块，我们也可以自己写一些牛逼的模块，发布到NPM社区上，供别人使用，自己手动实践下还是比较好的。[参考资料](http://www.elmerzhang.com/2011/09/nodejs-module-develop-publish/)

前提是你已经安装了Node和NPM，没有的可以先去[Node官网](https://nodejs.org/en/)下载安装。
{% highlight ruby %}
➜  ~ node -v
v0.12.0
➜  ~ npm -v
2.14.3
{% endhighlight %}

<br/>

###  创建一个空的hello的目录

![screenshot](http://img4.tbcdn.cn/L1/461/1/47e3c5a3e178e8a3f929e84052b6cdeb6d41b20e.png)

<br/>

###  创建hello.js文件

{% highlight ruby %}
touch hello.js       //创建hello.js
{% endhighlight %}

写入以下内容

{% highlight ruby %}
exports.Hello = function ( name ) {
    console.log( "Hello " + name );
}
{% endhighlight %}

<br/>

###  NPM初始化

执行npm init


![screenshot](http://img3.tbcdn.cn/L1/461/1/714307e869e87bd9410b79d3babb3f231a3094b5.png)

按要求填写一些信息

![screenshot](http://img1.tbcdn.cn/L1/461/1/d55a682b122b80c186cfe21e433b245dcda8da46.png)

这样就生成了package.json文件

![screenshot](http://img2.tbcdn.cn/L1/461/1/adc279f10ec00866e643d7e3d09cf2cb69e0e350.png)

返回hello的上级目录  安装这个模块

![screenshot](http://img4.tbcdn.cn/L1/461/1/5ae782646235c63be1b51e0ada0b6fdcb49d6520.png)

显示安装成功

用node执行下，成功输出数据

![screenshot](http://img1.tbcdn.cn/L1/461/1/0dbd486f0c7d86ac5fffd567a29d029bf2dd7748.png)

这样一个简单的模块就开发完成了，只需要把它发布到NPM上即可。

<br/>

###  NPM包发布

发布之前需要在官网上注册一个帐号：

{% highlight ruby %}
➜  npm-package npm adduser  
Username: joannazhu
Password: 
Email: (this IS public) XXXXXX@126.com
{% endhighlight %}
 
注册完成之后，只要发布就行了

{% highlight ruby %}
npm publish
{% endhighlight %}


结果提示：
![screenshot](http://img2.tbcdn.cn/L1/461/1/7f86a900d53334788b860bc9c9e23cce8dc6c063.png)

这是因为这个模块已经被别人上传了，hello这个名字太常见了，囧，改个特立独行的名字就好啦！

登录[自己的NPM主页](https://www.npmjs.com/~joannazhu)，或者输入模块名搜索，就可以看到自己发布的那个模块了

![screenshot](http://img2.tbcdn.cn/L1/461/1/c24b730ee444dba30bc910613f5df7b0276adab8.png)




