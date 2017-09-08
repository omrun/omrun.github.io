---
layout: post
title: linux crontab命令
date: 2017-09-07 23:04:18 +0759
category: Linux
tags: [linux]
---


```
#分 时 日　 月　 周　用户   命令            (*/1 每1个单位)
# m h dom mon dow user	command
17 *	* * *	root    cd / && run-parts --report /etc/cron.hourly
25 6	* * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6	* * 7	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6	1 * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )
```

我以为编辑crontab保存后会自动执行，其实不然，必须通过重启cron才可以，命令如下：

启动

```language
/etc/init.d/cron start
```

关闭

```language
/etc/init.d/cron stop
```

重启

```
/etc/init.d/cron restart
```

