---
layout: post
title: linux wget命令
date: 2017-09-07 22:16:22 +0759
category: Linux
tags: [linux]
---



* 不检查https证书

```
--no-check-certificate
```

* 使用wget -O下载并以不同的文件名保存 

wget默认会以最后一个符合”/”的后面的字符来命令，对于动态链接的下载通常文件名会不正确。 
错误：下面的例子会下载一个文件并以名称download.php?id=1080保存 

```
wget http://www.centos.bz/download?id=1
```

即使下载的文件是zip格式，它仍然以download.php?id=1080命令。 
正确：为了解决这个问题，我们可以使用参数-O来指定一个文件名： 

```
wget -O wordpress.zip http://www.centos.bz/download.php?id=1080 
```


* 使用wget –tries增加重试次数
如果网络有问题或下载一个大文件也有可能失败。wget默认重试20次连接下载文件。如果需要，你可以使用–tries增加重试次数。 

```
wget –tries=10 [URL]
```



* 使用wget -i下载多个文件 

首先，保存一份下载链接文件 

```
cat > filelist.txt 
url1 
url2 
url3 
url4 
```

接着使用这个文件和参数-i下载 

```
wget -i filelist.txt
```



* 使用wget FTP下载 

你可以使用wget来完成ftp链接的下载。 
使用wget匿名ftp下载 

```
wget ftp-[url]
```

使用wget用户名和密码认证的ftp下载 

```
wget –ftp-user=[USERNAME] –ftp-password=[PASSWORD] [url]
```

