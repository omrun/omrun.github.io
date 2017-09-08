---
layout: post
title: 启用debian root账户
date: 2017-09-07 21:59:46 +0759
category: Linux
tags: [linux]
---

debian里root账户默认没有密码，但账户锁定

##### 1. 修改root账户的密码 
```
sudo passwd root
```
输入要设为的密码两次	
##### 2. 启用root账户
``` 
sudo passwd --unlock root
```
输入上面命令如果报错，是由于新版本ssh默认关闭root登陆，可以修改一下ssh的配置文件
> /etc/ssh/sshd_config

搜索`PermitRootLogin without-password`
改为`PermitRootLogin yes`
保存

