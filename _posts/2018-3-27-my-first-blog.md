---
layout: post
title: Linux�°�װzookeeper
categories: Linux
description: Linux�°�װzookeeper
keywords: Linux
---
#Linux�°�װzookeeper
##׼������
�ڰ�װzookeeper֮ǰ��������Ҫ��װJDK��������������뿴..
##��װ
���Ƚ�����ʵİ�װĿ¼��
`cd /usr/local/`
����zookeeper��װ����
`wget -c https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.4.11/zookeeper-3.4.11.tar.gz`
��ѹ����
`tar -xzvf zookeeper-3.4.11.tar.gz`
�����ѹ���Ŀ¼���ֱ𴴽�data��logs�ļ���:
```
cd zookeeper-3.4.11
mkdir data
mkdir logs
```
����confĿ¼���༭zoo.cfg�ļ���
```
cd conf/
cp zoo_sample.cfg zoo.cfg
vim zoo.cfg
```
����������룺
```
dataDir=/usr/local/zookeeper-3.4.11/data
dataLogDir=/usr/local/zookeeper-3.4.11/logs
```
�㶨������binĿ¼������zookeeper��
`./zkServer.sh start`
��ʾ���£�
�鿴 zkServer.sh status ״̬����ʾ���£�
�鿴zookeeper.out�ļ���ʾ���£�
`nohup: failed to run command `java': No such file or directory`
���ϲ����ڶ����ϣ�������.zkServer.sh�ļ���ȡ����jdk��װĿ¼��
���������
��.zkServer.sh�ļ���ͷ������´��룺
```
export JAVA_HOME=/usr/lib/jdk  
export PATH=$JAVA_HOME/bin:$PATH
```
����zookeeper,�������������

