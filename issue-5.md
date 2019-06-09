## 摘文

### 是否值得花时间提高软件质量？

软件质量划分为外部 （例如UI和功能缺陷）和内部（代码架构）。

假设，丽贝卡和我写一个跟踪和预测航班延误的应用程序。我们的应用程序都具有相同的基本功能，同样美观友好的用户界面，几乎没有任何缺陷。唯一的区别是她的内部源代码整齐有序，而我的代码却是混乱不堪。还有一个区别：我以6美元的价格出售我的产品，她的价格是10美元。

用户无法看到软件的内部结构，也无法判断它的好坏。为什么要为看不见摸不着的东西付出更多金钱？

为什么软件开发人员应该花时间和精力来提高软件的内部质量？程序员大部分时间都在修改代码。即使新功能，编程也是围绕现有代码完成的。当我想为添加新功能时，第一个任务是弄清楚这个功能的流程，然后需要考虑添加新功能会不会对现有功能产生影响。

衡量一个内部质量好坏一个重要特点是更容易弄清楚程序的工作原理，这样就可以清楚添加新功能。如果合理的划分软件模块，就不必阅读所有代码，只需要快速阅读几个模块。将精力放在明确的命名上，我可以快速了解代码的各个部分，而不必赘述细节。混乱的代码会增加时间成本去理解内部结构，也会增加犯错误的可能性。如果出现错误，必须花时间去了解是什么导致故障是以及如何去解决它。如果没有在开发过程中发现，等到错误暴露给客户，就需要花更多的时间来修复。

快速的添加新功能不考虑代码质量，违背了程序模块化结构，可能增加缺陷。如果采取快速开发，今天可能很快完成任务，但是在未来几周和几个月里，处理相关代码时会降低效率。如果团队其他成员也做出相同的决定。那么，一个易于修改的功能原本只需要几个小时，现在可能需要花费数周时间完成。

许多人认为只有开发团队粗心大意时才会犯错误，其实即使是最优秀的团队也会产生一些缺陷。

许多人，包括软件行业的一些人，将构建软件比作建造大教堂或摩天大楼 - 这就是为什么我们称高级程序员为“架构师”？但构建软件不同于真实世界。软件的客户只是粗略地了解他们想要在产品中需要哪些功能，等到构建软件时才了解需要具体需要哪些功能 - 特别是一旦早期版本发布给用户。

软件开发行业的高速发展，总是创造出新颖的软件技术。用于构建软件的开发语言，库和平台每隔几年甚至每个月就会发生重大变化。常常听到某个团队花了一年甚至几年时间的构建项目。到后来发现技术更不上需求的变化，导致开发进度缓慢，开发团队不得不重新重构整个项目。

好的团队产生少量的低质量的代码，但是他们会持续不断重构代码已满足不断新的需求。差的技术团队不关心代码质量，对低质量代码视而不见，盲目无章堆新功能，导致整个项目一步一步陷入泥潭，甚至毁灭整个项目。一个常见的比喻就是清理厨房。你做饭时弄脏，但是如果你不快速清理，时间久脏东西就很难去除，所有肮脏的东西妨碍了烹饪下一道菜。

总结

- 忽视内部质量会快速完成任务同时也可能导致更多缺陷
- 缺陷越多会降低功能开发进度
- 再伟大的团队也会产生少量的低质量的代码，但是通过保持内部质量，可以控制
- 尽量减少低质量的代码，团队才能够减少工作量，同时有更多时间和成本去添加新功能

