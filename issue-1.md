## 新闻摘要

### 微软发布一款全新终端

Windows Terminal是一个全新的终端应用程序，适用于命令行工具和命令提示符，PowerShell和WSL等命令行的用户。支持多标签，更好的文字渲染。

该软件开源在github上，发布将近一天时间已有2万多用户star

原文链接：[Windows终端介绍](https://devblogs.microsoft.com/commandline/introducing-windows-terminal/ "Windows终端介绍")

链接：[github](https://github.com/Microsoft/Terminal "Windows终端github")

### 谷歌推出Jetpack Compose

Google I/O 2019开发者大会上，Google宣布推出[Jetpack Compose](https://developer.android.com/jetpack/compose?authuser=1 "Jetpack Compose官方文档")的第一个预览版，这是一个新的开源UI工具包，适用于想要使用类似于React Native和Vue.js的反应式编程模型的Kotlin开发人员。

Jetpack Compose是一个非捆绑式工具包，是Google为Android开发人员提供的整体Android Jetpack软件组件的一部分，不要求使用任何其他Jetpack组件。

开发人员可以混合搭配Jetpack Compose API，并根据Android的原生API查看这些API。开箱即用，Jetpack Compose本身也支持Google的Material Design。

原文链接：[Jetpack Compose](https://techcrunch.com/2019/05/07/google-launches-jetpack-compose-an-open-source-kotlin-based-ui-development-toolkit/ "Jetpack Compose")

### Kotlin成为Android开发首选语言

谷歌宣布，Kotlin编程语言现在是Android应用程序开发人员的首选语言。

谷歌同时宣布，今后将以Kotlin为先，许多新的Jetpack API和功能将首先在Kotlin中提供。 建议开发者应该首选kotlin；因为Kotlin编写的代码更简短，易于测试和可维护。

原文链接：[Kotlin成为Android开发首选语言](https://techcrunch.com/2019/05/07/kotlin-is-now-googles-preferred-language-for-android-app-development/ "Kotlin成为Android开发首选语言")

## 好文推荐

### 继承与组合

> 面向对象语言的问题在于，它们依赖于特定的环境。你想要个香蕉，但拿到的却是拿着香蕉的猩猩，乃至最后你拥有了整片丛林。 -- Joe Armstrong

《设计模式：可重用面向对象软件的元素》一书也建议使用组合而不是继承；

继承优点代码重用，缺点耦合度高，不易于维护；组合灵活、解藕。在两者都可行的情况下，优先使用组合而不是继承。当然，并不是说两者选其一。如果是“包含”`has a`建议用组合；如果是“属于”`is a`建议使用继承。

原文链接：[继承与组合](https://lwn.net/SubscriberLink/787800/b7f5351b3a41421a/ "继承与组合")

链接：[HackNews讨论](https://news.ycombinator.com/item?id=19863871 "HackNews讨论")

扩展阅读：

链接：[优先使用组合而不是继承？](https://lovoedu.gitee.io/javablog/2017/06/01/20170601/ "为什么老鸟要告诉你优先使用组合而不是继承？")

链接：[组合以及与继承的区别](https://www.cnblogs.com/Qian123/p/5176405.html "组合以及与继承的区别")

链接：[深入理解Java中的组合和继承](https://www.hollischuang.com/archives/1319 "深入理解Java中的组合和继承")

## 观点

### 1. 我们可以做得比SQL更好

SQL发展之初是针对没有计算机编程培训的用户设计的，SQL语言的主要用途是用于临时查询。

虽然早期的许多缺点都在标准的后续版本中得到修复，但一些严重的问题根深蒂固。总结起来有四大缺点：缺乏正确的正交性（SQL很难编写）、缺乏紧凑性、缺乏一致性、系统内聚性差。不同关系型数据库语法有差异。

关系模型仍然是表示数据的最普遍适用和有效的方法。SQL作为声明的，存储中立的查询语言的概念功能强大且功能多样。EdgeQL是一种“更好的SQL”：一种查询语言，为用户提供更多的功能，但这也更简单，更一致。

原文链接：[我们可以做得比SQL更好](https://edgedb.com/blog/we-can-do-better-than-sql/ "我们可以做得比SQL更好")

### 2. 是时候用AV1视频替换GIF了！

GIF占用了大量的空间（通常是数兆字节！）。如果您的目标是提高网站的加载性能，那么GIF需要被淘汰！但那你怎么展示动人的照片呢？答案是视频。在大多数情况下，将获得更好的质量以及近节省50-90％的尺寸大小！

技术向前发展，我们需要随之而动。到目前为止，已经有两种编解码器可供所有浏览器和平台广泛采用，用于编码视频：

1. H.264 - 于2003年推出，是当今使用最广泛的编解码器
2. VP9 - 在2013年推出，与H.264大多数时间相比，压缩率提高了50％，根据reddit上的讨论，有时它会很糟糕。

我们的目标是将庞大的GIF缩小到尽可能缩小尺寸大小，以改善网页加载时间。我们讨论的AV1与VP9相比，可以实现约30％的压缩。所以，比H.264好大约80％。

原文链接：[是时候用AV1视频替换GIF了](https://www.singhkays.com/blog/its-time-replace-gifs-with-av1-video/media/scene1/x264_200k.mp4 "是时候用AV1视频替换GIF了")