## 新闻

### [purescript npm存在恶意代码](https://harry.garrood.me/blog/malicious-code-in-purescript-npm-installer/ "purescript npm存在恶意代码")

恶意代码首先插入到load-from-cwd-or-npm版本3.0.2 的npm包中，然后插入到rate-map从版本1.0.3开始的npm包中。简而言之，恶意代码破坏了purescript npm安装程序，以防止下载完成，使安装程序在“检查是否为您的平台提供预构建的二进制文件”步骤中挂起。

- 恶意代码被添加到purescript npm安装程序的各种依赖项中
- @shinnn声称恶意代码是由获得访问他的npm帐户的攻击者发布的
- 恶意代码的唯一目的是破坏purescript npm安装程序以防止它成功运行
- 在最新版本的purescript npm安装程序中，恶意代码现已被删除，所有依赖项都被删除了
- 如果你想确保没有恶意代码，应该删除node_modules的目录和你的 package-lock.json文件，并设置0.13.2以上purescript包

## 教程

### [JetBrains发布了一个新的实践教程来学习协程](https://play.kotlinlang.org/hands-on/Introduction%20to%20Coroutines%20and%20Channels/01_Introduction "JetBrains发布了一个新的实践教程来学习协程")

在这个实践教程中，熟悉协程的概念。协程可以更好的处理异步和非阻塞，并提高代码可读性。以及如何使用协程来执行网络请求，不使用回调并且也不会阻塞线程。

将学到

- 如何使用挂起函数来执行网络请求。
- 如何使用协程同时发送请求。
- 如何使用管道在不同的协程之间共享信息。

### [Kotlin初学者教程](https://www.youtube.com/watch?v=F9UC9DY-vIU&feature=youtu.be "Kotlin初学者教程")

freeCodeCamp.org在YouTube发布长达两个半小时的Kotlin初学者教程

### [MVVM与Kotlin  -  Android架构组件，Dagger 2，Retrofit和RxAndroid](https://proandroiddev.com/mvvm-with-kotlin-android-architecture-components-dagger-2-retrofit-and-rxandroid-1a4ebb38c699 "MVVM与Kotlin  -  Android架构组件，Dagger 2，Retrofit和RxAndroid")

<img src="https://miro.medium.com/max/2500/1*SPuMvcXi1awXJBMtzvEzog.jpeg">

这篇文章展示如何MVVM架构组合使用Kotlin、架构组件、Retrofit以及RxAndroid

### [Kotlin领域特定语言：入门](https://www.raywenderlich.com/2780058-domain-specific-languages-in-kotlin-getting-started "Kotlin领域特定语言：入门")

在这个Kotlin教程中，学习如何使用接收器，构建器模式和扩展函数以及lambdas创建DSL！

### [GeckoView入门](https://www.raywenderlich.com/1381698-android-tutorial-for-geckoview-getting-started "GeckoView入门")

<img src="https://koenig-media.raywenderlich.com/uploads/2019/02/awesomebrowser.gif"/>

GeckoView是一个Android Web引擎库，它是由社区和Mozilla的开发人员创建。

GeckoView和WebView不一样。GeckoView有自己的API，并不是替代品。以下是它们之间的一些主要差异：

- GeckoView不是基于WebView，它是一个完整的Web引擎，如果引用GeckoView安装包将增长高达30MB到40MB。
- 不同的设备可能WebView API版本不相同。导致碎片化增加开发难度。相比之下，GeckoView是独立的。
- GeckoView符合Web标准。此外，它还得到了Mozilla的支持。
- GeckoView提供对低Web API的访问和控制。还内置支持私有模式，跟踪保护，WebVR以及即将推出的Web扩展。

GeckoView将会大大增加应用包，在如下几种情况可以考虑使用它：

- 开发一个Web浏览器
- 保证Web API一致性
- 开发依赖于Web技术的游戏

### [Dagger 教程](https://dagger.dev/tutorial/ "Dagger 教程")

<img src="https://miro.medium.com/max/875/1*-5F_pHkHu1Gzl1gnxlAWYw.jpeg"/>

Dagger官方交互式Dagger教程，每个部分都有Dagger示例。

### [Android Studio使用技巧](https://www.raywenderlich.com/2807578-android-studio-tips-and-tricks "Android Studio使用技巧")

图文并茂教你掌握代码导航，重构，调试工具以及插件等

### [支持Android Q手势导航](https://jeroenmols.com/blog/2019/07/17/androidqgestures/ "支持Android Q手势导航")

<img src="https://jeroenmols.com/img/blog/androidqgestures/androidqgestures.png"/>

从Android Q开始，设备现在可以在完全手势模式下导航系统。在该模式下，不再有屏幕上的后退按钮，用户可以从两个边缘滑动。

在这篇博文中，介绍如何在飞利浦Hue应用程序中添加对这些手势的支持。

### [MotionLayout 实现动态工具栏](https://blog.stylingandroid.com/motionlayout-dynamic-toolbar/ "MotionLayout 实现动态工具栏")

通过MotionLayout可以创建一些非常有趣的动画，本文通过案例教你如何实现动态工具栏

### [Android矢量图](https://www.raywenderlich.com/3988300-vector-graphics-on-android "Android矢量图")

在本教程中，您将了解什么是矢量图以及如何在Android上创建和操作矢量图

### [探索App Actions](https://joebirch.co/2019/07/16/exploring-app-actions-on-android-what-are-app-actions/ "探索App Actions")

App Actions允许我们扩展Google智能助理的功能，嵌入到我们的应用程序。通过将这两种技术结合在一起，能够带来更好的用户体验。

本文深入研究App Actions，并学习如何实现App Actions

### [ARCore面部化妆](https://medium.com/@KristiSimakova/try-on-makeup-with-augmented-faces-d2ade1906f90 "ARCore面部化妆")

<img src="https://miro.medium.com/max/875/0*T6IlqTwpukY6RrIZ"/>

使用ARCore的Augmented Faces功能来创建Android化妆应用。

### [Picassor入门](https://www.raywenderlich.com/3658341-picasso-tutorial-for-android-getting-started "Picassor入门")

<img src="https://koenig-media.raywenderlich.com/uploads/2019/06/Picasso-feature.png"/>

在本教程中，学习如何使用Picassor来加载不同来源的图像以及如何应用滤镜和转换。

## 工具&资源

### [ktlint](https://github.com/pinterest/ktlint "ktlint")

ktlint是一个开源用于检查遵循JetBrains标准Kotlin代码格式工具

### [SocialTextView](https://github.com/hasankucuk/SocialTextView "SocialTextView")

一个简单的自定义Android TextView，高亮手机号码，Email和Url等内容

### [2019 Kotliners会议](https://www.youtube.com/playlist?list=PLnYRVL0Cw1FSUJ-WdhV2Ija9kA9q0qP3e "2019 Kotliners会议")

2019年Kotliners在YouTube上发布了过去所有会议视频

### [eventscalendar](https://github.com/tizisdeepan/eventscalendar "eventscalendar")

<img src="https://github.com/tizisdeepan/eventscalendar/raw/master/screenshots/ss2.png"/>

Events Calendar是一个用户友好炫酷事件日历UI库

### [readme-md-generator](https://github.com/kefranabg/readme-md-generator "readme-md-generator")

<img src="https://user-images.githubusercontent.com/9840435/60266090-9cf9e180-98e7-11e9-9cac-3afeec349bbc.jpg"/>

CLI生成漂亮的README.md文件