链接：[是否值得花时间提高软件质量？](https://martinfowler.com/articles/is-quality-worth-cost.html "是否值得花时间提高软件质量？")

## 新闻

### SwiftUI

SwiftUI一全新简洁的UI构建工具适用于Apple所有平台

链接：[SwiftUI](https://developer.apple.com/xcode/swiftui/ "SwiftUI")

### Koin发布2.0版本

KOIN实用轻量级依赖注入框架

链接：[Koin发布2.0版本](https://medium.com/koin-developers/ready-for-koin-2-0-2722ab59cac3 "Koin发布2.0版本")

### W3C和WHATWG携手合作，共同推进开放的WEB平台

W3C和WHATWG刚签署了一项协议，合作开发单一版本的HTML和DOM规范。认为两个不同的HTML和DOM规范对社区有害。

链接：[W3C和WHATWG携手合作，共同推进开放的WEB平台](https://www.w3.org/blog/2019/05/w3c-and-whatwg-to-work-together-to-advance-the-open-web-platform/ "W3C和WHATWG携手合作，共同推进开放的WEB平台")

### Firefox使用AV1解码器

AV1可以在不降低网络使用率的情况下提供高质量的视频体验，提高我们在互联网上观看视频体验

链接：[Firefox使用AV1解码器](https://hacks.mozilla.org/2019/05/firefox-brings-you-smooth-video-playback-with-the-worlds-fastest-av1-decoder/ "Firefox使用AV1解码器")

## 文章

### 被遗忘的Web浏览器

一段有趣的互联网历史。很多人认为Netscape是世界上第一个Web浏览器，20世纪90年代早期在它前面已经有很多浏览器。

链接：[被遗忘的Web浏览器](https://arstechnica.com/information-technology/2019/05/before-netscape-forgotten-web-browsers-of-the-early-1990s/ "被遗忘的Web浏览器")

### 2019互联网健康报告

Mozilla2019年研究五个问题对互联网健康的报告，包括：安全吗？有多开放？谁受欢迎？谁能成功？谁控制它？它还关注人工智能，城市的力量以及我们如何重新思考数字广告

链接：[2019互联网健康报告](https://internethealthreport.org/2019/ "2019互联网健康报告")

### 夜间模式

ios和android两大系统都先后宣布支持夜间模式。夜间模式不是越黑越好，总之这是一篇很好教你如何让你的app更好的适配夜间模式的教程。

链接：[夜间模式](https://medium.com/by-digiti/the-future-is-dark-8c3bdadf9fdc?sk=22e43184d9f5b095c0971d9f6add473f "夜间模式")

### 电子邮件开发和设计

电子邮件开发和设计并不容易，因为电子邮件客户端供应商并不像Web浏览器供应商实施新标准那样进步。随着更多移动设备和电子邮件客户端的推出，在构建HTML电子邮件时需要处理更多限制。本文提供了构建和发送电子邮件的一些见解。

链接：[电子邮件开发和设计](https://medium.com/@andrewlaurentiu/html-emails-4de656a6b7ef "电子邮件开发和设计")

### 10可用性启发式应用于视频游戏

我觉得这篇文章启发也适用于其他平台开发。比如：系统应始终在合理的时间内通过适当的反馈向用户通知正在发生的事情。系统应该使用用户熟悉的单词，短语和概念来说明用户的语言，而不是面向系统的术语。

链接：[10可用性启发式应用于视频游戏](https://www.nngroup.com/articles/usability-heuristics-applied-video-games/ "电子邮件开发和设计")

## 教程

### Kotlin教程

为Python开发者准备的Kotlin教程，如果你是Java开发者建议阅读官方文档

链接：[Kotlin教程](https://khan.github.io/kotlin-for-python-developers/ "Kotlin教程")

## 前端

### JavaScript整洁代码 - 最佳实践

“Uncle Bob”启发的技巧可能会帮助你思考如何命名和构建代码

链接：[JavaScript整洁代码 - 最佳实践](http://pop.frontendweekly.co/PsVdT9?utm_campaign=Frontend%2BWeekly&utm_medium=email&utm_source=Frontend_Weekly_154 "JavaScript整洁代码 - 最佳实践")

### React hooks

关于React Hooks基础知识的简短教程

链接：[React hooks](https://github.com/httpJunkie/telerik-blogs/blob/master/kendoreact-tip-of-the-day-frontend-focus.md "React hooks")

这里还有一段F8大会关于Hooks视频介绍

链接：[React hooks](https://developers.facebook.com/videos/2019/intro-to-react-hooks/?pix=yb_0_0 "React hooks")

### 网页排版

移动网页设计中排版参考指南

链接：[网页排版](https://www.smashingmagazine.com/2018/06/reference-guide-typography-mobile-web-design/ "网页排版")

### 使用Svelte 3.0进行真正的响应式编程

Svelte不是库，也不是一个框架，它是一个编译器。

链接：[使用Svelte 3.0进行真正的响应式编程](https://blog.logrocket.com/truly-reactive-programming-with-svelte-3-0-321b49b75969/?pix=z3_0_0 "使用Svelte 3.0进行真正的响应式编程")

### 使用CSS构建太阳系

使用css样式构建逼真的太阳系

链接：[使用CSS构建太阳系](https://codepen.io/robdimarzo/post/rebuilding-the-solar-system-with-css?ref=devawesome.io "使用CSS构建太阳系")

## 工具

### IP地理位置API

免费实时的IP地理位置API。通过IPv4或IPv6地址获取所在国家/地区的详细信息，包括位置，货币，电话号码等信息

链接：[IP地理位置API](https://ipgeolocationapi.com/ "IP地理位置API")

### material-ui

Rect　material-ui库

链接：[material-ui](https://github.com/mui-org/material-ui?ref=devawesome.io "material-ui")

### Coder

Coder是一个基于于Visual Studio Code的开源远程开发环境

链接：[Coder](https://coder.com/ "Coder")

### Vim.Wasm

Vim编辑器移植到WebAssembly

链接：[Vim.Wasm](https://rhysd.github.io/vim.wasm/ "Vim.Wasm")

### FireQL

一个用于测试/调试GraphQL工具

链接：[FireQL](https://fireql.dev/?url=https%3A%2F%2Fapi.spacex.land%2Fgraphql&ref=producthunt "FireQL")

### SQLGate

一个用于数据库的智能IDE

链接：[SQLGate](https://www.sqlgate.com/ "SQLGate")

### QuickChart

单个URL生成图表

链接：[QuickChart](https://quickchart.io/ "QuickChart")

### Ikonate

完全可定制和可访问的矢量图标

链接：[Ikonate](https://www.ikonate.com/ "Ikonate")

### ElGrapho

<img src="https://raw.githubusercontent.com/ericdrowell/ElGrapho/master/img/elgrapho-examples.png"/>

El Grapho是一个高性能的WebGL图形数据可视化引擎。可以在任何浏览器中支持数百万个交互式节点

链接：[ElGrapho](https://github.com/ericdrowell/ElGrapho "ElGrapho")

### fabulous

<img src="https://camo.githubusercontent.com/12e05ae80ab82bd927d5c2b131f0bf7284925591/68747470733a2f2f616666656374696f6e6174652d626f6f74682d3130613166342e6e65746c6966792e636f6d2f62616e6e65722e706e67"/>

在Visual Studio Code中引入了CSS属性侧边栏。

链接：[fabulous](https://github.com/Raathigesh/fabulous?utm_source=CSS-Weekly&utm_campaign=Issue-365&utm_medium=email "fabulous")

### Overflow

<img src="https://cdn-images-1.medium.com/max/2400/1*DM-fjMAImOp9JabrTxYklw.gif"/>

专为计师量身定制的用户流程图工具

链接：[Overflow](https://blog.overflow.io/welcome-overflow-1-0-b4a23bcbb2f9 "Overflow")

### Fontanello

适用于Google Chrome和Firefox的浏览器插件，可通过右键单击来显示文本的基本布局样式。

链接：[Fontanello](https://fontanello.oktavilla.se/ "Fontanello")