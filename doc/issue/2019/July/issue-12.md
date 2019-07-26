## 文摘

### [了解渐进式JPEG和WebP格式](https://www.shopify.com/partners/blog/progressive-jpeg-and-webp "了解渐进式JPEG和WebP格式")

#### 什么是进步的jpeg

渐进式JPEG是使用与典型标准JPEG不同的编码过程创建的图像。传统上，JPEG从上到下，从左到右进行编码和解码。这被称为基线编码。但是，渐进式JPEG以不同的方式编码。当您看到渐进式JPEG加载时，您将看到整个图像的模糊版本，随着时间的推移，图像被解码或在浏览器中呈现时会变得更加清晰。

![标准JPEG加载率为33％，66％和100％](https://cdn.shopify.com/s/files/1/0533/2089/files/JPEG-and-WebP-baseline_0a04d4c3-6d58-423d-ac7d-279f398cd8ff.jpg?v=1563811818)

![渐进式JPEG加载，分别为33％，66％和100％](https://cdn.shopify.com/s/files/1/0533/2089/files/JPEG-and-WebP-progressive.jpg?v=1563811737)

#### 为什么要使用渐进式JPEG

渐进式JPEG的一个明显优势是存在感知性能提升。用户可以预览图像在下载完成之前的样子。此外，图像占用您网站的布局和空间加载速度更快，使整个过程感觉更快。渐进式JPEG通常也比非渐进式JPEG小，即使最终图像在视觉上是相同的。

重要的是，渐进式JPEG会占用更多的CPU和内存来进行编码和解码，因为图像数据会被多次解析。因此，虽然它确实可以让您更快地进行预览，但解码的总时间可能会接近2.5倍。

#### WebP

WebP是一种现代图像格式，可为Web上的图像提供卓越的压缩，与PNG和JPEG等传统文件格式相比，文件大小平均节省30％以上。较小的图像意味着下载速度更快以及减少网络带宽，这两者都有助于页面显着更快地显示。

<img src="https://cdn.shopify.com/s/files/1/0533/2089/files/JPEG-and-WebP-format.png?v=1563811862"/>

可以在Chrome开发者控制台，查看图像类型。

#### 何时应该使用渐进式JPEG与WebP

除了使用延迟加载之外，使用WebP是理想方式。

如果你想使用渐进式JPEG，请确保你理解为什么要使用它们 - 因为它们也有缺点。我会警告不要使用渐进式JPEG格式来处理像缩略图这样的小图像，因为这些文件的文件大小往往比普通的JPEG图像大。

像任何东西一样，重要的是测试 并看看否真的减少了时间。在某些情况下，使用渐进式JPEG可能比WebP格式更好。例如，考虑文件大小差异。如果渐进式JPEG接近（在10kb到20kb之间）或小于WebP，则考虑使用渐进式JPEG而不是WebP。

### [渐进增强vs优雅降级](https://zhuanlan.zhihu.com/p/34415047 "渐进增强vs优雅降级")

<img src="https://pic3.zhimg.com/80/v2-919cb5da54eda9705318d51b339c0862_hd.jpg"/>

渐进增强：在网站设计初期以主体功能为主，一般都以IE为最低兼容对象并逐步的向主流浏览器兼容（如Chrome、Firefox等），这样就会使一些新的前端技术、功能无法全效展示。并追求极致的用户体验也就是说用户使用任何浏览器访问网页都不会觉得有什么不同。比如一些大型的公开网站、门户类网站都会使用渐进增强的方式开发，因为你不知道用户会使用什么样的浏览器和设备访问，你必须做到页面功能的全部兼容。

优雅降级：在网站设计初期以主流浏览器的标准为主，并赋予项目各种新技术和功能已达到最佳展示效果，然后在对一些不兼容的浏览器和设备做一些简单的向下兼容，或直接舍弃。有时我们在浏览一些web网页的时候会发现他有些提示：推荐使用某某浏览器或是请使用某某设备访问等等。这些web项目都舍弃了一些客户端来实现项目的最佳效果，而这种网站还是少数优雅降级的常用场景还有一些公司内部的系统或是特定用户和场景的应用。

## 教程

### [React的完整介绍](https://jscomplete.com/learn/complete-intro-react "React的完整介绍")

<img src="https://www.reactjscn.com/logo-og.png"/>

适合初学者的指南，涵盖了React的基础知识的概念。它不是React的编程指南，而是完整的介绍。

### [破解Android应用](https://java-design-patterns.com/ "破解Android应用")

<img src="https://koenig-media.raywenderlich.com/uploads/2019/06/mascot_android-lab-technician-500x500.png"/>

本文并不是教你怎么去破解他人Android应用，而是帮助您成为具有安全意识的应用程序开发者。在本教程你能学到如下知识：

- 访问应用的私有数据
- 分析数据库
- 反编译代码

### [Vim历史和高效使用Vim](https://begriffs.com/posts/2019-07-19-history-use-vim.html "Vim历史和高效使用Vim")

<img src="https://www.runoob.com/wp-content/uploads/2015/10/vi-vim-cheat-sheet-sch.gif"/>

本文研究Vim历史，同时教你如何高效利用Vim

### [JavaScript SEO基础知识](https://developers.google.com/search/docs/guides/javascript-seo-basics "JavaScript SEO基础知识")

本指南介绍了Google搜索如何处理JavaScript以及改进web应用的最佳做法。

### [异步加载CSS的最简单方法](https://www.filamentgroup.com/lab/load-css-simpler/?utm_source=Responsive+Design+Weekly&utm_campaign=fb3189a12c-RWD_Newsletter_370&utm_medium=email&utm_term=0_df65b6d7c8-fb3189a12c-59181885 "异步加载CSS的最简单方法")

默认情况下，浏览器会同步加载外部CSS - 在下载和解析CSS时会影响页面渲染。本文教你如何使用最简单方式实现异步加载CSS。

### [在没有框架的情况下设计和构建渐进式Web应用程序（第1部分）](https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1/ "在没有框架的情况下设计和构建渐进式Web应用程序（第1部分）")

不需要计算机专业知识，也不需要了解JavaScript框架。仅需要一点HTML和CSS以及JavaScript基本知识，就能创建渐进式Web应用程序。

### [重构桌面版Slack](https://slack.engineering/rebuilding-slack-on-the-desktop-308d6fe94ae4 "重构桌面版Slack")

<img src="https://miro.medium.com/max/875/0*cgkWRCMtQXti3jbA"/>

不要从头开始重写你的代码。Slack分享他们如何渐进逐步重构桌面版Slack。

### [Changefeed](https://changelog.changefeed.app/general "Changefeed")

精美的更改日志模块

## 资源&工具

### [exif-js](https://github.com/exif-js/exif-js "exif-js")

<img src="https://paul.kinlan.me/images/2019-05-13-extracting-text-from-an-imageexperiments-with-shape-detection-2.jpeg"/>

一个JavaScript库用于提取图片中的文字信息

### [JavaScript的基础知识（播客）](https://syntax.fm/show/001/react-tools "JavaScript的基础知识（播客）")

一个讲解JavaScript的基础知识播客网站

### [用Java实现的设计模式](https://java-design-patterns.com/ "用Java实现的设计模式")

通过简短介绍再搭配UML设计图

### [编程算法书](https://lisp-univ-etc.blogspot.com/ "编程算法书")

<img src="https://2.bp.blogspot.com/-xmwP2e5QeSA/XTXJQd0BTFI/AAAAAAAACG4/FAlIVeffx1M524S7ANdlbwu7Pg4DxK74QCLcBGAs/s320/cover3.png"/>

一本关于算法和Lisp的书，本书分为16章，3部分：基本数据结构，衍生数据和高级算法。作者计划每周在个人博客发布一部分内容，预计年底发布所有内容。

### [编写良好Common Lisp代码指南](https://lisp-lang.org/style-guide/ "编写良好Common Lisp代码指南")

编写良好可维护Common Lisp代码指南

### [JavaScript 代码规范](https://github.com/standard/standard "JavaScript 代码规范")

<img src="https://camo.githubusercontent.com/3c76c70b25e941a4b21554015aebe2913afb3611/68747470733a2f2f63646e2e7261776769742e636f6d2f7374616e646172642f7374616e646172642f6d61737465722f737469636b65722e737667"/>

JavaScript 代码规范，自带 linter & 代码自动修正

### [Python - 100天从新手到大师](https://github.com/jackfrued/Python-100-Days "Python - 100天从新手到大师")

github五万star，只要你能坚持100天就能从零基础步入python编程高手。学习路线：

- Day01~15 - Python语言基础
- Day16~Day20 - Python语言进阶
- Day21~30 - Web前端入门
- Day31~35 - 玩转Linux操作系统
- Day36~40 - 数据库基础和进阶
- Day41~55 - 实战Django
- Day56~60 - 实战Flask
- Day61~65 - 实战Tornado
- Day66~75 - 爬虫开发
- Day76~90 - 数据处理和机器学习
- Day91~100 - 团队项目开发

### [coding-interview-university](https://github.com/jwasham/coding-interview-university "coding-interview-university")

完整的计算机科学研究计划。

### [游戏源代码集合](https://archive.org/details/gamesourcecode "游戏源代码集合")

这是PC游戏源代码的集合。大多数为商业产品，随后开放源代码。

### [Puffer](https://puffer.stanford.edu/ "Puffer")

在浏览器中免费观看电视直播。可以观看NBC，CBS，ABC，PBS，FOX和Univision网络的美国电视台。

Puffer支持Chrome，Firefox和Edge浏览器，PC或Android手机或平板电脑。 不支持在iPhone或iPad或Safari浏览器中使用。

### [纯JS生成WiFi二维码](https://qifi.org/ "纯JS生成WiFi二维码")

纯JS生成`WIFI:S:<SSID>;T:<WPA|WEP|>;P:<password>;;`二维码，生成的二维码保存HTML5 localStorage中，不在服务器。

### [编程讲座](https://github.com/hellerve/programming-talks "编程讲座")

主要收录关于编程语言架构设计相关内容视频

### [calisphere](https://calisphere.org/ "calisphere")

Calisphere是加利福尼亚州著名图书馆，档案馆和博物馆门户网站。收录超过1,275,000张图像，文本和录音。其中收录了上个世纪七十年代中国相关图像。

### [拉长号](https://matthewrayfield.com/goodies/popup-trombone/ "拉长号")

<img src="https://ci6.googleusercontent.com/proxy/NDG3ACLD_XRanOJk54ssgXnbYcVYYRcBDBY-WaeMsW7aD-lzQE-L5Kwu5tkMtTC7Fri5ak9XcnHzrm3PRfym5HAMt0pD8TCONDYeUdQm6Ja9RWXQzWbc1LrldIKbbttgMZzE06z0QaDQRYomqNT6l4Bg2GItuvfoLrM=s0-d-e1-ft#https://res.cloudinary.com/cpress/image/upload/w_1280,e_sharpen:60/v1563889316/dly6bpty0lxomzahcxav.jpg"/>

通过拉缩浏览器来拉长号（听起来也不太像哈哈哈）

### [Web历史](https://thehistoryofweb.design/ "Web历史")

一个有趣的网站简单介绍Web重要历史
