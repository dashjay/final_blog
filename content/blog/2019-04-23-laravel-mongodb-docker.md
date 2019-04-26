---
title: Laravel使用MongoDB纯Docker化部署
author: Dashjay
date: '2019-04-23'
slug: laravel-mongodb-docker
categories:
  - 运维
  - Docker
tags:
  - tutorial
description: ''
featured: 屏幕快照 2019-04-23 上午7.20.54.png
featuredalt: ''
featuredpath: /blog/2019-04-23-laravel-mongodb-docker_files
linktitle: ''
type: post
---

使用场景：学校，OJ，使用的本不会太懂，尽量傻瓜式部署。

> ### 在PHP下使用Laravel必须安装MongoDB插件，然后MongoDB-Server必须运行，这次为了方便软件使用，我使用了纯Docker部署，也是为了方便拓展。

首先拉到一个非常好的Docker，已经配置的非常好了~可以直接使用那种！-->`webdevops/php-nginx`

```
$docker pull  webdevops/php-nginx

$docker run -d -p 32778:80 -p 32777:443 -p 32776:9000 webdevops/php-nginx supervisord

``` 

不出意外此时你访问localhost:32778的时候可以看到nginx404了，那是因为网页没有index
<img src="/./2019-04-23-laravel-mongodb-docker_files/屏幕快照 2019-04-23 下午1.15.09.png" alt="" width="60%"/>

这时候你运行docker ps -a 检查一下刚才运行的docker的名字

```
$docker ps -a 
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS              PORTS                                                                    NAMES
a969d60ac6ea        webdevops/php-nginx   "/entrypoint supervi…"   8 minutes ago       Up 8 minutes        0.0.0.0:32778->80/tcp, 0.0.0.0:32777->443/tcp, 0.0.0.0:32776->9000/tcp   fervent_hofstadter

```
其中docker的id是这个`a969d60ac6ea`

然后使用docker exec来执行命令进入docker

```
docker exec -it a969d60ac6ea bash
```

我们既不会影响原来的程序supervisord的运行，还能进入现有docker

```
$ls
1  bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

```
查看一下有哪些目录，整个目录是映射在app里的，所以我们进入app

```
$cd app
$vim index.php
```

```
## $cat  index.php
<?php
phpinfo()
?>
```
文件里面就写那么多！

<img src="/./2019-04-23-laravel-mongodb-docker_files/屏幕快照 2019-04-23 下午4.31.16.png" alt="" width="60%"/>

直接访问开始设置的端口就可以访问到内容！

这个webdevops/php-nginx是不是太好用了，配置文件在深处自己找，可以改目录或者你自己把你的目录映射进去即可。
