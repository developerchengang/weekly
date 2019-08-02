# [Kotlin领域特定语言：入门](https://www.raywenderlich.com/2780058-domain-specific-languages-in-kotlin-getting-started#toc-anchor-004 "Kotlin领域特定语言：入门")

开发环境：Kotlin 1.3, Android 4.4, Android Studio 3

在这个Kotlin教程中，学习如何使用带有接收器的lambda，构建者模式和扩展函数创建DSL！

在开发过程中开发人员如果想编写简洁易读且易于维护的代码。通常，使用设计模式或者搭建良好架构作为解决方案。你想成为优秀的工程师吗？

Kotlin为你提供工具，特定领域的语言（DSL）！

在本教程中，创建DSL以显示Android对话框，不同的DSL样式以及数据模型。在小狗列表中，选择你喜欢的小狗并在弹出的对话框点击“YES”收藏小狗。在接下来的教程中你将学到：

- 了解在Kotlin中构建DSL的基础知识。
- 学习带有接收器的lambda。
- 使用构建者模式创建DSL。
- 使用Kotlin扩展函数创建DSL。

接下来我们开始学习DSL知识吧。

### 特定领域语言

特定领域语言指的是专注于某个应用程序领域的计算机语言。又译作领域专用语言。提取部分代码，使其可重用且更易理解。与函数或方法相反，DSL会改变你使用和编写代码的方式。通常，DSL使代码更具可读性，几乎就像自然语言一样。即使不了解代码的人也能够大概理解它的含义。

使用DSL意味着改变部分代码语法。在Kotlin中，通过使用lambda和扩展函数以及表达式来实现的，删除大量的样板代码并隐藏内部实现。一个最好的例子是Android构建工具 - Gradle

### 流行的DSL

如果你是Android开发人员，你肯定接触过DSL。请看以下代码：

```kotlin

android {
  compileSdkVersion 28
  defaultConfig {
    applicationId "android.raywenderlich.com.puppyparadise"
    minSdkVersion 19
    targetSdkVersion 28
    versionCode 1
    versionName "1.0"
    testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
  }
  buildTypes {
    release {
      minifyEnabled false
      proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
    }
  }
}

```

是否很惊讶地发现你曾经使用DSL编写过Gradle构建文件？

查看`build.gradle`文件中的代码编写方式。对象使用大括号。在这些括号中，编写参数名称然后设置参数的值。

下面，请看没有使用DSL编写的相同逻辑代码：

``` kotlin

Android(28,
  DefaultConfig("android.raywenderlich.com.puppyparadise",
    19,
    28,
    1,
    "1.0",
    "android.support.test.runner.AndroidJUnitRunner"
  )
),
  BuildTypes(
  Release(false,
    getDefaultProguardFile('proguard-android-optimize.txt'),
    'proguard-rules.pro'
    )
)

```

乍一看，它看起来不清晰，主要是因为每个对象都有很多参数，而你又不知道它们的参数名称。 通过比较这两种方法，你可以看到使用DSL编写的代码更易于阅读。更重要的是，因为你知道参数名称和属性，这样更容易维护。 这是DSL重要特性之一，它比对象更容易使用。

另一个流行的例子是Anko。 它是一组Kotlin DSL库，包含许多功能。不仅用于UI组件，还用于处理网络调用，后台任务和数据库管理。下面的代码片段使用协程执行后台调用：

``` kotlin

suspend fun getData(): Data { ... }

class MyActivity : Activity() {
  fun loadAndShowData() {
    // Ref<T> 使用弱引用
    val ref: Ref<MyActivity> = this.asReference()

    async(UI) {
      val data = getData()

      // 使用ref()代替this@MyActivity
      ref().showData(data)
    }
  }

  fun showData(data: Data) { ... }
}

```

