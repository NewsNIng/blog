---
title: 在 Centos 中安装 java8
date: 2019-08-01 18:56:29
tags:
  - Centos
  - Java
categories: Linux
---

## 前言

由于要在服务器上安装 [Jenkins](https://jenkins.io/zh/) 所以首先要安装 java。

## 更新

安装之前最好更新下

```bash
yum -y update
```

## 安装 Java8

```bash
yum install java-1.8.0-openjdk
```

## 查看版本

```bash
java -version
```

## 设置环境变量 JAVA_HOME

首先找到安装 java 的位置

```bash
update-alternatives --config java
```

编辑 .bash_profile 文件

```bash
vim .bash_profile
```

添加这一行

```bash
export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.191.b12-1.el7_6.x86_64/jre/bin/java
```

重新执行刚修改的 .bash_profile

```bash
source .bash_profile
```

## 验证一下

```bash
echo $JAVA_HOME
```