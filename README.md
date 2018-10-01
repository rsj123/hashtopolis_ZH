# Hashtopolis

<img src="https://github.com/s3inlc/hashtopolis/blob/master/src/static/logo.png" alt='Hashtopolis' width="100">

[![CodeFactor](https://www.codefactor.io/repository/github/s3inlc/hashtopolis/badge)](https://www.codefactor.io/repository/github/s3inlc/hashtopolis)
[![LoC](https://tokei.rs/b1/github/s3inlc/Hashtopolis?category=code)](https://github.com/s3inlc/Hashtopolis)
[![Test Status](https://travis-ci.org/s3inlc/hashtopolis.svg?branch=master)](https://travis-ci.org/s3inlc/hashtopolis)

Hashtopolis是一个多平台客户端和服务器工具，用于把hashcat的任务分发到多台计算机。 Hashtopolis我们的目标是可移植性，健壮性，多用户支持和多个组管理。
该程序有两个部分：

- **代理端** 多个客户端（C＃，Python），可轻松定制以满足任何需求。
- **服务端** 基于PHP，CSS文件：拥有图形化后台和代理链接管理

为了在有限的网络上实现高可用性，Hashtopolis通过HTTP（S）使用JSON传输hash。

服务器部分基于PHP并使用MySQL作为数据库。 将您的MySQL服务器通过配置提高性能至关重要。 数据库操作可能非常重要，正确的配置使得等待几毫秒和灾难性的延时之间存在差异。 数据库若使用索引将快很多。 因此，如果您看到有关对哈希表进行预排序的提示，请执行此操作。
Web管理界面是所有客户端代理的单一访问点。 新代理部署需要在“新代理”选项卡中生成一次性密码（token）。 这样可以降低将恶意用户或文件泄露给恶意用户或虚假代理的风险。
文档和维基的某些部分不是最新的。 如果您发现任何错误或对理解描述有疑问，请随时通过Twitter（@ s3inlc，@ winxp5421）与我们联系或加入我们的Discord服务器(https://discord.gg/S2NTxbz)

要报告错误，请创建一个问题并尝试尽可能准确地描述问题。 这有助于我们识别错误并重现。

为了使Hashtopussy项目的名称符合更具政治中立性，它于2018年3月更名为“Hashtopolis”。

## 特性

- 使用简单方便
- 可以在任何设备上通过web访问
- 有较高的兼容性
- 无人值守的代理
- 字典和规则的管理
- Hashtopolis 和 Hashcat的自动更新
- 破解相同hash类型的多个hash列表，就像它们是单个hash列表一样
- 在Windows，Linux和OS X上运行相同的客户端
- 标记为“机密”的文件和hash仅分发给标记为“受信任”的代理
- 许多的数据导入和导出选项
- 关于任务运行和hash列表有丰富的统计信息
- 可视化的块分布
- 支持多用户
- 用户权限管理
- 多类型通知
- 小型任务和仅CPU任务
- 用于细粒度访问控制的代理和用户的组分配
- 兼容支持特定标志的破解软件

## 设置和使用

请访问[wiki](https://github.com/rsj123/hashtopolis_ZH/wiki) 获取更多有关设置和升级的信息.

Hashtopolis的一些截图（由winxp5421和s3in！c提供）: [Imgur1](http://imgur.com/gallery/Fj0s0) [Imgur2](http://imgur.com/gallery/LzTsI)

## 贡献指南

我们欢迎各种贡献。如果是错误修复或新功能，请随意创建pull请求。并考虑以下几点：

* 只需在一个pull请求中包含一个功能或一个错误修复。 如果您有两个新功能，请同时创建两个pull请求。
* 尝试坚持使用统一代码样式（特别是在PHP部分）。 IntelliJ / PHPStorm用户可以获得代码样式的XML[here](https://gist.github.com/s3inlc/226ed78b05eb6dc8f60f18d6fd310d74).

拉取请求将由一个以上的成员进行审核，并在审核通过后合并。 不要因为第一次未通过而气馁，通常这些只是无关紧要的。

## 支持我们

[PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7P3KXV8DQ5XKE)

```
BTC: 15gi3X5L4VPa5S2yygztYaN7MF7VA26Zaf
ETH: 0x06B3Ae7561AD763eF58Df9C37deB6757bDA2BC0c
```

## 鸣谢

* winxp5421的测试，编写帮助文本并提出大量建议
* blazer处理csharp代理和处理python代理
* Cynosure Prime 的测试
* atom 的 [hashcat](https://github.com/hashcat/hashcat)
* curlyboi 的原版代码 [Hashtopus](https://github.com/curlyboi/hashtopus)
* 7zip [here](https://sourceforge.net/projects/sevenzip/files/7-Zip/16.04/)
* uftp [here](http://uftp-multicast.sourceforge.net/)