`asnyc`大括号是DSL的签名。 在这里，声明函数调用在异步中完成，现在无需深入研究实现细节。如果你想查看更多Anko库的示例，请查看官方[GitHub页面](https://github.com/Kotlin/anko "anko")。

### 入门

在开始编写DSL之前，请从点击[链接](https://koenig-media.raywenderlich.com/uploads/2019/05/PuppyParadise.zip "代码")获取代码。 包含初始项目和最终项目，将在整个教程中使用到。

下载完成之后，构建并运行应用程序，如下图所示：

<img src="https://koenig-media.raywenderlich.com/uploads/2019/04/puppies-287x500.jpg"/>

你可以看到可爱的小狗列表。你可以单击其中任何一个以打开对话框

<img src="https://koenig-media.raywenderlich.com/uploads/2019/04/puppies_dialog-287x500.jpg"/>

点击小狗后，会显示一个背景模糊的对话框。是否喜欢小狗。如果选择“YES”选项，则会在图片右下角显示心形图标。 选择“NO”选项会移除心形图标，你不需要“NO”，因为所有的小狗都太可爱了。

该对话框是本教程的重点。 打开`DialogPopupView`类。 如果查看代码，可以看到该类包含对话框的几个属性。 包括点击监听事件和模糊背景的方法。 在底部，你可以找到`DialogPopupBuilder`，它负责构建和设置这些属性，最终创建一个对话框。

打开`PuppyActivity.kt`并查看`createDialogPopup()`：

``` kotlin

DialogPopupView.builder(this)
    .viewToBlur(rootView)
    .titleText(titleText)
    .negativeText(negativeText)
    .positiveText(positiveText)
    .onBackgroundClickAction(backgroundClickAction)
    .onCancelClickAction(cancelActionClick)
    .onPositiveClickAction(positiveClickAction)
    .build()

```

此方法使用构建者模式创建`DialogPopupView`。目标是使用DSL使代码更简洁。简单来讲，就是重构上面代码，改写如下：

``` kotlin

buildDialog(this) {
  viewToBlur(rootView)
  title(titleText)
  positiveAction(positiveText) { positiveClickAction() }
  negativeAction(negativeText) { negativeClickAction() }
  backgroundAction { backgroundClickAction() }
}

```

**注意：如果你不熟悉构建者模式，则应查看Swift中的设计模式。虽然是Swift编写的教程，但该教程中描述的概念适用于包括Kotlin在内的所有编程语言。**

正如你所看到的，对于构建者模式，使用DSL，代码量更少。

### Kotlin的DSL

既然你已经知道要实现什么，那么你需要使用Kotlin语言的两个重要特性来创建DSL：

- Lambda表达式
- 高阶函数
- Lambda与接收器

lambda表达式是一个匿名函数，也可称为闭包。Lambda 允许把函数作为一个方法的参数（函数作为参数传递进方法中），或者赋值给属性。 如果你不熟悉lambda表达式，可以查看[官方文档](https://kotlinlang.org/docs/reference/lambdas.html "官方文档")。

要创建或使用lambda表达式，首先必须声明所需的**lambda类型**。 lambda类型语法如下：`（parameter，parameter）-> returnType`。

我们将其分成箭头的左侧和右侧两部分来解释。在左侧，括号内有必需的参数。你可以为每个lambda函数定义任意数量的参数，因此它不一定只有一个或两个参数。可以没有参数，也可以有任意数量的参数。

在右侧，定义返回类型。更简单来讲，在左侧，将参数传递给右侧，调用方法并返回结果。对于没有返回值的lambda函数，可以使用`Unit`作为返回类型。如果编写一个带有`String`参数并返回`Int`的lambdas：`（String）-> Int`。

但是，在代码中使用lambdas表达式时，编写方式与lambda类型语法不同。使用lambda：`{parameter，parameter  -> behavior}`。首先是花括号并定义参数列表。然后使用箭头（`->`）分隔代码。之后，你可以在箭头和右括号之间调用任意数量的函数。

### 推断Lamda参数

例如，如果lambda只有一个参数，可以省略。然后在花括号内推断，并给它命名（隐式名称）。在使用集合函数时很常见，因为在过滤列表时会编写类似：`list.filter {it.isFavorite}` 代码。 将此示例中的`it`（可以取任意名称）推断为列表中的每一项，进行迭代。

### 高阶函数

高阶函数是Kotlin中的一个特性，如果函数的最后一个参数是函数，那么作为相应参数传入的 lambda 表达式可以放在圆括号之外。此外，如果它是唯一的参数，则可以完全删除括号。假设有一个类似这样的方法`method({})`，可以简写为`method{}`。使得代码更具可读性。

### Lambda与接收器

想象一下，你有一个模型类，如下所示：

``` kotlin

data class Puppy(var isLiked: Boolean = false, var imageResource: Int = 0)

```

你可以通过名为`puppy`的函数来创建DSL，该函数将lambda作为参数并返回`Puppy`对象：

``` kotlin

fun puppy(lambda: (Puppy) -> Unit): Puppy {
  // 1
  val puppy = Puppy()
  // 2
  lambda(puppy)
  // 3
  return puppy
}

```

在此方法中，做了以下操作：

1. 实例化一个`Puppy`对象
2. 调用lambda并传递`Puppy`对象
3. 返回`Puppy`

你可以调用DSL，创建和编辑`Puppy`：

``` kotlin

puppy {
  it.isLiked = true
  it.imageResource = R.drawable.golden_retriever
}

```

调用`puppy`函数并在大括号内设置属性。当前的解决方案有效，但你必须使用`it`来访问属性。还可以通过使用接收器实现lambda来解决。

带接收器的lambda允许你在没有任何限定符（例如`it`）的情况下调用lambda体中对象。你可以使用class（类）类型添加接收器，这样是该类型的任何对象都可以调用函数。查看下面的代码段：

``` kotlin

fun puppy(lambda: Puppy.() -> Unit): Puppy {
  val puppy = Puppy()
  puppy.lambda()
  return puppy
}

```

请注意，之前，lambda将一个`Puppy`（`lambda: (Puppy) -> Unit`）传递给调用者。但是，对于接收器，你可以直接在任何`Puppy`对象上将lambda作为函数调用。还可以使代码更简单，可以使用Kotlin的`apply`扩展函数：

``` kotlin

fun puppy(lambda: Puppy.() -> Unit) = Puppy().apply(lambda)

```

`apply`允许你通过直接引用对象属性。现在`puppy`方法调用是这样的：

``` kotlin

puppy {
  isLiked = true
  imageResource = R.drawable.golden_retriever
}

```

你现在可以直接引用该对象属性，而不必通过`it`关键字，因为已经明确表示必须是`Puppy`类型。

### 你的第一个DSL

有了上述知识，是时候修改`DialogPopupBuilder`并创建你的第一个DSL了！

你将所学知识重构`DialogPopupView`并创建一个DSL。目标是通过lambda替换当前函数来设置属性。这样，你将能够在括号外使用lambdas调用构建器，而无需使用链式函数调用。将`DialogPopupBuilder`替换为：

``` kotlin

class DialogPopupBuilder {
  var context: Context? = null
  var viewToBlur: View? = null
  var titleText: String = ""
  var negativeText: String = ""
  var positiveText: String = ""
  var onBackgroundClickAction: () -> Unit = {}
  var onNegativeClickAction: () -> Unit = {}
  var onPositiveClickAction: () -> Unit = {}

  inline fun with(context: () -> Context) {
    this.context = context()
  }

  inline fun viewToBlur(viewToBlur: () -> View) {
    this.viewToBlur = viewToBlur()
  }

  inline fun titleText(title: () -> String) {
    this.titleText = title()
  }

  inline fun negativeText(negativeText: () -> String) {
    this.negativeText = negativeText()
  }

  inline fun positiveText(positiveText: () -> String) {
    this.positiveText = positiveText()
  }

  fun onNegativeClickAction(onNegativeClickAction: () -> Unit) {
    this.onNegativeClickAction = onNegativeClickAction
  }

  fun onPositiveClickAction(onPositiveClickAction: () -> Unit) {
    this.onPositiveClickAction = onPositiveClickAction
  }

  fun onBackgroundClickAction(onBackgroundClickAction: () -> Unit) {
    this.onBackgroundClickAction = onBackgroundClickAction
  }

  fun build() = DialogPopupView(context!!, this)
}

```

删除了构造函数并添加了`with()`方法，现在代码看起来清晰很多。由于我们将使用DSL来构建对话框，因此不需要再通过`builder`方法构建`DialogPopupView`。从`companion object`中删除`builder`

最后，编写一个DSL，它将创建`DialogPopupBuilder`并构建`DialogPopupView`。创建一个名为`DialogPopupViewDsl.kt`的新Kotlin文件并粘贴以下代码：

``` kotlin

fun dialogPopupView(lambda: DialogPopupView.DialogPopupBuilder.() -> Unit) =
  DialogPopupView.DialogPopupBuilder() // 1
    .apply(lambda)                     // 2
    .build()                           // 3

```

该函数有一个带有`DialogPopupBuilder`接收器的lambda作为参数。 每行分解如下：

1. 实例化`DialogPopupBuilder`的实例。
2. 使用lambda设置所有属性。
3. 调用`build()`返回`DialogPopupView`。

在`PuppyActivity`中使用DSL。更改`createDialogPopup()`方法以使用DSL：

``` kotlin

dialogPopupView {
  with { this@PuppyActivity }
  viewToBlur { rootView }
  titleText { titleText }
  negativeText { negativeText }
  positiveText { positiveText }
  onPositiveClickAction { positiveClickAction() }
  onNegativeClickAction { negativeClickAction() }
  onBackgroundClickAction { backgroundClickAction() }
}

```

`dialogPopupView()`直接获取对话框每个属性，无需链式调用或调用`build()`方法。

构建并运行代码。和之前看到的一样，测试对话框确保能正常运行。

### 带扩展函数的DSL

你刚刚使用构建者模式创建了第一个DSL！

接下来，你将使用扩展函数创建DSL并应用构建者模式来显示小狗的数据！

扩展函数是允许你向现有类类型添加新功能的函数。任何类型的对象都可以使用扩展函数。如果你不熟悉扩展函数，可以查看[官方文档](https://kotlinlang.org/docs/reference/extensions.html "官方文档")。

使用扩展函数为同一个`DialogPopupView`创建另一个DSL。

创建一个名为`DialogPopupViewWithExtensionsDsl.kt`的新Kotlin文件。 这一次，你需要将`context`作为参数传递，将UI与属性分开。将标题作为扩展函数。

首先，创建一个`buildDialog`函数，它将创建整个对话框并构建它：

``` kotlin

inline fun buildDialog(context: Context, buildDialog: DialogPopupView.DialogPopupBuilder.() -> Unit): DialogPopupView {
  val builder = DialogPopupView.DialogPopupBuilder()

  builder.context = context
  builder.buildDialog()
  return builder.build()
}

```

该函数接受`Context`以及`DialogPopupView.DialogPopupBuilder`类型的接收器。构建对话框与上一个示例相同。

接下来，为每个属性创建一个扩展函数：

``` kotlin

fun DialogPopupView.DialogPopupBuilder.title(title: String) {
  this.titleText = title
}

fun DialogPopupView.DialogPopupBuilder.viewToBlur(viewToBlur: View) {
  this.viewToBlur = viewToBlur
}

fun DialogPopupView.DialogPopupBuilder.negativeAction(
  negativeText: String,
  onNegativeClickAction: () -> Unit
) {
  this.onNegativeClickAction = onNegativeClickAction
  this.negativeText = negativeText
}

fun DialogPopupView.DialogPopupBuilder.positiveAction(
  positiveText: String,
  onPositiveClickAction: () -> Unit
) {
  this.onPositiveClickAction = onPositiveClickAction
  this.positiveText = positiveText
}

fun DialogPopupView.DialogPopupBuilder.backgroundAction(onBackgroundClickAction: () -> Unit) {
  this.onBackgroundClickAction = onBackgroundClickAction
}

```

最后，更改`PuppyActivity.kt`中的`createDialogPopup()`以使用新的DSL：

``` kotlin

buildDialog(this) {
  viewToBlur(rootView)
  title(titleText)
  positiveAction(positiveText) { positiveClickAction() }
  negativeAction(negativeText) { negativeClickAction() }
  backgroundAction { backgroundClickAction() }
}

```

现在通过参数而不是函数设置`context`。Positive和negative的动作与它们各自的文本相结合，通过对代码进行分组来提高可读性。

构建并运行代码以验证一切是否按预期工作。 再次，你将获得与以前相同的屏幕，因为你只更改了语法而不是逻辑。 但是，确保它永远不会伤害！

### DSL收藏

DSL的另一个有趣用途是收藏。 看看小狗，它在PuppyActivity的顶部实例化。 代码本身看起来非常干净和可读; 这是因为Puppy类中目前只有两个属性。 但是如果你有四个或更多的属性，它将开始显得笨重。 因此，你将创建一个将改变实例化集合的方式的DSL。

创建一个名为PuppiesDsl.kt的新Kotlin文件。 首先，添加一个具有两个属性和构建方法的PuppyBuilder：

``` kotlin

class PuppyBuilder {
  var isLiked: Boolean = false
  var imageResourceId: Int = 0

  fun build(): Puppy = Puppy(isLiked, imageResourceId)
}

```

构建方法返回具有列出属性的`Puppy`。

接下来，创建一个`Puppies.kt`文件，该文件扩展了Puppy的ArrayList并具有puppy方法：

``` kotlin

class Puppies : ArrayList<Puppy>() {
  fun puppy(puppyBuilder: PuppyBuilder.() -> Unit) {
    add(PuppyBuilder().apply(puppyBuilder).build())
  }
}

```

puppy（）使用lambda和PuppyBuilder类型的接收器。 在里面，你从ArrayList调用add（）来添加一个用PuppyBuilder构建的新Puppy。

接下来，你需要创建一个PuppyViewModelBuilder，通过添加以下代码来保存所有小狗的列表：

``` kotlin

class PuppyViewModelBuilder {
  private val puppies = mutableListOf<Puppy>()

  fun puppies(puppiesList: Puppies.() -> Unit) {
    puppies.addAll(Puppies().apply(puppiesList))
  }

  fun build(): ArrayList<Puppy> = ArrayList(puppies)
}

```

该类包含一个Puppy的MutableList。 puppies（）有一个带有Puppies类型接收器的lambda，它将通过调用puppiesList（）返回的所有元素添加到集合中。 此外，你添加了build（），它返回Puppy的ArrayList，其中包含puppies作为其数据。

最后，在PuppiesDsl中创建一个puppyViewModel方法：

``` kotlin

fun puppyViewModel(puppies: PuppyViewModelBuilder.() -> Unit): ArrayList<Puppy> =
  PuppyViewModelBuilder().apply(puppies).build()

```

该函数使用lambda和PuppyViewModelBuilder类型的接收器作为参数，你可以使用它来构建Puppy的ArrayList。

现在，你可以使用你刚刚创建的DSL替换PuppyActivity.kt中的代码，该代码可以创建小狗：

``` kotlin

private var puppies: List<Puppy> = puppyViewModel {
    puppies {
      puppy {
        isLiked = false
        imageResourceId = R.drawable.samoyed
      }
      puppy {
        isLiked = false
        imageResourceId = R.drawable.shiba
      }
      puppy {
        isLiked = false
        imageResourceId = R.drawable.siberian_husky
      }
      puppy {
        isLiked = false
        imageResourceId = R.drawable.akita
      }
      puppy {
        isLiked = false
        imageResourceId = R.drawable.german_shepherd
      }
      puppy {
        isLiked = false
        imageResourceId = R.drawable.golden_retriever
      }
    }
  }

```

首先，调用puppyViewModel（），开始数据构建。 在里面，你可以调用puppies（），你可以在其中为你需要创建的每个Puppy调用puppy（）。 这些调用中的每一个都会创建一个新的Puppy，你可以随意使用它们的属性。

创建集合的当前语法看起来像JSON结构，非常用户友好。 这种DSL的好处会越来越大，Puppy会越大越复杂。 我们都知道小狗如何成长！：]

构建并运行应用程序以检查当前状态。 你应该获得相同的起始屏幕，其中包含相同顺序的小狗列表。

### DSL标记

尝试将新Puppy添加到现有列表中的现有Puppy或Puppy的新ArrayList中。 即使你不应该这样做，你也会看到你能够做到这一点，因为它可能会破坏数据。 因为你在其他lambdas中创建lambdas，你仍然可以访问外部lambda的接收器！ 为了防止这种情况，你需要创建一个DSL标记，专门用于解决此问题。 在PuppiesDsl内部，在底部，创建一个名为PuppyDslMarker的新注释类：

``` kotlin

@DslMarker
annotation class PuppyDslMarker

```

@DslMarker指定用它标记的类或PuppyDslMarker定义DSL。

接下来，使用@PuppyDslMarker注释PuppiesDsl.kt文件中的所有类。 尝试将新Puppy添加到现有Puppy中，你将收到一条错误消息，指出“无法使用隐式接收器调用。”问题解决了！

### 最后

你可以使用本教程顶部或底部的“下载材料”按钮下载最终项目。

在本教程中，你学习了如何针对不同情况制作不同类型的DSL。你现在可以创建自己的特定DSL，这将简化你的日常编程。 如果你想了解更多信息，请查看[官方文档](https://build.bitcoinabc.org/app/dsl-documentation/index.html "官方文档")。


