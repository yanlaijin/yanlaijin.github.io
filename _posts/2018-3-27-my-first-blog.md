---
layout: post
title: Linux下安装zookeeper
categories: Linux
description: Linux下安装zookeeper
keywords: Linux
---

准备工作
--
在安装zookeeper之前，首先需要安装JDK环境，具体操作请看..
安装
--
首先进入合适的安装目录：
```
cd /usr/local/
```
下载zookeeper安装包：
```
wget -c https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.4.11/zookeeper-3.4.11.tar.gz
```
解压缩：
```
tar -xzvf zookeeper-3.4.11.tar.gz
```
进入解压后的目录，分别创建data和logs文件夹:
```
cd zookeeper-3.4.11
mkdir data
mkdir logs
```
进入conf目录，编辑zoo.cfg文件：
```
cd conf/
cp zoo_sample.cfg zoo.cfg
vim zoo.cfg
```
加入下面代码：
```
dataDir=/usr/local/zookeeper-3.4.11/data
dataLogDir=/usr/local/zookeeper-3.4.11/logs
```
搞定，进入bin目录，启动zookeeper：
```
./zkServer.sh start
```
显示如下：
![image](https://github.com/yanlaijin/yanlaijin.github.io/blob/master/images/posts/zookeeper-start.png)
查看 zkServer.sh status 状态后显示如下：
![image](https://github.com/yanlaijin/yanlaijin.github.io/blob/master/images/posts/zookeeper-status.png)
查看zookeeper.out文件显示如下：
```
nohup: failed to run command `java': No such file or directory
```
网上查了众多资料，发现是.zkServer.sh文件读取不到jdk安装目录。
解决方法：
在.zkServer.sh文件开头添加如下代码：
```
export JAVA_HOME=/usr/lib/jdk  
export PATH=$JAVA_HOME/bin:$PATH
```
重启zookeeper,问题完美解决。
