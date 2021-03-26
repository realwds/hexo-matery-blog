---
title: github 国内加速访问（改变 hosts 方式）
author: reralwds
img: /medias/featureimages/3.jpg
top: true
toc: false
categories: github
tags:
  - github
abbrlink: 9bcea011
date: 2021-03-25 00:00:00
---

一、访问链接 https://www.ipaddress.com/ip-lookup

二、分别查询以下 5 个链接 对应的 IP 地址，查询一个之后，在下面的 “Perform another IP Lookup” 框里可以继续查询。

```bash
github.com
gist.github.com
github.global.ssl.fastly.net
assets-cdn.github.com
raw.githubusercontent.com
```

assets-cdn.github.com 查询得到如下四个链接，请使用 cmd 分别 ping 四个链接，查看访问速度最快的。

```bash
ping 185.199.108.153
ping 185.199.109.153
ping 185.199.110.153
ping 185.199.111.153
```

三、修改 hosts 文件，添加内容（因为每个人网络环境不同，请自行采用本地查询结果，不要直接复制 ！！！）

```bash
140.82.114.4 github.com
140.82.114.3 gist.github.com
199.232.69.194 github.global.ssl.fastly.net
185.199.109.153 assets-cdn.github.com
199.232.96.133 raw.githubusercontent.com
199.232.96.133 gist.githubusercontent.com
199.232.96.133 cloud.githubusercontent.com
199.232.96.133 camo.githubusercontent.com
199.232.96.133 avatars0.githubusercontent.com
199.232.96.133 avatars1.githubusercontent.com
199.232.96.133 avatars2.githubusercontent.com
199.232.96.133 avatars3.githubusercontent.com
199.232.96.133 avatars4.githubusercontent.com
199.232.96.133 avatars5.githubusercontent.com
199.232.96.133 avatars6.githubusercontent.com
199.232.96.133 avatars7.githubusercontent.com
199.232.96.133 avatars8.githubusercontent.com
```

windows 系统的 hosts 文件的位置如下：

```bash
C:\Windows\System32\drivers\etc\host
```

mac/linux 系统的 hosts 文件的位置如下：
```bash
/etc/hosts
```

四、cmd 运行以下代码刷新 DNS 。

```bash
ipconfig /flushdns
```

五、打开 Github 进行测试，成功！

重新访问 github ，搞定！！！