---
layout: post
title: Flink环境搭载流程及一些问题
subtitle: Flink萌新
image: /img/hello_world.jpeg
---

​	萌新第一次接触Flink架构，尝试搭载并总结一些搭载中遇到的问题。

​	首先，我是一台Win10电脑，用VMware装了一个Ubuntu的虚拟机。由于这个大数据架构比较大，我给虚拟机分配了3G RAM和 20G ROM。然后，在github上找到了阿里巴巴工程师们提供的flink中文社区的官方教程。

<a href="https://github.com/flink-china/flink-training-course">教程</a>



​	接着，我在上面找到了一份完整详细的Flink配置教程，并参照其中进行配置。

<a href="https://files.alicdn.com/tpsservice/4824447b829149c86bedd19424d05915.pdf">配置</a>

​	环境配置需要jdk(1.8)+Maven(3.2.5)+Git。之后就可以下载Flink的代码了。



​	下载好就可以使用Maven编译Flink代码了。

​	编译代码的过程遇到许多ERROR（卡了2天多），最后发现是我没有声明版本，Flink默认编译最新的1.9版本，导致很多新增的插件如frontend-maven-plugin无法安装。

<center>
    <div class="photoset-grid-custom" data-layout="213">
        <img src="/img/20191015154331.png">
    </div>
</center>

​	最后进入Flink文件夹下的.github文件夹里打开终端，输入

 git checkout release-1.7 

声明为1.7版本，再编译错误少了很多，最后一一解决。

