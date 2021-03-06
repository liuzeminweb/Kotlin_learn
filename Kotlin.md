# Kotlin_learn
lzm  总结自https://developer.android.com/courses/android-basics-kotlin/course的Kotlin学习


# 一 Kotlin 中的 Android 基础知识

## 1 使用 Kotlin 编的第一个程序

```
fun main() {
    println("Happy Birthday!")
    println("Jhansi")
    println("You are 25!")
}
```

https://developer.android.com/training/kotlinplayground 是一个网页版交互式代码编辑器，您可以在其中练习编写 Kotlin 程序。

- 所有 Kotlin 程序都需要有一个 main() 函数：fun main() {}
- println() 函数用于输出一行文本。
- 用双引号括住您要输出的文本，例如 "Hello"。
- 重复 println() 指令可输出多行文本。
- 程序中的错误会标记为红色。输出窗格中会显示错误消息，帮助您确定发生错误的位置以及错误原因。
- https://developer.android.com/training/kotlinplayground
- [《使用 Kotlin 进行 Android 开发的基础知识》相关词汇](https://developer.android.com/courses/android-basics-kotlin/android-basics-kotlin-vocab)

## 2 在 Kotlin 中创建生日祝福语

```
val age = 5
```

这一行表示：

- `val` 是 Kotlin 使用的一个特殊单词，称为关键字，用于表示紧随其后的是变量名称。
- `age` 是变量的名称。
- `=` 使 `age`（在其左边）的值等于其右边的值。在数学中，单个等号用于表示等号两边的值相等。与数学中不同，在 Kotlin 中，单个等号用于将等号右边的值赋予等号左边的指定变量。

开发者会这样说：此行声明了一个名为 `age` 的变量，其赋值为 `5`。



**重要提示**：使用 `val` 关键字声明的变量只能设置一次。以后无法在程序中更改该变量的值。不过，您可以使用 `var` 关键字声明可更改的变量。



如需在输出语句中使用变量，需要在变量前后使用一些符号来告诉系统紧随其后的内容不是文本而是变量。系统需要输出变量的值，而非输出文本。为此，您需要将变量放在大括号内并在前面加上美元符号，如下例所示。

```
${variable}
```



关于函数命名的说明：

- 请注意，函数 `printBorder` 的名称以小写的动词开头。函数名称几乎总是以小写的动词开头，并且名称应描述函数的功能。例如：`print()` 或此处的 `printBorder()`。
- 另请注意，名称内的第二个单词以大写字母开头。这种样式称为“驼峰式大小写”，能够使名称更清晰易读。再多举两个名称的例子，譬如 `drawReallyCoolFancyBorder` 和 `printBirthdayMessage`。
- 

**注意**：像这样命名函数是一种“编码惯例”，是开发者之间有关代码格式的一种共识。所有代码均采用类似的格式，就能更加容易地阅读和学习其他编程人员编写的代码。如果您看看其他 Android 开发者编写的代码就会发现，那些代码的格式通常都遵循这些惯例。

如需详细了解如何设置代码格式，您可以在官方样式指南（网址：https://developer.android.com/kotlin/style-guide）中找到所有惯例。该指南中列举的惯例非常多，不过如果您想一探究竟，不妨去看看吧。

### 小结

```
fun main() {
    val age = 4
    val layers = 4
    printCakeCandles(age)
    printCakeTop(age)
    printCakeBottom(age, layers)
}

fun printCakeCandles(age: Int) {
    print ("  ")
    repeat(age) {
          print(",")
    }
    println() // Print an empty line

    print("  ") // Print the inset of the candles on the cake
    repeat(age) {
        print("|")
    }
    println()
}

fun printCakeTop(age: Int) {
    repeat(age + 4) {
        print("=")
    }
    println()
}

fun printCakeBottom(age: Int, layers: Int) {
    repeat(layers) {
        repeat(age + 4) {
            print("@")
        }
        println()
    }
}
```



- 使用 `${}` 将输出语句的文本中的变量和计算括起来。例如：`${age}`，其中的 `age` 就是变量。

- 使用 `val` 关键字和名称创建变量。此值设定后即无法更改。使用等号为变量赋值。值的示例包括文本和数字。

- `String` 是用引号括起来的文本，例如 `"Hello"`。

- `Int` 是正整数或负整数，例如 0、23 或 -1024。

- 您可以将一个或多个参数传入函数中供函数使用，例如：`fun printCakeBottom(age:Int, layers:Int) {}`

- 使用 `repeat() {}` 语句重复一组指令若干次。例如，`repeat (23) { print("%") }` 或 `repeat (layers) { print("@@@@@@@@@@") }`

- 循环是用于多次重复某指令的一个指令。`repeat()` 语句就是循环的一个示例。

- 您可以嵌套循环，即，将循环放到循环内。例如，您可以在 `repeat()` 语句内创建一个 `repeat()` 语句，用于将符号输出若干次和若干行，就像您对蛋糕层所做的那样。

  **有关函数参数用法的摘要**：如需使用包含参数的函数，您需要执行以下三项操作：

- 将参数和类型添加到函数定义中：`printBorder(border: String)`

- 在函数内使用参数：`println(border)`

- 在调用函数时提供参数：`printBorder(border)`





## 3 [下载并安装 Android Studio](https://developer.android.com/codelabs/basic-android-kotlin-training-install-android-studio?continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-kotlin-two%23codelab-https%3A%2F%2Fdeveloper.android.com%2Fcodelabs%2Fbasic-android-kotlin-training-install-android-studio)

### ① 验证系统要求

为了运行 Android Studio，您的计算机和操作系统需要满足一些要求。

1. 请确保互联网连接状况良好且稳定。根据互联网连接的速度和可靠性，安装时间可能会有所不同。
2. 打开任意网络浏览器（例如 [Chrome](https://www.google.com/chrome/?brand=CHBD&gclid=EAIaIQobChMImJ3iyd6u5wIVsRx9Ch3_jAYSEAAYASAAEgJ1H_D_BwE&gclsrc=aw.ds)），然后转到 https://developer.android.com/studio#Requirements。此页面列出了在计算机上安装和运行 Android Studio 需要满足的特定硬件要求。
3. 请按照以下步骤检查 Windows 或 macOS 的系统要求。

### ② 下载 Android Studio

1. 打开任意网络浏览器并转到 https://developer.android.com/studio。（https://developer.android.google.cn/studio/）

这是 Android 开发者网站，您可以从中下载 Android Studio。此页面会自动检测您的操作系统。

1. 点击**下载 Android Studio**。系统会打开 Android Studio 许可协议的**条款及条件**页面。
2. 阅读许可协议。
3. 如果您同意条款及条件，在页面底部，勾选**我已阅读并同意上述条款及条件**。
4. 点击**下载 Android Studio 适用平台…**以开始下载。
5. 当系统提示时，将相应文件保存到您可以轻松找到的位置（例如，**桌面**或**下载**文件夹）。
6. 等待下载完成。下载可能需要一些时间，不妨喝杯茶吧！

### ③ 安装 Android Studio

**注意**：如果您需要更多帮助或想要自定义安装，请查看[安装 Android Studio](https://developer.android.com/studio/install.html) 的说明，其中包括抓屏说明。

#### 在 macOS 上安装 Android Studio

1. 打开您下载并保存了 Android Studio 安装文件的文件夹。
2. 双击下载的文件。系统随即会显示以下弹出式窗口：

![ec12d090ffcc39e4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-install-android-studio/img/ec12d090ffcc39e4.png)

1. 将 **Android Studio** 图标拖放到**应用程序**文件夹中。
2. 在**应用程序**文件夹中，双击 **Android Studio** 图标，以启动 **Android Studio 设置向导**。

如果您看到有关安装或运行从互联网下载的文件的警告，请选择接受安装。

按照 **Android Studio 设置向导**进行操作，接受所有步骤的默认设置。

在安装过程中，设置向导会下载并安装开发 Android 应用所需的其他组件和工具。这可能需要一些时间，具体取决于您的网速。不妨再续一杯茶吧！

1. 安装完成后，Android Studio 会自动启动。

系统将打开 **Welcome to Android Studio** 对话框，您可以随时开始创建应用！

![a90bab2f521eaa97.png](https://developer.android.com/codelabs/basic-android-kotlin-training-install-android-studio/img/a90bab2f521eaa97.png)

#### 在 Windows 上安装 Android Studio

1. 打开您下载并保存了 Android Studio 安装文件的文件夹。
2. 双击下载的文件。

如果您看到有关允许安装更改计算机的警告，请确认安装。

此时将显示 **Welcome to Android Studio Setup** 对话框。

![7fe7a67467d22fb0.jpeg](https://developer.android.com/codelabs/basic-android-kotlin-training-install-android-studio/img/7fe7a67467d22fb0.jpeg)

1. 点击 **Next** 开始安装。
2. 接受所有步骤的默认安装设置。
3. 安装完成后，点击 **Finish**。

**此时会显示 Android Studio 设置向导**。

1. 按照 **Android Studio 设置向导**进行操作，接受所有步骤的默认设置。

在安装过程中，设置向导会下载并安装开发 Android 应用所需的其他组件和工具。这可能需要一些时间，具体取决于您的网速。不妨再续一杯茶吧！

1. 下载并安装完成后，点击 **Finish**。

此时将显示 **Welcome to Android Studio** 对话框，您可以随时开始创建应用！

![a90bab2f521eaa97.png](https://developer.android.com/codelabs/basic-android-kotlin-training-install-android-studio/img/a90bab2f521eaa97.png)

祝贺您！您已成功安装 Android Studio。现在，您可以执行下一步了！



### ④ 创建并运行您的首个 Android 应用

- ##### 项目模板

在 Android Studio 中，项目模板是一个 Android 应用，其中包含所有必要的部件，但不具有什么功能。其宗旨是帮助您更快地入门，为您省去一些工作。Android Studio 中的一些模板示例包括：包含一个地图的应用以及具有多个屏幕的应用。

- ##### 创建空 Activity 项目

在以下步骤中，您将使用 **Empty Activity** 项目模板为您的新应用创建一个新的 Android Studio 项目。

1. 点击 Android Studio 图标 ![815d56ac706c78d4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/815d56ac706c78d4.png) 启动 Android Studio（如果尚未打开）。

系统随即会显示 **Welcome to Android Studio** 窗口。

![a08769027af79823.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/a08769027af79823.png)

1. 在 **Welcome to Android Studio** 窗口中，点击 **+ Start a new Android Studio project**。

系统随即会打开 **Create New Project** 窗口，其中列出了 Android Studio 提供的模板。

![ae293fe0a0b06a45.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/ae293fe0a0b06a45.png)

1. 点击顶部的标签页并滚动浏览模板，了解您可以执行的操作！我们针对许多不同类型的设备（例如手机、平板电脑和手表）以及不同类型的应用（具有可滚动屏幕的应用、包含地图的应用以及采用复杂导航方式的应用）提供了模板。
2. 在窗口左上角，点击 **Phone and Tablet** 标签页。
3. 点击最上面一行中的 **Empty Activity** 模板，以选择该模板作为项目的模板。

**Empty Activity** 模板是可用于创建应用的最简单的模板。它只有一个屏幕，上面显示一条简单的消息“Hello World!”。

1. 点击窗口底部的 **Next**。系统随即会打开 **Create New Project** 对话框。

![204a8fde117875a5.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/204a8fde117875a5.png)

按如下方式配置项目：

1. **Name** 是应用的名称。在 **Name** 下方的框中，输入 `Happy Birthday` 作为项目的名称。
2. **Package name** 是 Android 系统用来唯一标识您的应用的名称。通常，该名称默认为贵组织的名称后跟应用的名称，且所有字符均采用小写形式（在此例中为“`com.example.happybirthday`”）。
3. **Save location** 是保存与项目相关的所有文件的位置。请记下这些文件在您计算机上的保存位置，以便查找文件。您可以暂时将“Save location”字段保留原样。
4. **Language** 定义了您要用于构建项目的编程语言。请确保在 **Language** 字段中选择 `Kotlin`。
5. **Minimum SDK** 指示可运行您的应用的最低 Android 版本。从下拉列表中选择 `API 19: Android 4.4 (KitKat)`。

**注意**：Android 操作系统有许多不同的版本，每个版本在发布时都按字母顺序指定了名称。

1. 请注意 **Minimum SDK** 下的信息性说明，该说明指出了如果选择相应 API 级别，您的应用可以在多少设备上运行。如果您有兴趣，请点击 **Help me choose** 链接，以查看各个 Android 版本的列表，如下所示。然后，返回 **New Project** 窗口。

![f650fadcfac653de.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/f650fadcfac653de.png)

1. 在 **Create New Project** 窗口中，确保 **Use legacy android.support libraries** 未选中。如果您想详细了解相关信息，请点击问号图标。
2. 点击 **Finish**。

Android Studio 会打开项目及其所有文件。

![c27a57875b0356f2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/c27a57875b0356f2.png)

首次打开 Android Studio 时，您会看到以下三个窗口：

(1) **Project** 窗口显示项目的文件和文件夹。

(2) **Editing** 窗口用于修改代码。

(3) **What's New** 窗口显示资讯和实用提示。

在 Android Studio 的右下角，会显示进度条或消息来指示 Android Studio 是否仍在设置您的项目。例如：

![68405342ab13c821.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/68405342ab13c821.png)

1. 等待 Android Studio 完成项目设置。项目设置完成后，系统会在左下角显示一条消息通知您，如下所示。

![3558f61a535db5d1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/3558f61a535db5d1.png)



### ⑤ 在虚拟设备（模拟器）上运行您的应用

在该任务中，您将使用 [Android 虚拟设备 (AVD) 管理器](http://developer.android.com/tools/devices/managing-avds.html)创建移动设备的软件版本（模拟器），然后在计算机上运行它。虚拟设备（即模拟器）可以模拟特定类型的 Android 设备（如手机）的配置。它可以是搭载您所选 Android 系统版本的任何手机或平板电脑。然后，您将使用该虚拟设备运行通过 **Empty Activity** 模板创建的应用。

**注意**：Android 模拟器是一个用于设置虚拟设备的独立应用，有自己的系统要求。虚拟设备可能会占用大量磁盘空间。如果您遇到任何问题，请参阅[在 Android 模拟器上运行应用](https://developer.android.com/studio/run/emulator.html#Requirements)。

- #### android 修改avd路径 (可不设置)


AVD保存在c:\user\username\.android\avd，后来想改路径，亲测成功。

1、比如你要把AVD放在D盘AndroidAVD下面，则预先在D盘下建立一个文件夹 AndroidAVD。必须的。不然设置了环境变量也没有用，因为模拟器不会自动创建该文件夹。

 

2、在桌面右击“我的电脑”选择“属性”，进入“高级----环境变量-----系统变量----新建“，从而新建一个环境变量ANDROID_SDK_HOME，变量值设置为：D:\AndroidAVD。如图所示。一路确定下来，保存环境变量。重新启动计算机。

 

3、如果你以前没有AVD，则启动AVD Manager新建一个AVD，则文件会全部保存到 D:\AndroidAVD下面。第4点不用看了。

 

4、如果你以前有AVD，改了路径后想继续用，则要把原来c:\user\username\.android\avd下面的全部文件夹复制到  D:\AndroidAVD下面，把avd下面的.ini文件里面的路径 c:\user\username\.android\avd部分全部改成D:\AndroidAVD\.android\avd。再进一个以.AVD结尾的文件夹改下面的hardware-qemu.ini这个文件里面的路径 c:\user\username\.android\avd部分全部改成D:\AndroidAVD\.android\avd。

这2个ini文件里面的路径不改光复制文件过去没有用的，AVD Manager会报错且会删除复制过来的所有avd文件，但并不会删除和影响c:\user\username\.android\avd下面的文件。

为保险，建议新的AVD启动正常能进安卓系统了以后，再把原来c:\user\username\.android\avd下面的所有文件删除即可。



- #### 创建 Android 虚拟设备 (AVD)


如要在计算机上运行模拟器，首先应为虚拟设备创建配置。

1. 在 Android Studio 菜单栏中，依次选择 **Tools > AVD Manager**。

![54805e080c63dfa6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/54805e080c63dfa6.png)

**提示**：您也可以通过在工具栏中点击 AVD 管理器的图标 ![AVD 管理器图标](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/c46555f7a03d86c.png) 将其打开。

系统随即会显示 **Your Virtual Devices** 对话框，如下所示。（如果您以前创建过虚拟设备，此处将会列出。）

![372df0683f138a8e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/372df0683f138a8e.png)

1. 点击 **+ Create Virtual Device**。

系统随即会显示 **Select Hardware** 窗口。![93848e9822710c69.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/93848e9822710c69.png) **Select Hardware** 窗口显示了一系列预配置的设备（按**类别**整理），您可以从中进行选择。对于每种设备，该表都提供了 **Size** 列（提供显示屏尺寸信息）、**Resolution** 列（提供以像素为单位的屏幕分辨率信息）和 **Density** 列（提供像素密度信息）。

1. 选择 **Phone** 类别。
2. 选择一部手机（例如 **`Pixel 3 XL`**），然后点击 **Next**。您可以选择任何手机，但对于此 Codelab，请选择较新的设备。

系统随即会显示 **System Image** 窗口。在该窗口中，选择要在虚拟设备上运行的 Android 系统版本。这可让您在不同版本的 Android 系统上测试您的应用。

![ebb05cea5122f10b.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/ebb05cea5122f10b.png)

1. 在 **Recommended** 标签页中，选择 **`Q`** 作为要在虚拟设备上运行的 Android 系统版本。在撰写本文时，这是最新的 Android 版本，不过您可以选择任何较新的稳定版本。点击[此处](https://source.android.com/setup/start/build-numbers)查看稳定版本列表。

**注意**：如果您要使用的系统映像旁边显示了 **Download** 链接，则说明您的计算机上未安装该映像。您必须先安装映像，然后才能配置虚拟设备。![dca196de91530326.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/dca196de91530326.png)

如需安装系统映像，请点击 **Download** 链接。请注意，下载可能需要较长时间，具体取决于您的互联网连接。下载完成后，点击 **Finish**。

**重要提示**：这些 Android 系统映像会占用大量磁盘空间，因此您的原始安装中只会包含几个。**Recommended** 标签页中只显示了部分 Android 系统版本，除此之外，还有很多。如要查看这些版本的映像，请点击 **x86 Images** 和 **Other Images** 标签页。

1. 点击 **Next**。

系统随即会显示 **Android Virtual Device (AVD)** 窗口，您可以从该窗口中为设备选择其他配置详情。

![e04f76da034d25dd.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/e04f76da034d25dd.png)

1. 在 **AVD Name** 字段中，输入您的 Android 虚拟设备的名称。保持其余部分不变。
2. 点击 **Finish**。

您的新虚拟设备会显示在 **Your Virtual Device** 窗口中，可以开始使用。

![dd2b0e5526503678.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/dd2b0e5526503678.png)

1. 关闭 **Your Virtual Device** 窗口。

- #### 在虚拟设备上运行您的应用


1. 将 Android Studio 调入前台（如果尚不在前台）。
2. 在 Android Studio 中，从工具栏找到虚拟设备下拉菜单（与以下示例类似），然后从下拉列表中选择您创建的虚拟设备。![2a0b5569bde32673.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/2a0b5569bde32673.png)（或者，依次点击 **Run > Select Device..**，然后从弹出式窗口上显示的可用设备中选择您的虚拟设备。）
3. 在 Android Studio 中，依次选择 **Run > Run app**，或点击工具栏中的 **Run** 图标。虚拟设备的启动方式与实体设备类似。这可能需要一些时间，具体取决于您的计算机的速度。

当您的应用准备就绪时，会在虚拟设备上打开，如下所示。

![6330323003a1da4c.png](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/6330323003a1da4c.png)

很好！您的虚拟设备现已启动，正在运行。请注意，应用名称现在为“`Happy Birthday`”，且屏幕上显示“`Hello World!`”。



### ⑥小结

- 如要创建新项目，请启动 Android Studio，点击 **+ Start a new Android Studio project**，为项目命名，选择模板，然后填写详细信息。
- 如要创建 Android 虚拟设备（模拟器）来运行应用，请依次选择 **Tools > AVD Manager**，然后使用 [AVD 管理器](http://developer.android.com/tools/devices/managing-avds.html)选择硬件设备和系统映像。
- 如要在虚拟设备上运行应用，请确保您已创建设备，从工具栏下拉菜单中选择相应设备，然后点击工具栏中的 **Run** 图标 ![依次选择“Run”>“Run app”，或点击工具栏中的“Run”图标 [ICON HERE]。[IMAGEINFO]：ic_run.png，Android Studio 的“Run”图标](https://developer.android.com/codelabs/basic-android-kotlin-training-first-template-project/img/609c3e4473493202.png) 以运行您的应用。
- 如要查找项目文件，请转到 **Project** 窗口，从下拉列表中选择 **Project Source Files**。



## 4 创建 Birthday Card 应用

### ①界面简介

应用的界面 (UI) 就是您在屏幕上所看到的内容，包括文本、图片、按钮和许多其他类型的元素。它既是应用向用户显示内容的方式，也是用户与应用展开互动的载体。

其中的每个元素都是所谓的 `View`。您在应用屏幕上看到的所有内容几乎均属于 `View`。`Views` 还可以是互动元素，例如可点击的按钮或可修改的输入字段。

在本 Codelab 中，您将使用一种用于显示文本的 `View`，我们称之为 `TextView`。

Android 应用中的 `Views` 并非独自悬浮在屏幕上。各个 `Views` 之间彼此存在关联。例如，图片可能位于某些文本旁边，几个按钮也可能会自成一行。若要整理 `Views`，您可以将它们放到一个容器中。`ViewGroup` 就是一个可在其中放入 `View` 对象的容器，负责排列内部的各个 `Views`。排列方式（即布局）可能会因运行应用的 Android 设备的屏幕尺寸和宽高比而发生变化，并且可以根据设备是处于纵向还是横向模式做出调整。

`ConstraintLayout` 就是一种 `ViewGroup`，可帮助您灵活地排列其内部的 `Views`。

![e4c1f4e455d72c81.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/e4c1f4e455d72c81.png)



### ②布局编辑器简介

通过安排 `Views` 和 `ViewGroups` 来创建界面是创建 Android 应用的重要组成部分。Android Studio 提供了一个名为**布局编辑器**的工具，可协助您完成这项操作。您将使用**布局编辑器**将“Hello World!”文本更改为“Happy Birthday!”，随后再设置该文本的样式。

打开**布局编辑器**后，您会看到许多窗口。在本 Codelab 中，您将学习如何使用其中的大部分窗口。请参考下方带有注解的屏幕截图，帮助您识别**布局编辑器**中的窗口。在更改应用时，您将会对每一个窗口作进一步了解。

- 左侧标注 (1) 处就是您之前已看到的 **Project** 窗口，其中列出了构成您项目的所有文件。
- 在中心区域，您能看到标注 (4) 和 (5) 的两个绘图窗口，代表应用的屏幕布局。左侧标注 (4) 的窗口呈现的是应用在运行时屏幕将呈现的近似效果，也就是所谓的 **Design** 视图。
- 右侧标注 (5) 的窗口呈现的是 **Blueprint** 视图。在执行特定操作时，该视图会非常有用。
- 标注 (2) 的 **Palette** 窗口包含的是您可以向应用添加的各类 `Views` 的列表。
- 标注 (3) 的 **Component Tree** 窗口则是屏幕视图的另一种呈现形式。它会列出屏幕的所有视图。
- 最右边标注 (6) 的窗口是 **Attributes** 视图，其中显示了 `View` 的各个属性。您可在此处更改这些属性。

如需详细了解**布局编辑器**以及如何对其进行配置，请参阅[开发者参考指南](https://developer.android.com/studio/write/layout-editor)。

整个**布局编辑器**的屏幕截图（带注解）：

![ba8fee53dbc7dba4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/ba8fee53dbc7dba4.png)



### ③更改 Hello World 消息

1. 在 Android Studio 中，找到左侧的 **Project** 窗口。

2. 留意下面这些文件夹和文件：**app** 文件夹包含您要更改的大多数应用文件。**res** 文件夹用于各种资源，例如图片或屏幕布局。**layout** 文件夹用于屏幕布局。`activity_main.xml` 文件包含屏幕布局的说明。

3. 依次展开 **app** 文件夹、**res** 文件夹和 **layout** 文件夹。

4. 双击 `activity_main.xml`。系统随即会在**布局编辑器**中打开 `activity_main.xml` 并会在 **Design** 视图中显示它描述的布局。![8cf417be2106c8d6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/8cf417be2106c8d6.png)

   

   **注意**：在这些 Codelab 中，您经常需要像上述步骤一样打开文件。简而言之，这些步骤可以归纳为以下几个步骤：打开 **activity_main.xml** (**res** > **layout** > **activity_main.xml**)，不必单独列出每一个步骤。

   

5. 查看 **Component Tree** 中的视图列表。请注意，该列表中有一个 `ConstraintLayout`，它下面有一个 `TextView`。这些表示应用的界面。`TextView` 之所以缩进显示，是因为它位于 `ConstraintLayout` 中。当您向 `ConstraintLayout` 添加更多的 `Views` 时，它们都会被添加到这个列表中。

6. 注意 `TextView` 旁边显示的 **“Hello World!”**，也就是您在运行应用后会看到的那个文本。

   **text** 属性会显示在 `TextView` 中输出的文本。![bdc321e165680ff0.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/bdc321e165680ff0.png)

7. 在 **Component Tree** 中，点击 `TextView`。

8. 找到右侧的 **Attributes**。

9. 找到 **Declared Attributes** 部分。

10. 注意，**Declared Attributes** 部分中的 **text** 属性包含 **Hello World!**。![94a84633f74f4404.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/94a84633f74f4404.png)

11. 点击 **Hello World!** 文本所在的 **text** 属性。

12. 将其更改为 **Happy Birthday!**，然后按 **Enter** 键。如果您看到有关硬编码字符串的警告，暂时先不用担心。您将在下一个 Codelab 中解决该警告所指出的问题。

13. 注意，**Design View** 中的文本已经发生变化.....（这很酷，您可以立即看到自己所做的更改！）

14. 现在，您运行应用，就会显示 **Happy Birthday!**<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/233655306db5a589.png" alt="233655306db5a589.png" style="zoom: 25%;" />

干得真棒！您对 Android 应用做出了第一次更改。

### ④添加 TextView

在这一步，您将在应用左上角添加一个 `TextView` 来存放生日祝福。

![da933f736e60ee9b.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/da933f736e60ee9b.png)

**布局编辑器**左上角的 **Palette** 包含各种 `Views` 的列表（按类别整理），可供您添加到自己的应用中。

1. 查找 `TextView`。您在 **Common** 类别和 **Text** 类别中都能找到它。![e9d7cbe0218ad9a2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/e9d7cbe0218ad9a2.png)
2. 将 `TextView` 从 **Palette** 拖放到**布局编辑器**中设计图面的左上角。您不必做到精准到位，只需在左上角附近的位置放下即可。![bdc71e5cd4f88012.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/bdc71e5cd4f88012.gif)
3. 您会看到添加了一个 `TextView`，并且 **Component Tree** 中出现了一个红色的感叹号。
4. 将鼠标指针悬停在该感叹号上，您会看到一条警告消息，提示该视图未进行约束，在您运行应用时，视图会跳到其他位置。在接下来的这一步，您将解决此问题。![dec0dca3f753bc8c.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/dec0dca3f753bc8c.png)

### ⑤放置 TextView

如果是制作生日贺卡，您需要将 `TextView` 置于左上角附近，并且周围要留出一些空间。为了解决前文警告中指出的问题，您需要向 `TextView` 中添加一些约束条件，以告知应用如何放置该视图。约束条件用于指定在布局中放置 `View` 的方向和限制。

向顶部和左侧添加的约束条件将带有外边距。外边距用于指定 `View` 离它所在容器的边缘有多远。![ae54b1ca99784e08.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/ae54b1ca99784e08.png)

1. 在右侧的 **Attributes** 中，找到 **Layout** 部分中的 **Constraint Widget**。其中显示的方形代表您的视图。![ad04973e9a49e7db.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/ad04973e9a49e7db.png)

2. 点击方形顶部的 **+**。这会在文本视图的顶部与约束布局的上边缘之间添加约束条件。

3. 系统会显示一个带数字的字段，用于设置上外边距。该外边距是指从 `TextView` 到容器（即 `ConstraintLayout`）边缘的距离。显示的数字会因您放下 `TextView` 的位置而有所不同。在您设置上外边距时，Android Studio 还会在文本视图的顶部和 `ConstrainLayout` 的顶部之间自动添加约束条件。![eb0dc185dcac8a52.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/eb0dc185dcac8a52.png)

4. 将上外边距更改为 16。

   

   **注意**：界面中的外边距和其他距离的单位是密度无关像素 (dp)。它与厘米或英寸类似，但表示的是屏幕上的距离。Android 会针对每种设备将此值转换为相应的实际像素数。通常，1dp 大约是 1 英寸的 1/160，但对于某些设备，该尺寸可能会有所不同。

5. 对左外边距设置同样的数值。![a323a885bc39853d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/a323a885bc39853d.png)

6. 在 **text** 字段中输入您对朋友的生日祝福（例如：“Happy Birthday, Sam!”），然后按 **Enter** 键。![df20bb9a9fecaaeb.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/df20bb9a9fecaaeb.png)

7. 注意，**Design** 视图会随即更新，以呈现应用的外观。![da933f736e60ee9b.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/da933f736e60ee9b.png)

### ⑥添加并放置另一个 TextView

生日贺卡还需要在右下角附近显示另一行文本，您将在这一步中按照先前任务所采用的方法添加这行文本。您觉得这个 `TextView` 的外边距应该是多少呢？

1. 将一个新的 `TextView` 从 **Palette** 拖放到布局编辑器中应用视图的右下角附近。![80225484f67a3fc4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/80225484f67a3fc4.png)
2. 将右外边距设为 16。
3. 将下外边距设为 16。![279401c5156ba23f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/279401c5156ba23f.png)
4. 在 **Attributes** 中，将 **text** 属性设为您的贺卡签名，例如“From Emma”。
5. 运行应用。您应该会在左上角看到您的生日祝福，并在右下角看到您的签名。![f547c1b45045984a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/f547c1b45045984a.png)

祝贺您！您已经在应用中添加并放置了一些界面元素。

### ⑦. 向文本添加样式

您已将文本添加到界面中，但它看起来和最终应用还不太一样。在此任务中，您将了解如何更改大小、文本颜色以及影响 `TextView` 外观的其他属性。此外，您还可以尝试使用不同的字体。

1. 点击 **Component Tree** 中的第一个 `TextView`，然后找到 **Attributes** 窗口的 **Common Attributes** 部分。您可能需要向下滚动鼠标才能找到该部分。

2. 注意各种属性，包括 **fontFamily**、**textSize** 和 **textColor**。![623877d1c739fd8b.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/623877d1c739fd8b.png)

3. 查找 **textAppearance**。

4. 如果 **textAppearance** 未展开，请点击向下三角形。

5. 将 **textSize** 设为 **36sp**。![fc28815db05fbb5f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/fc28815db05fbb5f.png)

   **注意**：就像 dp 是屏幕上距离的度量单位一样，**sp** 是字体大小的度量单位。Android 应用中的界面元素使用两种不同的度量单位：一种是您之前为布局使用的密度无关像素 (**dp**)，另一种是在设置字体大小时使用的可缩放像素 (**sp**)。默认情况下，sp 和 dp 大小相同，但前者的大小会根据用户的首选文本大小进行调整。

6. 注意**布局编辑器**中出现的变化。![4845b7d5265f0417.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/4845b7d5265f0417.png)

7. 将 **fontFamily** 更改为 **casual**。

8. 尝试使用一些不同的字体，看看它们各自的呈现效果。您还可以通过列表底部的 **More Fonts...** 选择其他字体。

9. 尝试完不同的字体后，请将 **fontFamily** 设为 **sans-serif-light**。

10. 点击 **textColor** 属性的编辑框，然后开始输入 **black**。请注意，在您输入的过程中，Android Studio 会显示包含到目前为止您已输入文字的颜色的列表。![a615955683853ace.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/a615955683853ace.png)

11. 从颜色列表中选择 **@android:color/black**，然后按 **Enter** 键。

12. 在包含签名的 `TextView` 中，将 **textSize**、**textColor** 和 **fontFamily** 更改为匹配的值。

13. 运行应用并查看结果。![f22135316709f0f7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app/img/f22135316709f0f7.png)

恭喜，您已完成创建 Birthday Card 应用的前几步！

### ⑧ 小结

- **布局编辑器**可帮助您创建 Android 应用的界面。
- 您在应用屏幕上看到的所有内容几乎均属于 `View`。
- `TextView` 是在应用中显示文本的界面元素。
- `ConstraintLayout` 是存放其他界面元素的容器。
- 在 `ConstraintLayout` 中，必须为 `Views` 设置水平和垂直方向的约束条件。
- 放置 `View` 的一种方式是使用外边距。
- 外边距表示 `View` 离它所处容器的边缘有多远。
- 您可以在 `TextView` 上设置字体、文字大小和颜色等属性。



## 5 向 Android 应用添加图片

### ①为项目添加图片

在此任务中，您将从互联网上下载一张图片，然后将其添加到您的 Happy Birthday 应用中。

1. 点击[此处](https://github.com/google-developer-training/android-basics-kotlin-birthday-card-with-image-app-solution/blob/master/androidparty.png)，以在 GitHub 上查看生日贺卡的图片。
2. 点击右侧的 **Download**（下载）按钮，界面上随即会显示该图片。![292d671821b59699.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/292d671821b59699.png)
3. 右键点击该图片，并在计算机中将该文件另存为 **androidparty.png**。请记下保存位置（例如：**下载**文件夹）。
4. 在 Android Studio 中，在菜单中依次点击 **View > Tool Windows > Resource Manager**，或者点击 **Project** 窗口左侧的 **Resource Manager** 标签页。
5. 点击 **Resource Manager** 下方的 **+**，然后选择 **Import Drawables**。系统随即会打开一个文件浏览器。![9e14eac71fe055b7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/9e14eac71fe055b7.png)
6. 在文件浏览器中，找到已下载的图片文件，然后点击 **Open**。
7. 点击 **Next**。Android Studio 会向您显示该图片的预览。
8. 点击 **Import**。
9. 如果图片导入成功，Android Studio 就会将此图片添加到 **Drawable** 列表中。此列表包含该应用的所有图片和图标。现在，您可以在应用中使用这张图片了。![d96dbcb7fd1df4de.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/d96dbcb7fd1df4de.png)
10. 依次点击菜单中的 **View > Tool Windows > Project** 或最左侧的 **Project** 标签页，切换回项目视图。
11. 展开 **app > res > drawable**，确认图片位于应用的 **drawable** 文件夹中。![143d88acc8f0c5da.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/143d88acc8f0c5da.png)



### ②添加 ImageView

若要在应用中显示图片，需要有一个显示位置。就像使用 `TextView` 显示文本一样，您可以使用 `ImageView` 来显示图片。

在此任务中，您将向应用添加 `ImageView`，并将其图片设为您下载的纸杯蛋糕图片。然后，您将放置该图片并调整它的尺寸，使其填满整个屏幕。

- **添加 ImageView 并设置其图片**

1. 在 **Project** 窗口中，打开 **activity_main.xml**（依次点击 **app > res > layout > activity_main.xml**）。

**提示**：如果您没有看到**布局编辑器**，请点击右上角的 **Design** 模式按钮。![469c3e31c689dc5.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/469c3e31c689dc5.png)

1. 在**布局编辑器**中，转到 **Palette** 并将 `ImageView` 拖动到应用上，将其放在靠近中心的位置，且不与任何文本重叠

此时，系统会打开 **Pick a Resource** 对话框。此对话框列出了可供您应用使用的所有图片资源。请注意生日图片列于 **Drawable** 标签页下。可绘制资源是图形的一般概念，是指可在屏幕上绘制的图形，其中包括图片、位图、图标以及许多其他类型的绘图资源。

1. 在 **Pick a Resource** 对话框中，从 **Drawable** 列表里找到蛋糕图片。
2. 点击该图片，然后点击 **OK**。![c901de3471f4fc5.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/c901de3471f4fc5.gif)

系统随即会将该图片添加到应用中，但放置的位置可能不对，并且不会让图片填满屏幕。在接下来的这一步，您将解决此问题。



### ③放置 ImageView 并调整其大小

1. 在**布局编辑器**中点击并拖动 `ImageView`。在拖动时，您会看到 **Design** 视图中应用屏幕的周围会显示粉色矩形边框。粉色矩形边框表示放置 `ImageView` 的屏幕边界。
2. 拖动 `ImageView`，使其左右边缘与粉色矩形对齐。当您靠近时，Android Studio 便会让该图片“贴靠”边缘。（然后，您需要贴靠顶部和底部边缘。）![f4efafb08c24ef9e.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/f4efafb08c24ef9e.gif)

`ConstraintLayout` 中的 `Views` 需要具有水平和垂直约束条件，以便告知 `ConstraintLayout` 如何放置这些视图。接下来，您将添加这些约束条件。

**注意**：在**布局编辑器**环境中，约束条件表示某个视图与其他视图、父布局或隐形引导线之间的连接或对齐方式。例如，视图可以被约束为与其容器边缘保持一定距离，或始终位于另一个视图的右侧，或始终作为容器内的顶部视图。

1. 将指针悬停在 `ImageView` 轮廓顶部的圆圈上，这个圆圈便会与另一个圆圈一起突出显示。

2. 如果将圆圈拖向应用屏幕的顶部，那么在您拖动时，会有一个箭头将该圆圈连接到指针。请进行拖动，直至贴靠到屏幕顶部。这样，您就在 `ImageView` 的顶部与 `ConstraintLayout` 的顶部之间添加了约束条件。![bbfeb4b1d884197d.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/bbfeb4b1d884197d.gif)

3. 在 `ImageView` 的底部和 `ConstraintLayout` 的底部之间添加约束条件。有可能会因为距离边缘太近而无法像对顶部那样进行拖动。在这种情况下，您可以点击 **Attributes** 窗口中 **Constraint Widget** 底部的 **+**，添加约束条件。请务必将外边距设为 0。![35969560df456b8c.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/35969560df456b8c.png)

   

   **提示**：您在屏幕上添加的 `Views` 越多，添加约束条件就会变得越困难。如果您为错误的 `View` 添加了约束条件，可以使用 `Control+Z`（在 Mac 上，使用 `Command+Z`）进行撤消。或者，右键点击相应的 `View`，在弹出的菜单中选择 **Clear Constraints of Selection**，从而移除针对该 `View` 的所有约束条件。![6b5fb1f3c11226d3.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/6b5fb1f3c11226d3.png)

4. 在 **Attributes** 窗格中，使用 **Constraint Widget** 将左右两侧的外边距设为 0。系统会自动创建该方向的约束条件。![4ae2538135af71db.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/4ae2538135af71db.png)

现在，图片已经居中，但尚未占据整个屏幕。在接下来的步骤中，您将解决此问题。

1. 在 **Constraints** 部分的 **Constraint Widget** 下，将 **layout_width** 设为 **0dp (match constraint)**。0dp 是一种简写形式，用于指示 Android Studio 对 `ImageView` 的宽度使用匹配约束条件。“匹配约束条件”意味着，由于您刚刚添加的约束条件，这会让它与 `ConstraintLayout` 一样宽，所有外边距都会被减去。![78e478f7e1d5314d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/78e478f7e1d5314d.png)

2. 将 **layout_height** 设为 **0dp (match constraint)**。由于您添加的约束条件，这会让 `ImageView` 与 `ConstraintLayout` 一样高，所有外边距都会被减去。![fe1a6139a3704e88.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/fe1a6139a3704e88.png)

3. `ImageView` 与应用屏幕一样高、一样宽，但图片位于 `ImageView` 的中心，并且图片的上方和下方还有很多空白区域。这看起来不太好看，因此请调整 `ImageView` 的 **scaleType**，告知系统如何调整图片的大小和对齐方式。如需详细了解 `ScaleType`，请参阅[开发者参考指南](https://developer.android.com/reference/kotlin/android/widget/ImageView.ScaleType)。现在，应用应如下所示。![ad6e5c3b6b5a920e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/ad6e5c3b6b5a920e.png)

4. 找到 **scaleType** 属性。您可能需要向下滚动或搜索该属性。尝试为 **scaleType** 设置不同的值，看看不同值的效果。

   

   **提示**：若要在所有属性的列表中找到某个属性，请点击“Attributes”右侧的放大镜图标，然后开始输入该属性的名称。Android Studio 只会显示包含所输入字符串的属性。

   ![6349e6a522fda9ea.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/6349e6a522fda9ea.png)

   ![1e116f4ea013be17.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/1e116f4ea013be17.png)

   

5. 完成后，请将 **scaleType** 设为 **centerCrop**。这样一来，图片将填满整个屏幕，而不会变形。

![4f662df54ecd9119.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/4f662df54ecd9119.png)

现在，蛋糕图片应该会填满整个屏幕，如下所示。

![63f0cf7d9e300b8a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/63f0cf7d9e300b8a.png)

但现在您就看不到生日祝福和签名了。在接下来的这一步，您将解决此问题。



### ④将 ImageView 移到文本后面

让 `ImageView` 填满整个屏幕后，您便无法再看到文本。这是因为图片现在盖住了文本。因此，界面元素的顺序很重要。您先添加了 `TextViews`，然后添加了 `ImageView`，这就意味着图片视图会位于顶部。当您向布局添加视图后，这些视图将添加到视图列表的末尾，并会按照它们在列表中的顺序进行绘制。`ImageView` 被添加到 `ConstraintLayout` 中 `Views` 列表的末尾，这意味着这个视图会在最后绘制，并且是在 `TextViews` 的上面进行绘制。若要解决此问题，您需要更改各个视图的顺序，将 `ImageView` 移至列表开头。这样，系统就会首先绘制该视图。

![19a049a18ff68413.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/19a049a18ff68413.gif)

1. 在 **Component Tree** 中，点击 `ImageView`，将它拖动到 `TextViews` 的上面，`ConstraintLayout` 的正下方。系统会显示一个带三角形的蓝色线条，指示 `ImageView` 的目标位置。请将 `ImageView` 拖至 `ConstraintLayout` 的正下方。![f54176e6fe76783c.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-birthday-card-app-image/img/f54176e6fe76783c.gif)

现在，`ImageView` 应该位于 `ConstraintLayout` 下方列表的首位，后面是 `TextViews`。您就应该能够看到“Happy Birthday, Sam!”和“From Emma.”这两条文本了。（请暂时忽略有关缺少内容说明的警告。）

祝贺您！您已经为自己的 Android 应用添加了图片！

### ⑤小结

- Android Studio 中的 **Resource Manager** 可帮助您添加和整理图片及其他资源。
- `ImageView` 是在应用中显示图片的界面元素。
- `ImageViews` 应包含内容说明，以便提高应用的无障碍性。
- 向用户显示的文本（例如生日祝福）应提取到字符串资源中，以便让应用更容易翻译成其他语言。



## 6 Kotlin 中的类和对象实例



**注意**：

- 与使用 Kotlin 中的 `fun` 关键字创建新函数类似，请使用 `class` 关键字创建新类。
- 您可以为 `class` 选择任何名称，但如果名称能指示类所表示的对象，将会很有帮助。按照惯例，类名称采用大驼峰式命名法（也称为驼峰式大小写）编写。例如：`Car`、`ParkingMeter` 和 `CustomerRecord` 都是有效的类名称，您可以猜出它们所表示的对象。

```
fun main() {
    val myFirstDice = Dice(6)
    println("Your ${myFirstDice.numSides} sided dice rolled ${myFirstDice.roll()}!")

    val mySecondDice = Dice(20)
    println("Your ${mySecondDice.numSides} sided dice rolled ${mySecondDice.roll()}!")
}

class Dice (val numSides: Int) {

    fun roll(): Int {
        return (1..numSides).random()
    }
}
```

**小结**

- 对 `IntRange` 调用 `random()` 函数以生成随机数字：`(1..6).random()`
- 类就像是对象的蓝图。它们可以具有作为变量和函数实现的属性和行为。
- 类的实例代表对象，通常是实物，如骰子。可以调用针对对象的操作并更改其属性。
- 创建实例时，可以向类提供值。例如：创建 `class Dice(val numSides: Int)`，然后通过 `Dice(6)` 创建实例。
- 函数可以返回一些内容。可以在函数定义中指定要返回的数据类型，并在函数正文中使用 `return` 语句来返回内容。例如：`fun example(): Int { return 5 }`

**参考**

- [《使用 Kotlin 进行 Android 开发的基础知识》相关词汇](https://developer.android.com/courses/android-basics-kotlin/android-basics-kotlin-vocab)
- [随机数字生成（维基百科）](https://en.wikipedia.org/wiki/Random_number_generation#Practical_applications_and_uses)
- [设计 120 面骰子时面临的巨大难题](https://www.wired.com/2016/05/mathematical-challenge-of-designing-the-worlds-most-complex-120-sided-dice/)
- [Kotlin 中的类](https://play.kotlinlang.org/byExample/01_introduction/05_Classes)
- [Kotlin 中的函数声明](https://kotlinlang.org/docs/reference/functions.html#function-declarations)
- [从函数返回值](https://kotlinlang.org/docs/reference/basic-syntax.html#defining-functions)

## 7 创建交互式 Dice Roller 应用

### ①Activity 简介

`Activity` 提供窗口供应用在其中绘制界面。通常，`Activity` 会占用正在运行的应用的整个屏幕。每个应用都有一个或多个 Activity。顶级 Activity 或第一个 Activity 通常称为 `MainActivity`，由项目模板提供。例如，当用户滚动浏览设备上的应用列表并点按“Dice Roller”应用图标时，Android 系统会启动该应用的 `MainActivity`。

在 `MainActivity` 代码中，您需要提供 `Activity` 布局以及用户应如何与其交互的详细信息。

- 在 Birthday Card 应用中，有一个 `Activity` 用于显示生日消息和图片。
- 在 Dice Roller 应用中，有一个 `Activity` 用于显示刚构建的 `TextView` 和 `Button` 布局。

对于更复杂的应用，可能会设置多个屏幕和多个 `Activity`。每个 `Activity` 都有特定用途。

例如，在“Photo Gallery”应用中，您可以使用一个 `Activity` 来显示照片网格，一个 `Activity` 来查看单张照片，以及另一个 `Activity` 来修改单张照片。

![28acaa7127236555.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/28acaa7127236555.png)

**打开 MainActivity.kt 文件**

您将添加代码以响应 `MainActivity` 中的按钮点按。如需正确执行此操作，您需要详细了解应用中已有的 `MainActivity` 代码。

1. 导航到 `MainActivity.kt` 文件并打开文件 (**app > java > com.example.diceroller > MainActivity.kt**)。您应该会看到以下内容：如果看到 `import...`，请点击 `...` 以展开导入。

```
package com.example.diceroller

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle

class MainActivity : AppCompatActivity() {

   override fun onCreate(savedInstanceState: Bundle?) {
       super.onCreate(savedInstanceState)
       setContentView(R.layout.activity_main)
   }
}
```

您无需理解上述代码的每个单词，但需要大致了解其功能。您对 Android 代码的使用越多，您对代码就会越熟悉，也就对其越了解。

1. 查看 `MainActivity` 类的 Kotlin 代码，由关键字 `class` 和名称标识。

```
class MainActivity : AppCompatActivity() {
    ...
}
```

1. 请注意，您的 `MainActivity` 中没有 `main()` 函数。

之前，您已了解每个 Kotlin 程序都必须具有 `main()` 函数。Android 应用的工作方式有所不同。当您第一次打开应用时，Android 系统会调用 `MainActivity` 的 `onCreate()` 方法，而不会调用 `main()` 函数。

1. 查找 `onCreate()` 方法，该方法类似于以下代码。

```
   override fun onCreate(savedInstanceState: Bundle?) {       super.onCreate(savedInstanceState)       setContentView(R.layout.activity_main)   }
```

您将在后面的 Codelab 中了解 `override`（目前不用操心）。`onCreate()` 方法的其余部分使用导入中的代码设置 `MainActivity`，并通过 `setContentView()` 设置起始布局。

1. 请注意以 `import` 开头的行。

Android 提供了许多类的框架，可帮助您更轻松地编写 Android 应用，但需要准确了解您所指的具体类。您可以使用 `import` 语句指定要在代码中使用的框架中的类。例如，`Button` 类在 `android.widget.Button` 中定义。

#### **启用自动导入**

使用更多类时，记住添加 `import` 语句将会变得很繁琐。幸运的是，当您使用其他程序提供的类时，Android Studio 可以帮助您选择正确的导入。在此步骤中，您将对 Android Studio 进行配置，使其尽可能自动添加导入，并自动从您的代码中移除未使用的导入。

1. 在 Android Studio 中，如果使用 macOS，请依次转到 **File > New Project Settings > Preferences for New Project** 以打开设置。在 Windows 中，依次转到 **File > Other Settings > Setting New Project...**。
2. 展开 **Other Settings > Auto Import**。在 **Java** 和 **Kotlin** 部分中，确保选中 **Add unambiguous imports on the fly** 和 **Optimize imports on the fly (for current project)**。请注意，每个部分中有两个复选框。![79fe20153135b22e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/79fe20153135b22e.png) **明确导入**设置会指示 Android Studio 自动添加 import 语句，只要它可以确定要使用的语句即可。**优化导入**设置会指示 Android Studio 移除您的代码未使用的任何导入。
3. 按 **OK**，保存更改并关闭设置。



### ②将 Button 设置为可交互

**点击 Button 时显示消息**

在此步骤中，您将指定点击该 Button 时，屏幕底部会出现一条简短的消息。

![13e87361209e5460.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/13e87361209e5460.png)

1. 在调用 `setContentView()` 后，将以下代码添加到 `onCreate()` 方法中。`findViewById()` 方法在布局中找到 `Button`。`R.id.button` 是 `Button` 的资源 ID，该 ID 是 Button 的唯一标识符。代码将 `Button` 对象的引用保存到名为 `rollButton` 的变量中，而不是保存 `Button` 对象本身。

```
val rollButton: Button = findViewById(R.id.button)
```

**注意**：Android 会自动为应用中的资源分配 ID 号。例如，**Roll** 按钮具有资源 ID，按钮文字的字符串也具有资源 ID。资源 ID 的格式为 `R.<type>.<name>`；例如 `R.string.roll`。对于 `View` ID，`<type>` 为 `id`，例如 `R.id.button`。

代码将对 `Button` 对象的引用保存在名为 `rollButton` 的变量中，而不是 `Button` 对象本身。

**重要说明**：在为变量分配对象时，Kotlin 不会每次都复制整个对象，而是保存对象的引用。您可以将引用视为国民身份证号码；号码代表某一人，但并非人物本身。复制号码时不会复制对应的人。

`onCreate()` 方法现在应如下所示：

```
override fun onCreate(savedInstanceState: Bundle?) {   super.onCreate(savedInstanceState)   setContentView(R.layout.activity_main)   val rollButton: Button = findViewById(R.id.button)}
```

验证 Android Studio 是否自动为 `Button` 添加了 `import` 语句。请注意，现在有 3 个 import 语句，第三个语句是自动添加的。

```
import androidx.appcompat.app.AppCompatActivityimport android.os.Bundleimport android.widget.Button
```

**注意**：如果未能启用自动导入功能，`Button` 将以红色突出显示。您可以手动添加正确的导入操作，方法是将文本光标置于 `Button` 内，然后按 `Alt+Enter`（在 Mac 上，按 `Option+Enter`）。

接下来，您需要将代码与 `Button` 相关联，以便在点按 `Button` 时执行代码。点击监听器是一些代码，用于在发生点按或点击时执行相应操作。此处的点击监听器用于监听用户点击 `Button` 的操作。

使用 `rollButton` 对象，并调用 `setOnClickListener()` 方法为其设置点击监听器。实际上，在方法名称后面您将使用大括号，而不在方法名称后面使用圆括号。这是用于声明 [Lambda](https://kotlinlang.org/docs/reference/lambdas.html) 的特殊语法，在未来的 Codelab 中可了解详情。

当前您需要注意的是，在大括号内，给出了在点按按钮时应执行的操作的说明。您可以让应用显示消息框，其中显示有关下一步的简短消息。

```
rollButton.setOnClickListener {}
```

在输入过程中，Android Studio 可能会显示多个建议。在本例中，请选择 **setOnClickListener {...}** 选项。

![814b3618b46e2ad5.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/814b3618b46e2ad5.png)

在大括号中，您可以说明点按按钮时应执行的操作。现在，您可以让应用显示 [`Toast`](https://developer.android.com/reference/android/widget/Toast)，这是一条向用户显示的简短消息。

通过调用 `Toast.makeText()` 创建包含文字 `"Dice Rolled!"` 的 `Toast`。

```
val toast = Toast.makeText(this, "Dice Rolled!", Toast.LENGTH_SHORT)
```

1. 然后，通过调用 `show()` 方法告知 `Toast` 自行显示。

```
toast.show()
```

更新后的 `MainActivity` 类如下所示；`package` 和 `import` 语句仍位于文件顶部：

```
class MainActivity : AppCompatActivity() {   override fun onCreate(savedInstanceState: Bundle?) {       super.onCreate(savedInstanceState)       setContentView(R.layout.activity_main)       val rollButton: Button = findViewById(R.id.button)       rollButton.setOnClickListener {           val toast = Toast.makeText(this, "Dice Rolled!", Toast.LENGTH_SHORT)           toast.show()       }   }}
```

您可以将点击监听器中的两行合并为一行，而不使用变量。该模式一种常见模式，您在其他代码中也可以找到。

```
Toast.makeText(this, "Dice Rolled!", Toast.LENGTH_SHORT).show()
```

运行该应用，然后点击 **Roll** 按钮。消息框消息将在屏幕底部弹出，不久后就会消失。

![fe4a03053b25cb7a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/fe4a03053b25cb7a.png)

太棒了！点击按钮后，消息就会弹出！这是您第一次为 Android 编写 Kotlin 代码！



**点击 Button 时更新 TextView**

您需要编写代码以在用户点击 **Roll** 按钮时更新屏幕上的 `TextView`，而不是显示临时 `Toast` 消息。

1. 返回到 `activity_main.xml` (**app > res > layout >activity_main.xml**)

2. 点击 `TextView`。

3. 请注意，**id** 为 **textView**。![d0834ec93ef00a25.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/d0834ec93ef00a25.png)

4. 打开 `MainActivity.kt` (**app > java > com.example.diceroller > MainActivity.kt**)

5. 删除用于创建和显示 `Toast` 的代码行。

   ```
   rollButton.setOnClickListener {}
   ```

6. 在其中创建一个名为 `resultTextView` 的新变量来存储 `TextView`。

7. 使用 `findViewById()` 以在布局中使用 textView 的 ID 查找 `textView`，并存储对其的引用。

   ```
   val resultTextView: TextView = findViewById(R.id.textView)
   ```

   

8. 将 `resultTextView` 上的文字设置为带引号的“6”。

```
resultTextView.text = "6"
```

这与在 **Attributes** 中设置 **text** 类似，但它现已在代码中，因此文字必须位于双引号中。明确进行此设置意味着，`TextView` 当前始终显示 6。您将添加代码，以在下一个任务中掷骰子并显示不同的值。

`MainActivity` 类的内容应如下所示：

```
class MainActivity : AppCompatActivity() {   override fun onCreate(savedInstanceState: Bundle?) {       super.onCreate(savedInstanceState)       setContentView(R.layout.activity_main)       val rollButton: Button = findViewById(R.id.button)       rollButton.setOnClickListener {           val resultTextView: TextView = findViewById(R.id.textView)           resultTextView.text = "6"       }   }}
```

运行应用。点击按钮。它应将 `TextView` 更新为“6”。

![6a908f7aa5226e04.png](https://developer.android.com/codelabs/basic-android-kotlin-training-create-dice-roller-app-with-button/img/6a908f7aa5226e04.png)



### ③小结

- 使用**布局编辑器**在 Android 应用中添加 `Button`。
- 修改 `MainActivity.kt` 类，以便向应用添加交互行为。
- 弹出 `Toast` 消息作为临时解决方案，可验证您的操作是否正确。
- 使用 `setOnClickListener()` 为 `Button` 设置点击监听器，以添加在用户点击 `Button` 时的行为。
- 在应用运行时，您可以通过对布局中的 `TextView`、`Button` 或其他界面元素调用方法来更新屏幕。
- 对您的代码添加注释，帮助阅读代码的其他人了解您的方法。
- 重新格式化代码并清理代码。(如下)

1. 在 `MainActivity.kt` 类中，在 Windows 中使用键盘快捷键 `Control+A`（或 Mac 上的 `Command+A`）选择文件中的所有文本。或者，您也可以转到 Android Studio 中的菜单 (**Edit > Select All**) 完成相应操作。
2. 选择文件中的所有文本后，转到 Android Studio 菜单的 **Code > Reformat Code**，或使用键盘快捷键 `Ctrl+Alt+L`（在 Mac 上，则使用 `Command+Option+L`）。



## 8 在 Kotlin 中添加条件行为

`>` 符号是用于比较两个值的运算符，它会比较第一个值是否大于第二个值，并返回 `true` 或 `false` 结果。其他常见运算符包括：`<`（表示小于）、`==`（表示等于）、`>=`（表示大于等于）和 `<=`（表示小于等于）。

请注意 `if` 语句的一般格式：

- 以 `if` 关键字开头。
- 后跟一对圆括号 `()`。括号内包含条件。该条件是结果可以为 `true` 或 `false` 的任何条件。例如，一个数字是否大于另一个数字。
- 再后跟一对大括号 `{}`。在大括号内放置条件结果为 `true` 时要执行的代码。

```
if (condition-is-true) {    execute-this-code}
```

**提示**：在 if-else 代码块中，只能有一个 `if` 语句和一个 `else` 语句；但在两者之间，可以有任意数量的 `else if` 语句。



**true 和 false 值的 Boolean 数据类型**：

- 程序测试是否满足条件的过程称为“评估条件”。如果满足条件，评估条件结果为 `true`，如果不满足条件，结果为 `false`。开发者还会这样表达：“条件评估为 `true`”或“条件评估为 `false`”。
- 条件只能评估为 `true` 或 `false`。
- 就像整数的数据类型为 `Int`、范围为 `IntRange` 一样，`true` 和 `false` 也有数据类型，称为 `Boolean`。

**控制流**

可以看出，根据上面的 if-else 语句，代码将按照条件的控制执行或向下继续运行。您使用这些条件来引导程序执行的过程称为程序的“控制流”。

- 假设掷骰子的 `num` 是 3。程序会检查第一个条件 (num > 4)。该结果为 false，因此程序会检查下一个条件 (num == 4)，其结果同样为 false。然后，程序会执行 else 语句的代码，这是最后一个选项。
- 如果掷骰子的 num 为 6，那么第一个条件 (num > 4) 的结果为 true。程序会输出 `"The variable is greater than 4"` 消息。由于该条件结果为 true，因此无需检查其余条件，程序运行到 if-else 语句便已结束。
- 使用 else + if 组合可以添加替代条件。



**使用 when 语句**

针对许多不同结果（或情况）进行测试在编程中很常见。有时，可能的结果非常多。例如，如果是掷 12 面的骰子，获得成功结果与最后的 `else` 之间会有 11 个 `else if` 语句。为了使此类语句更易于读写，从而帮助避免错误，Kotlin 提供了 `when` 语句。

使用 `when` 语句。`when` 语句以关键字 `when` 开头，后跟括号 `()`。括号内放置要测试的值。后跟大括号 `{}`，这样可以针对不同的条件执行代码。

```
fun main() {    val myFirstDice = Dice(6)    val rollResult = myFirstDice.roll()    val luckyNumber = 4    when (rollResult) {        luckyNumber -> println("You won!")        1 -> println("So sorry! You rolled a 1. Try again!")        2 -> println("Sadly, you rolled a 2. Try again!")        3 -> println("Unfortunately, you rolled a 3. Try again!")        5 -> println("Don't cry! You rolled a 5. Try again!")        6 -> println("Apologies! you rolled a 6. Try again!")   }}class Dice(val numSides: Int) {    fun roll(): Int {        return (1..numSides).random()    }}
```

与之前一样，首先测试 `rollResult` 是否与 `luckyNumber` 相同。

1. 在 `when` 语句的大括号 `{}` 内，添加一个针对 `luckyNumber` 测试 `rollResult` 的语句，如果二者相同，就输出获胜消息。该语句如下所示：

```
luckyNumber -> println("You win!")
```

这意味着：

- 您首先放入要与 `rollResult` 比较的值。即，`luckyNumber`。
- 后跟箭头 (`->`)。
- 然后添加存在匹配项时要执行的操作。

这可以理解为，“如果 `rollResult` 为 `luckyNumber`，就输出 `"You win!"` 消息。”



### 小结

- 使用 `if` 语句设置用于执行某些指令的条件。例如，如果用户掷出幸运数字，就输出获胜消息。
- `Boolean` 数据类型的值为 `true` 和 `false`，可用于做出决策。
- 使用大于 (`>`)、小于 (`<`) 和等于 (`==`) 等运算符可比较数值。
- 使用 `else if` 语句链可设置多个条件。例如，针对每种可能的掷骰结果输出不同的消息。
- 在条件链末尾使用 `else` 语句来捕获您未明确涵盖的任何情况。如果您涵盖掷 6 面骰子的情况，`else` 语句将捕获使用 8 面骰子时的数字 7 和 8。
- 使用 `when` 语句作为基于比较数值的一种紧凑的代码执行方法。

**if-else 的常规形式**：

```
if (`*`condition-is-true`*`) {*`execute-this-code`*} else if (`*`condition-is-true`*`) {*`execute-this-code`*} else {*`execute-this-code`*}
```

**when 语句**：

```
when (`***`variable`\***`) {`matches-value -&gt;` *`execute-this-code`*`matches-value -&gt;` *`execute-this-code`*`...`}
```



使用 [`setImageResource()`](https://developer.android.com/reference/android/widget/ImageView#setImageResource(int)) 更改 `ImageView` 中显示的图片

使用 `if / else` 表达式或 `when` 表达式等控制流语句来处理应用中的不同情况，例如，在不同情况下显示不同的图片。



# 二 布局

## 1  Kotlin 中的类和继承

### ①什么是类层次结构？

人们很自然地会将具有相似属性和行为的内容划分为组，甚至会在这些组之间形成某种类型的层次结构。例如，您可以使用比较宽泛的类别（例如蔬菜），在该类别内，您可以设置更具体的类型（例如[豆类](https://en.wikipedia.org/wiki/Legume)）。在豆类中，您可以划分更加具体的类型，例如豌豆、黄豆、扁豆、鹰嘴豆和大豆。

这可以表示为层次结构，因为豆类包含或继承了蔬菜的所有属性（例如，它们属于植物，且可以食用）。同样地，豌豆、黄豆和扁豆均具有豆类的属性，同时也具有自己独特的属性。

我们来看看，如何用编程术语表示这种关系。如果您将 `Vegetable` 作为 Kotlin 中的一个类，您可以创建 `Legume` 作为 `Vegetable` 类的子级或子类。这意味着，`Vegetable` 类的所有属性和方法均会被 `Legume` 类继承（即，这些属性和方法同样可用于后者）。

您可以在类层次结构示意图中表示这种关系，如下所示。您可以以 `Legume` 类父级或父类的形式引用 `Vegetable`。

![75d159d370c31d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-classes-and-inheritance/img/75d159d370c31d.png)

您可以通过创建 `Legume` 的子类（例如 `Lentil` 和 `Chickpea`）继续扩展类层次结构。这会使 `Legume` 既是 `Vegetable` 的子级或子类，同时也是 `Lentil` 和 `Chickpea` 的父级或父类。`Vegetable` 是此层次结构的根类或*顶级类（*也称为基类）。

![9b13da1fe9fadb3f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-classes-and-inheritance/img/9b13da1fe9fadb3f.png)

**注意**：术语总结

下面总结了此 Codelab 中使用的术语，及其在 Kotlin 类语境下的含义。

- **类层次结构**。一种将类按父级和子级层次结构进行整理的排列方式。层次结构示意图通常会以父级在上、子级在下的方式绘制。
- **子级或子类**。层次结构中位于其他类下方的任意类。
- **父级、父类或基类**。具有一个或多个子类的任意类。
- **根类或顶级类**。位于类层次结构顶部（或根部）的类。
- **继承**。子类包含（或继承）其父类的所有属性和方法的情况。借助继承，您可以共享和重复使用代码，从而使程序更易于理解和维护。

### ②Android 类中的继承

正如您在之前的 Codelab 中所做的那样，虽然您可以在不使用类的情况下编写 Kotlin 代码，但 Android  的很多部分都是以类的形式向您提供的，包括 activity、视图和视图组。因此，理解类层次结构是 Android  应用开发的基础，并且有助于您利用 Android 框架提供的诸多功能。

例如，Android 中有一个 [`View`](https://developer.android.com/reference/kotlin/android/view/View) 类，它表示屏幕上的一个矩形区域，并且负责绘制和事件处理。[`TextView`](https://developer.android.com/reference/kotlin/android/widget/TextView) 类是 `View` 类的子类，这意味着 `TextView` 会继承 `View` 类的所有属性和函数，并会添加特定的逻辑，以向用户显示文本。

![2fbc991a6afe5299.png](https://developer.android.com/codelabs/basic-android-kotlin-training-classes-and-inheritance/img/2fbc991a6afe5299.png)

再往下一级，[`EditText`](https://developer.android.com/reference/kotlin/android/widget/EditText) 和 [`Button`](https://developer.android.com/reference/kotlin/android/widget/Button) 类是 `TextView` 类的子级。它们会继承 `TextView` 和 `View` 类的所有属性和方法，并会添加自己的特定逻辑。例如，`EditText` 添加了自己的功能，能够修改屏幕上的文本。

您不必从 `View` 和 `TextView` 类中复制所有逻辑，并将其粘贴到 `EditText` 类中，`EditText` 可以直接子类化 `TextView` 类，后者再子类化 `View` 类。然后，`EditText` 类中的代码便可专注于使此界面组件不同于其他视图的其他方面。

在 developer.android.com 网站上有关 Android 类的[文档页面顶部](https://developer.android.com/reference/kotlin/android/widget/Button)，您可以看到类层次结构示意图。如果您在层次结构顶部看到 `kotlin.Any`，这是因为在 Kotlin 中，所有类都具有一个通用父类 Any。请点击[此处](https://kotlinlang.org/docs/reference/classes.html#inheritance)了解详情。

![57cd75bd819126bb.png](https://developer.android.com/codelabs/basic-android-kotlin-training-classes-and-inheritance/img/57cd75bd819126bb.png)

如您所见，学习利用类之间的继承关系，可使您的代码更易于编写、重复使用、阅读和测试。

### ③创建基类

任何类都可以是类层次结构的基类或其他类的父类。

“抽象”类是一种无法实例化的类，因为它没有完全实现。您可以将其视为一个草图。草图包含关于某些事的想法和计划，但其中的信息通常并不足以完成构建。您可以使用草图（抽象类）来创建一个蓝图（类），然后基于后者构建实际的对象实例。

创建父类的一个常见好处是，能够包含其所有子类通用的属性和函数。如果属性的值及函数的实现情况未知，则可以将其作为抽象类。例如，`Vegetables` 中有许多所有蔬菜通用的属性，但您无法为某种非特定的蔬菜创建实例，因为您不知道关于它的某些信息，例如其形状或颜色。因此，`Vegetable` 是一个抽象类，每种蔬菜的具体细节交由子类来确定。

抽象类的声明以 `abstract` 关键字开头。

```
abstract class Dweling(private var residents: Int){    abstract val buildingMaterial: String    abstract val capacity: Int    fun hasRoom(): Boolean {        return residents < capacity    }}
```

### ④创建子类

通过在 `SquareCabin` 类名称后添加一个冒号 (`:`)，后跟用于初始化父级 `Dwelling` 类的调用，表明此继承关系。不要忘记在 `Dwelling` 类名称后添加圆括号。

```
class SquareCabin : Dwelling()
```

如果是从父类扩展，您必须传入父类所需的参数。`Dwelling` 需要输入 `residents` 人数。您可以传入固定的住客人数，例如 `3`。

```
class SquareCabin : Dwelling(3)
```

不过，您希望您的程序能够更加灵活，并且允许 `SquareCabins` 拥有不同的住客人数。因此，在 `SquareCabin` 类定义中将 `residents` 作为一个参数。不要将 `residents` 声明为 `val,`，因为您是在重复使用已在父类 `Dwelling` 中声明的属性。

```
class SquareCabin(residents: Int) : Dwelling(residents)
```



**注意**：使用这些类定义后，系统会在后台执行许多操作。

在类标头中，您会看到 `class SquareCabin(residents: Int) ...`

这实际上是 `class SquareCabin constructor(residents: Int) ...` 的简写形式

当您通过某个类创建对象实例时，系统会调用 `constructor`。例如，当您调用 `SquareCabin(4)` 时，系统会调用 `SquareCabin` 的 `constructor`，以初始化对象实例。

`constructor` 会根据相应类中的所有信息（包括传入的参数）构建实例。当某个类从父级继承属性和函数时，`constructor` 会调用父类的 `constructor`，以完成对象实例的初始化。

因此，当您使用 `SquareCabin(4)` 创建实例时，系统将执行 `SquareCabin` 的 `constructor`，由于继承关系，同时还会执行 `Dwelling` 构造函数。`Dwelling` 类定义指明其构造函数需要 `residents` 参数，因此，您会在 `SquareCabin` 类定义中看到传递给 `Dwelling` 构造函数的 `residents`。



如果您声明抽象函数和变量，就表示您承诺稍后将为它们提供值和实现。对于变量，这意味着该抽象类的任何子类都需要为其提供值。对于函数，这意味着任何子类都需要实现函数主体。

在 `Dwelling` 类中，您定义了一个 `abstract` 变量 `buildingMaterial`。`SquareCabin` 是 `Dwelling` 的子类，因此它必须为 `buildingMaterial` 提供值。使用 `override` 关键字来表明此属性是在父类中定义的，并且在此类中将被替换掉。



**使用 with 简化代码**

在 `println()` 语句中，每次引用 `squareCabin` 的属性或函数时，都必须反复输入 `squareCabin.`。这会形成重复，可能在您复制和粘贴输出语句时造成错误。

当您使用某个类的特定实例，并需要访问该实例的多个属性和函数时，您可以使用 `with` 语句表明“对此实例对象执行以下所有操作”。先输入关键字 `with`，再在圆括号内输入实例名称，然后再输入大括号并在其中指明您想要执行的操作。

```
with (instanceName) {    // all operations to do with instanceName}
```



默认情况下，在 Kotlin 中，[类是最终层级](https://kotlinlang.org/docs/reference/classes.html#inheritance)，无法被子类化。您只能从 `abstract` 类或标记有 `open` 关键字的类继承。因此，您需要使用 `open` 关键字标记 子类，使其能够被继承。

```
open class RoundHut(residents: Int) : Dwelling(residents) {   override val buildingMaterial = "Straw"   override val capacity = 4}
```



**注意**：对于面积值，如果仅显示 2 位小数，用户体验会更好。您可以使用以下语句输出建筑面积：println("Floor area: %.2f".format(floorArea()))



```
/*** Program that implements classes for different kinds of dwellings.* Shows how to:* Create class hierarchy, variables and functions with inheritance,* abstract class, overriding, and private vs. public variables.*/import kotlin.math.PIimport kotlin.math.sqrtfun main() {   val squareCabin = SquareCabin(6, 50.0)   val roundHut = RoundHut(3, 10.0)   val roundTower = RoundTower(4, 15.5)   with(squareCabin) {       println("\nSquare Cabin\n============")       println("Capacity: ${capacity}")       println("Material: ${buildingMaterial}")       println("Floor area: ${floorArea()}")   }   with(roundHut) {       println("\nRound Hut\n=========")       println("Material: ${buildingMaterial}")       println("Capacity: ${capacity}")       println("Floor area: ${floorArea()}")       println("Has room? ${hasRoom()}")       getRoom()       println("Has room? ${hasRoom()}")       getRoom()       println("Carpet size: ${calculateMaxCarpetSize()}")   }   with(roundTower) {       println("\nRound Tower\n==========")       println("Material: ${buildingMaterial}")       println("Capacity: ${capacity}")       println("Floor area: ${floorArea()}")       println("Carpet size: ${calculateMaxCarpetSize()}")   }}/*** Defines properties common to all dwellings.* All dwellings have floorspace,* but its calculation is specific to the subclass.* Checking and getting a room are implemented here* because they are the same for all Dwelling subclasses.** @param residents Current number of residents*/abstract class Dwelling(private var residents: Int) {   abstract val buildingMaterial: String   abstract val capacity: Int   /**    * Calculates the floor area of the dwelling.    * Implemented by subclasses where shape is determined.    *    * @return floor area    */   abstract fun floorArea(): Double   /**    * Checks whether there is room for another resident.    *    * @return true if room available, false otherwise    */   fun hasRoom(): Boolean {       return residents < capacity   }   /**    * Compares the capacity to the number of residents and    * if capacity is larger than number of residents,    * add resident by increasing the number of residents.    * Print the result.    */   fun getRoom() {       if (capacity > residents) {           residents++           println("You got a room!")       } else {           println("Sorry, at capacity and no rooms left.")       }   }   }/*** A square cabin dwelling.**  @param residents Current number of residents*  @param length Length*/class SquareCabin(residents: Int, val length: Double) : Dwelling(residents) {   override val buildingMaterial = "Wood"   override val capacity = 6   /**    * Calculates floor area for a square dwelling.    *    * @return floor area    */   override fun floorArea(): Double {       return length * length   }}/*** Dwelling with a circular floorspace** @param residents Current number of residents* @param radius Radius*/open class RoundHut(       val residents: Int, val radius: Double) : Dwelling(residents) {   override val buildingMaterial = "Straw"   override val capacity = 4   /**    * Calculates floor area for a round dwelling.    *    * @return floor area    */   override fun floorArea(): Double {       return PI * radius * radius   }   /**    *  Calculates the max length for a square carpet    *  that fits the circular floor.    *    * @return length of carpet    */   fun calculateMaxCarpetSize(): Double {       val diameter = 2 * radius       return sqrt(diameter * diameter / 2)   }}/*** Round tower with multiple stories.** @param residents Current number of residents* @param radius Radius* @param floors Number of stories*/class RoundTower(       residents: Int,       radius: Double,       val floors: Int = 2) : RoundHut(residents, radius) {   override val buildingMaterial = "Stone"   // Capacity depends on the number of floors.   override val capacity = floors * 4   /**    * Calculates the total floor area for a tower dwelling    * with multiple stories.    *    * @return floor area    */   override fun floorArea(): Double {       return super.floorArea() * floors   }}
```

### ⑤小结

- 创建一个类层次结构，这是一种包含类的树形结构，其中子级会继承父类的函数。子类继承的有属性和函数。
- 创建一个 `abstract` 类，在这种类中，部分函数会留给其子类来实现。因此，`abstract` 类无法被实例化。
- 创建 `abstract` 类的子类。
- 使用 `override` 关键字，在子类中替换属性和函数。
- 使用 `super` 关键字，引用父类中的函数和属性。
- 将一个类标记为 `open`，使其能够被子类化。
- 将一个属性标记为 `private`，使其只能在相应类中使用。
- 使用 `with` 构造函数，在同一对象实例上进行多次调用。
- 从 `kotlin.math` 库导入函数



## 2 为 Android 应用创建 XML 布局

### ①阅读和理解 XML

注意：可见的界面层次结构基于包含机制，即一个组件内包含一个或多个组件。这与您之前了解的类和子类的层次结构无关。我们有时会使用术语“父级”和“子级”，但这里讨论的是父视图 (viewgroup) 包含子视图，而后者也会包含子视图。

![ab49d373ed5bacce.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/ab49d373ed5bacce.png)

每个界面元素都由 XML 文件中的 XML 元素表示。每个元素都以标记作为开头和结尾，而每个标记都以 `<` 开头，并以 `>` 结尾。正如您可以使用**布局编辑器（设计）**对界面元素设置属性一样，XML 元素也可以具有属性。简化过后，上述界面元素的 XML 可能会如下所示：

```
<ConstraintLayout>    <TextView        text="Hello World!">    </TextView></ConstraintLayout>
```

![9e3f433a224ba1f4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/9e3f433a224ba1f4.png) 

1. 打开 `activity_main.xml` (**res** > **layout** > **activity_main.xml**)

2. 您可能会注意到，正如您在之前通过此模板创建的项目中看到的一样，该应用在 `ConstraintLayout` 内显示了一个包含“Hello World!”的 `TextView`。

   ![](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/520f45bcfc7d1cf7.png)

3. 在布局编辑器的右上角，找到 **Code**、**Split** 以及 **Design** 视图。

4. 选择 **Code** 视图。![ae13d413ae4da131.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/ae13d413ae4da131.png)

   `activity_main.xml` 中的 XML 应如下所示：

   ```
   <?xml version="1.0" encoding="utf-8"?><androidx.constraintlayout.widget.ConstraintLayout    xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    tools:context=".MainActivity">    <TextView        android:layout_width="wrap_content"        android:layout_height="wrap_content"        android:text="Hello World!"        app:layout_constraintBottom_toBottomOf="parent"        app:layout_constraintLeft_toLeftOf="parent"        app:layout_constraintRight_toRightOf="parent"        app:layout_constraintTop_toTopOf="parent" /></androidx.constraintlayout.widget.ConstraintLayout>
   ```

   这与简化的示例相比要复杂得多，但 Android Studio 会执行一些操作来帮助确保 XML 更易于阅读，就像它针对 Kotlin 代码的处理方式一样。

5. 注意缩进。Android Studio 会自动执行此操作，以显示元素的层次结构。`TextView` 之所以缩进显示，是因为它包含在 `ConstraintLayout` 中。`ConstraintLayout` 是父级，而 `TextView` 是子级。每个元素的属性都会缩进显示，以表示它们属于该元素。

6. 注意颜色编码 -  有些是蓝色，有些是绿色，等等。该文件的类似部分会以相同的颜色绘制，以帮助您将它们匹配起来。需要特别注意的是，Android Studio  会以相同颜色绘制元素标记的开头和结尾。（注意：Codelab 中使用的颜色可能与您在 Android Studio 中看到的颜色不一致。）



**有关用于创建布局的 XML 的更多信息**

1. 查看 `ConstraintLayout` 的标记，您会注意到它显示的是 `androidx.constraintlayout.widget.ConstraintLayout`，而不是像 `TextView` 一样仅显示 `ConstraintLayout`。这是因为 `ConstraintLayout` 属于 Android Jetpack，而后者包含在 Android 核心平台上提供其他功能的代码库。Jetpack 包含诸多实用功能，您可以借此更加轻松地构建应用。您会发现此界面组件是 Jetpack 的一部分，因为它以“androidx”开头。

2. 您可能已经注意到以 `xmlns:` 开头，后跟 `android`、`app` 以及 `tools` 的代码行。

   ```
   xmlns:android="http://schemas.android.com/apk/res/android"xmlns:app="http://schemas.android.com/apk/res-auto"xmlns:tools="http://schemas.android.com/tools"
   ```

   `xmlns` 表示 XML 命名空间，并且每行代码都定义了一个架构，或者与这些字词相关的属性的词汇。例如，`android:` 命名空间标记了由 Android 系统定义的属性。布局 XML 中的所有属性均以其中一个命名空间开头。

3. 在 XML 元素之间增加空白字符并不会改变其对计算机的含义，但这有助于用户更加轻松地阅读 XML。

   Android Studio 会自动添加一些空白字符并进行缩进，以提升易读性。您稍后将了解如何使 Android Studio 确保您的 XML 遵循编码样式规范。

4. 您可以像为 Kotlin 代码添加注释一样为 XML 添加注释。注释应以 `<!--` 开头，以 `-->` 结束。请注意文件的第一行：

   ```
   <!-- this is a comment in XML --><!-- this is amulti-lineComment.And anotherMulti-line comment -->
   ```

5. 请注意文件的第一行：

   ```
   <?xml version="1.0" encoding="utf-8"?>
   ```

   这表示该文件是一个 XML 文件，但并非每个 XML 文件都包含此行代码。

   **注意**：如果应用的 XML 存在问题，Android  Studio 将会通过用红色绘制文本来标记相关问题。如果将鼠标悬停在红色文本上，Android Studio  将显示有关该问题的更多信息。如果问题并不明显，请查看缩进和颜色编码，它们可能有助于您找到问题的根源。



### ②使用 XML 构建布局

1. 还是在 `activity_main.xml` 中，切换到 **Split** 屏幕视图，以查看 **Design Editor** 旁边的 XML。在 **Design Editor** 中，您可以预览界面布局。

   ![a2c11e6fd366b378.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/a2c11e6fd366b378.png)

2. 您可以根据个人偏好来决定使用哪种视图，但对于此 Codelab，请使用 **Split** 视图，这样您既可以查看自己修改的 XML，也可以在 **Design Editor** 中看到这些修改造成的变化。

3. 尝试点击不同的代码行，比如先点击 `ConstraintLayout` 下的某行代码，然后再点击 `TextView` 下的某行代码，您会注意到 **Design Editor** 中的相应视图会被选中。反之亦然，例如，如果您在 **Design Editor** 中点击 `TextView`，系统会突出显示相应的 XML。

![d2bdc118dca27c72.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/d2bdc118dca27c72.png)



**删除 TextView**

1. 您现在不需要 `TextView`，因此请将其删除。请务必删除从 `<TextView` 到结束标记 `/>` 之间的所有内容。

   ```
   <TextView    android:layout_width="wrap_content"    android:layout_height="wrap_content"    android:text="Hello World!"    app:layout_constraintBottom_toBottomOf="parent"    app:layout_constraintLeft_toLeftOf="parent"    app:layout_constraintRight_toRightOf="parent"    app:layout_constraintTop_toTopOf="parent" />
   ```

   文件中剩余的所有内容便是 `ConstraintLayout`：

   ```
   <androidx.constraintlayout.widget.ConstraintLayout    xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    tools:context=".MainActivity"></androidx.constraintlayout.widget.ConstraintLayout>
   ```

2. 向 `ConstraintLayout` 添加 16dp 的内边距，避免界面被挤到屏幕的边缘。

内边距与外边距类似，但它会向 `ConstraintLayout` 的内侧增加空间，而不是在外侧增加空间。

```
<androidx.constraintlayout.widget.ConstraintLayout    ...    android:layout_width="match_parent"    android:layout_height="match_parent"    android:padding="16dp"    tools:context=".MainActivity">
```

**注意**：为简洁起见，此 Codelab 中的一些代码段并未显示完整内容。未更改或与当前步骤无关的代码将会用英文省略号（3 个连续的点 `...)`）表示，以便您能够专注于代码中最重要的部分。



**添加“Cost of Service”文本字段**

在这一步中，您将添加界面元素，以便用户在应用中输入服务费用。您将使用 `EditText` 元素，该元素使用户能够在应用中输入或修改文本。

![77011fa1d9b93110.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/77011fa1d9b93110.png)

1. 查看 [`EditText`](https://developer.android.com/reference/kotlin/android/widget/EditText) 文档，并检查示例 XML。
2. 找到 `ConstraintLayout` 的起始标记和结束标记之间的空白区域。
3. 从文档中复制 XML，并将其粘贴到您在 Android Studio 中的布局内的相应空白区域。

此时，您的布局文件应如下所示：

```
<?xml version="1.0" encoding="utf-8"?><androidx.constraintlayout.widget.ConstraintLayout    xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    tools:context=".MainActivity">    <EditText        android:id="@+id/plain_text_input"        android:layout_height="wrap_content"        android:layout_width="match_parent"        android:inputType="text"/></androidx.constraintlayout.widget.ConstraintLayout>
```

您可能还不完全理解上述代码，我们会在以下步骤中进行介绍。

1. 请注意，`EditText` 带有红色下划线。
2. 将鼠标指针悬停在此处，您会看到表明该视图未进行约束的错误，这与您在之前的 Codelab 中看到的类似。前面已经提到，`ConstraintLayout` 的子级需要进行约束，以便布局知道如何整理它们。

![ac6f87c3d5542f18.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/ac6f87c3d5542f18.png)

1. 将这些约束条件添加到 `EditText`，以将其锚定到父级的左上角。

```
app:layout_constraintStart_toStartOf="parent"app:layout_constraintTop_toTopOf="parent"
```

如果您使用英语或其他从左到右 (LTR) 书写的语言编写代码，起始边缘位于左侧。但某些语言（例如阿拉伯语）是从右到左 (RTL)  书写的，因此起始边缘位于右侧。这就是约束条件使用“start”的原因，这样它才能与 LTR 或 RTL  语言搭配使用。同样，约束条件使用“end”，而不是“right”。

**注意**：约束条件的名称应遵循 `layout_constraint<Source>_to<Target>Of` 格式，其中 `<Source>` 是指当前视图。`<Target>` 是指当前视图被约束到的目标视图（可以是父容器，也可以是其他视图）的边缘。

添加新的约束条件后，`EditText` 元素将如下所示：

```
<EditText    android:id="@+id/plain_text_input"    android:layout_height="wrap_content"    android:layout_width="match_parent"    app:layout_constraintStart_toStartOf="parent"    app:layout_constraintTop_toTopOf="parent"    android:inputType="text"/>
```

**检查 EditText 属性**

请仔细检查您粘贴进来的所有 `EditText` 属性，确保它能够在应用中有效运行。

1. 找到设置为 `@+id/plain_text_input` 的 `id` 属性。

2. 将 `id` 属性更改为更合适的名称 `@+id/cost_of_service`。

   **注意**：资源 ID 是元素的唯一资源名称。当您使用**布局编辑器**添加 `View` 或其他资源时，Android Studio 会自动为它们分配资源 ID。当您手动在 XML 中输入时，您需要自行明确声明资源 ID。XML 文件中的新视图 ID 必须使用 `@+id` 前缀进行定义，这会让 Android Studio 将相应 ID 添加为新的资源 ID。

   为资源选择描述性名称，以便您了解它们的用途，但这些名称应全部采用小写字母，且多个单词之间应使用下划线进行分隔。

   当您在应用代码中引用资源 ID 时，请使用 `R.<type>.<name>` 格式，例如 `R.string.roll`。对于 `View` ID，`<type>` 为 `id`，例如 `R.id.button`。

3. 查看 `layout_height` 属性。此属性设置为 `wrap_content`，这意味着它将与其中的内容一样高。此项设置没有问题，因为这里只有 1 行文本。

4. 查看 `layout_width` 属性。此属性设置为 `match_parent`，但您不能针对 `ConstraintLayout` 的子级设置 `match_parent`。此外，文本字段不需要那么宽。请将其设置为 `160dp` 这一固定宽度，这应该足够用户输入服务费用了。

   ![ac7b016367b8fc35.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/ac7b016367b8fc35.png)

5. 注意 `inputType` 属性，它是一项新的属性。该属性的值为 `"text"`，这意味着用户可以在屏幕上的字段中输入任意文本字符（字母字符、符号等）。

   ```
   android:inputType="text"
   ```

   但是，您需要用户在 `EditText` 中仅输入数字，因为该字段表示货币价值。

6. 清除 `text` 这个单词，但保留英文引号。

7. 开始在该位置输入 `number`。输入“n”后，Android Studio 会显示包含“n”的一系列可能的补全项。

   ![1a28bec8e9051cb8.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/1a28bec8e9051cb8.gif)

8. 选择 `numberDecimal`，这会将输入内容限制为带小数点的数字。

   ```
   android:inputType="numberDecimal"
   ```

   如需查看其他输入类型选项，请参阅开发者文档中的[指定输入法类型](https://developer.android.com/training/keyboard-input/style)。

   还需要进行另外一项更改，因为显示一些提示有助于用户确定应该在这个字段中输入什么内容。

9. 将 `hint` 属性添加到 `EditText` 中，用于描述用户应在此字段中输入什么内容。

   ```
   android:hint="Cost of Service"
   ```

   您会看到 **Design Editor** 也相应进行了更新。

   ![e57f60d70089e5c4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/e57f60d70089e5c4.png)

10. 在模拟器中运行您的应用。显示的内容应如图所示：<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/e20d1cc8ee244e71.png" alt="e20d1cc8ee244e71.png" style="zoom:33%;" />



非常棒！它的作用还不是很大，但是您已经有一个良好的开端，并且对 XML 进行了一些修改。您用于创建布局的 XML 应如下所示。

```
<?xml version="1.0" encoding="utf-8"?><androidx.constraintlayout.widget.ConstraintLayout    xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    android:padding="16dp"    tools:context=".MainActivity">    <EditText        android:id="@+id/cost_of_service"        android:layout_width="160dp"        android:layout_height="wrap_content"        android:hint="Cost of Service"        android:inputType="numberDecimal"        app:layout_constraintStart_toStartOf="parent"        app:layout_constraintTop_toTopOf="parent" /></androidx.constraintlayout.widget.ConstraintLayout>
```

**添加服务问题**

在这一步中，您将为问题提示“How was the service?”添加一个 `TextView`。尝试输入此内容，而不是复制/粘贴。Android Studio 提供的建议可能会对您有所帮助。

1. 在 `EditText` 标记的结尾 `/>` 后，新增一行代码并开始输入 `<TextView`

2. 从建议中选择 `TextView`，然后 Android Studio 将自动为 `TextView` 添加 `layout_width` 和 `layout_height` 属性。

3. 对于这两种属性，都选择 `wrap_content`，因为您只需要 `TextView` 与其中的文本内容大小一致。![a2b91d166daddb12.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/a2b91d166daddb12.png)

4. 添加 `text` 属性，将其设置为 `"How was the service?"`

   ```
    <TextView       android:layout_width="wrap_content"       android:layout_height="wrap_content"       android:text="How was the service?"
   ```

5. 以 `/>` 结束标记。

6. 请注意，在 **Design Editor** 中，`TextView` 与 `EditText` 重叠了。

   

   ![37e484973e7cea6c.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/37e484973e7cea6c.png)

   这样看起来不对，因此您接下来需要针对 `TextView` 添加约束条件。思考您需要哪些约束条件。`TextView` 在水平和垂直方向上应该位于何处？您可以通过查看应用屏幕截图来获取帮助。

   ![e53459106e39e86.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/e53459106e39e86.png)

   在垂直方向上，您需要 `TextView` 低于“Cost of Service”文本字段。在水平方向上，您需要 `TextView` 与父视图的起始边缘对齐。

7. 为 `TextView` 添加水平约束条件，将它的起始边缘约束为父视图的起始边缘。

   ```
   app:layout_constraintStart_toStartOf="parent"
   ```

8. 为 `TextView` 添加垂直约束条件，将 `TextView` 的顶部边缘约束为服务费用 `View` 的底部边缘。

   ```
   app:layout_constraintTop_toBottomOf="@id/cost_of_service"
   ```

   请注意，`@id/cost_of_service` 中没有半角加号，因为相应 ID 已定义。

   ![93f7c4dd02cf1a81.png](https://developer.android.com/codelabs/basic-android-kotlin-training-xml-layouts/img/93f7c4dd02cf1a81.png)

   这个应用看起来并不完美，但目前不用担心。您只需确保所有必要的组件都显示在屏幕上，并且功能正常即可。您将在后续 Codelab 中修改其外观。

9. 在 `TextView` 上添加资源 ID。稍后，当您添加更多视图，并使其互相约束时，会需要引用此视图。

```
android:id="@+id/service_question"
```

此时，您的 XML 应如下所示。

```
<?xml version="1.0" encoding="utf-8"?><androidx.constraintlayout.widget.ConstraintLayout    xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    tools:context=".MainActivity">    <EditText        android:id="@+id/cost_of_service"        android:hint="Cost of Service"        android:layout_height="wrap_content"        android:layout_width="160dp"        app:layout_constraintStart_toStartOf="parent"        app:layout_constraintTop_toTopOf="parent"        android:inputType="numberDecimal"/>    <TextView        android:id="@+id/service_question"        android:layout_width="wrap_content"        android:layout_height="wrap_content"        android:text="How was the service?"        app:layout_constraintStart_toStartOf="parent"        app:layout_constraintTop_toBottomOf="@id/cost_of_service"/></androidx.constraintlayout.widget.ConstraintLayout>
```



### ③小结

- XML（可扩展标记语言）是一种整理文本的方式，由标记、元素和属性组成。
- 使用 XML 可定义 Android 应用的布局。
- 使用 `EditText` 可支持用户输入或修改文本。
- `EditText` 会生成一条提示，告知用户应在相应字段内输入什么内容。
- 指定 `android:inputType` 属性可限制用户在 `EditText` 字段输入哪种类型的文本。
- 使用 `RadioButtons` 可创建一个互斥选项列表，并使用 `RadioGroup` 进行分组。
- `RadioGroup` 可以垂直排列，也可以水平排列，并且您可以指定最初选中的应该是哪个 `RadioButton`。
- 使用 `Switch` 可让用户在两个选项之间切换。
- 您可以在不使用单独的 `TextView` 的情况下为 `Switch` 添加标签。
- `ConstraintLayout` 的每个子级都必须具有垂直和水平约束条件。
- 使用“start”和“end”约束条件可处理从左到右 (LTR) 和从右到左 (RTL) 书写的语言。
- 约束条件属性的名称应遵循 `layout_constraint<Source>_to<Target>Of` 格式。
- 如需将 `View` 设置为与它所在的 `ConstraintLayout` 一样宽，请将其起始边缘约束为父级的起始边缘，将结束边缘约束为父级的结束边缘，并将宽度设置为 0dp。

## 3  视图绑定

为了计算小费，代码需要访问所有界面元素以读取用户的输入。您可以回想一下，在之前的 Codelab 中讲过，代码需要先找到对 `View`（如 `Button` 或 `TextView`）的引用，然后才能对 `View` 调用方法或访问其属性。Android 框架提供了 `findViewById()` 方法，其用途正是您所需要的，那就是给定 `View` 的 ID，返回对它的引用。此方法行得通，但随着您向应用添加更多视图并且界面变得越来越复杂，使用 `findViewById()` 可能会变得很麻烦。

为了方便起见，Android 还提供了一项名为[视图绑定](https://developer.android.com/topic/libraries/view-binding)的功能。只需提前多做一点工作，视图绑定就能使得在界面中对视图调用方法更加简便快捷。您需要在 Gradle 中为应用启用视图绑定，并对代码进行一些更改。



**启用视图绑定**

1. 打开应用的 `build.gradle` 文件 (**Gradle Scripts > build.gradle (Module: Tip_Time.app)**)。

2. 在 `android` 部分中，添加以下代码行：

   ```
   buildFeatures {    viewBinding = true}
   ```

3. 注意以下消息：**Gradle files have changed since last project sync**。

4. 按 **Sync Now**。

![aa49f2389f1d1b19.png](https://developer.android.com/codelabs/basic-android-kotlin-training-tip-calculator/img/aa49f2389f1d1b19.png)

片刻之后，您应该会看到 Android Studio 窗口底部显示以下消息：**Gradle sync finished**。如果需要，您可以关闭 `build.gradle` 文件。



**初始化绑定对象**

在之前的 Codelab 中，您看到过 `MainActivity` 类中的 `onCreate()` 方法。它是应用启动并初始化 `MainActivity` 时最先调用的内容之一。您将创建并初始化一次绑定对象，而不是在应用中针对每个 `View` 调用 `findViewById()`。

![a3f060e1765e049a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-tip-calculator/img/a3f060e1765e049a.png)

1. 打开 `MainActivity.kt` (**app > java > com.example.tiptime > MainActivity**)。

2. 将 `MainActivity` 类的所有现有代码替换为以下代码，设置 `MainActivity` 以使用视图绑定：

   ```
   class MainActivity : AppCompatActivity() {    lateinit var binding: ActivityMainBinding    override fun onCreate(savedInstanceState: Bundle?) {        super.onCreate(savedInstanceState)        binding = ActivityMainBinding.inflate(layoutInflater)        setContentView(binding.root)    }}
   ```

3. 以下代码行在类中为绑定对象声明一个顶级变量。之所以在此级别上定义该变量，是因为将在 `MainActivity` 类的多个方法中使用它。

   ```
   lateinit var binding: ActivityMainBinding
   ```

4. 以下代码行初始化 `binding` 对象，您将使用该对象访问 `activity_main.xml` 布局中的 `Views`。

   ```
   binding = ActivityMainBinding.inflate(layoutInflater)
   ```

5. 设置 activity 的内容视图。以下代码行指定应用中视图层次结构的根 `binding.root`，而不是传递布局 `R.layout.activity_main` 的资源 ID。

   ```
   setContentView(binding.root)
   ```

您可能还记得父视图和子视图的概念；根连接到所有这些视图。

现在，当您需要在应用中引用 `View` 时，您可以从 `binding` 对象获取它，而不是调用 `findViewById()`。`binding` 对象可自动为应用中具有 ID 的每个 `View` 定义引用。使用视图绑定要简洁得多，通常您甚至不需要创建一个变量来保存 `View` 的引用，只需直接从绑定对象使用它即可。

```
// Old way with findViewById()val myButton: Button = findViewById(R.id.my_button)myButton.text = "A button"// Better way with view bindingval myButton: Button = binding.myButtonmyButton.text = "A button"// Best way with view binding and no extra variablebinding.myButton.text = "A button"
```

这样是不是很棒！

**注意**：系统会通过以下方式生成绑定类的名称：将 XML 文件的名称转换为驼峰式大小写，并在末尾添加“Binding”一词。同样，系统会通过以下方式生成每个视图的引用：移除下划线并将视图名称转换为驼峰式大小写。例如，`activity_main.xml` 将变为 `ActivityMainBinding`，您能以 `binding.textView` 的形式访问 `@id/text_view`。



## 4  测试和调试

您已经在不同的步骤中运行了应用以确保它如您所愿，但现在是时候进行一些额外的测试了。

现在，考虑一下在 `calculateTip()` 方法中信息是如何在应用中移动的，以及每一步可能会出现什么问题。

例如，在以下代码行中：

```
val cost = stringInTextField.toDouble()
```

如果 `stringInTextField` 不表示数字，会发生什么情况？如果用户未输入任何文本因而 `stringInTextField` 为空，会发生什么情况？

1. 在模拟器中运行应用，但使用 **Run > Debug ‘app'**，而不是使用 **Run > Run ‘app'**。
2. 尝试服务费用、小费金额以及是否向上舍入小费的不同组合，验证您在各种情况下点按 **Calculate** 时是否能够获得预期结果。
3. 现在，尝试删除 **Cost of Service** 字段中的所有文本，然后点按 **Calculate**。糟糕，程序崩溃了。



**调试崩溃问题**

处理错误的第一步是弄清楚发生了什么。Android Studio 将系统中发生的情况保存在[日志](https://developer.android.com/studio/debug/am-logcat)中，您可以使用日志弄清楚出了什么问题。

1. 按 Android Studio 底部的 **Logcat** 按钮，或在菜单中依次选择 **View > Tool Windows > Logcat**。![30049befc3b5326e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-tip-calculator/img/30049befc3b5326e.png)

2. **Logcat** 窗口将显示在 Android Studio 底部，其中填充有一些看起来很奇怪的文本。![e78f4d64e5dbb7f1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-tip-calculator/img/e78f4d64e5dbb7f1.png)这些文本是一个堆栈轨迹，列出了发生崩溃时正在调用的方法。

3. 在 **Logcat** 文本中向上滚动，直到您找到包含 `FATAL EXCEPTION` 文本的行。

   ```
   2020-06-24 10:09:41.564 24423-24423/com.example.tiptime E/AndroidRuntime: FATAL EXCEPTION: main    Process: com.example.tiptime, PID: 24423    java.lang.NumberFormatException: empty String        at sun.misc.FloatingDecimal.readJavaFormatString(FloatingDecimal.java:1842)        at sun.misc.FloatingDecimal.parseDouble(FloatingDecimal.java:110)        at java.lang.Double.parseDouble(Double.java:538)        at com.example.tiptime.MainActivity.calculateTip(MainActivity.kt:22)        at com.example.tiptime.MainActivity$onCreate$1.onClick(MainActivity.kt:17)
   ```

4. 向下读，直到您找到包含 `NumberFormatException` 的行。

   ```
   java.lang.NumberFormatException: empty String
   ```

   右侧显示的是 `empty String`。异常的类型告知您它与数字格式有关，其余部分告知您问题的基本信息：找到了一个空 `String`，而它本应是一个具有值的 `String`。

5. 继续向下读，您会看到对 `parseDouble()` 的一些调用。

6. 在这些调用下面，找到包含 `calculateTip` 的行。请注意，它也包含 `MainActivity` 类。

   ```
   at com.example.tiptime.MainActivity.calculateTip(MainActivity.kt:20)
   ```

7. 仔细查看该行，您可以看到在代码中进行调用的确切位置，那就是 `MainActivity.kt` 中的第 20 行。（如果您以不同的方式输入代码，此处可能是一个不同的数字。）该行会将 `String` 转换为 `Double`，并将结果赋值给 `cost` 变量。

   ```
   val cost = stringInTextField.toDouble()
   ```

8. 在 Kotlin 文档中查找用于处理 `String` 的 `toDouble()` 方法。该方法称为 [`String.toDouble()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/to-double.html)。

9. 页面上显示“Exceptions: `NumberFormatException` - if the string is not a valid representation of a number”。

异常是系统提示出现问题的一种方式。在本例中，问题是 `toDouble()` 无法将空 `String` 转换为 `Double`。虽然 `EditText` 具有 `inputType=numberDecimal` 设置，但仍有可能输入一些 `toDouble()` 无法处理的值，如一个空字符串。



**了解 null**

对空字符串或不表示有效十进制数字的字符串调用 `toDouble()` 不起作用。幸好，Kotlin 还提供了一种名为 `toDoubleOrNull()` 的方法来处理这些问题。如果可以，它会返回十进制数字；如果存在问题，它会返回 `null`。

null 是一个特殊值，表示“无值”。它与值为 `0.0` 的 `Double` 或包含零个字符串的空 `String` `""` 不同。`Null` 表示没有值，没有 `Double` 或没有 `String`。许多方法都期望有一个值，但它们可能不知道如何处理 `null` 并且会停止，这意味着应用会崩溃，因此 Kotlin 试图限制使用 `null` 的位置。您将在未来的课程中详细了解这一点。

应用可以检查是否从 `toDoubleOrNull()` 返回 `null`，并在返回 null 时以不同的方式处理，这样应用就不会崩溃。

1. 在 `calculateTip()` 中，更改声明 `cost` 变量的代码行以调用 `toDoubleOrNull()`，而不是调用 `toDouble()`。

   ```
   val cost = stringInTextField.toDoubleOrNull()
   ```

2. 在该行后面，添加一个语句来检查 `cost` 是否为 `null`，如果是，则从方法返回。`return` 指令表示退出方法而不执行其余指令。如果方法需要返回一个值，您可以使用带有表达式的 `return` 指令来指定它。

   ```
   if (cost == null) {    return}
   ```

3. 再次运行应用。

4. 在 **Cost of Service** 字段中没有文本的情况下，点按 **Calculate**。这次应用没有崩溃！太棒了 - 您找到并修复了错误！



**处理其他情况**

并非所有错误都会导致应用崩溃，有时结果可能会让用户感到困惑。

下面是要考虑的其他情况。如果用户执行以下操作，会发生什么：

1. 为服务费用输入有效的金额
2. 点按 **Calculate** 以计算小费
3. 删除服务费用
4. 再次点按 **Calculate**

第一次，将按预期计算并显示小费。第二次，由于您刚刚添加的检查，`calculateTip()` 方法将提前返回，但应用仍显示之前的小费金额。这可能会让用户感到困惑，因此应添加一些代码，以便在出现问题时清除小费金额。

1. 确认此问题就是发生的情况，具体方法是输入有效的服务费用并点按 **Calculate**，然后删除文本，并再次点按 **Calculate**。应该仍显示第一次的小费值。
2. 在刚刚添加的 `if` 内，在 `return` 语句前面，添加一个代码行以将 `tipResult` 的 `text` 属性设置为一个空字符串。

```
if (cost == null) {    binding.tipResult.text = ""    return}
```

这样将在从 `calculateTip()` 返回之前清除小费金额。

1. 再次运行应用，并尝试上述情况。当您第二次点按 **Calculate** 时，第一次的小费金额应该会消失。

恭喜！您已经为 Android 创建了一个可以正常使用的小费计算器应用，并处理了一些极端情况！



**检查代码**

灰线非常细，很容易被忽视。您可以在整个文件中查找更多灰线，但有一种更简单的方法可以确保您找到所有建议。

1. 在 `MainActivity.kt` 仍打开的情况下，在菜单中依次选择 **Analyze > Inspect Code...**。此时将显示一个名为 **Specify Inspection Scope** 的对话框。![8928e3338cd97887.png](https://developer.android.com/codelabs/basic-android-kotlin-training-tip-calculator/img/8928e3338cd97887.png)
2. 选择以 **File** 开头的选项，然后按 **OK**。这样会将检查范围限制为只有 `MainActivity.kt`。
3. 此时将在底部显示一个包含 **Inspection Results** 的窗口。



**移除不必要的变量**

Android Studio 不再有任何检查结果。不过，如果您仔细看一下代码，您会看到一个与刚刚更改的模式类似的模式：`roundUp` 变量在一行中赋值，在下一行中使用，在其他任何位置都不使用。

1. 从 `roundUp` 赋值的行复制 `=` 右侧的表达式。

   ```
   val roundUp = binding.roundUpSwitch.isChecked
   ```

2. 将下一行中的 `roundUp` 替换为您刚刚复制的表达式 `binding.roundUpSwitch.isChecked`。

   ```
   if (binding.roundUpSwitch.isChecked) {    tip = kotlin.math.ceil(tip)}
   ```

3. 删除包含 `roundUp` 的行，因为不再需要这一行。

您执行的操作与 Android Studio 帮助您对 `selectedId` 变量执行的操作相同。同样，代码少了一行，少了一个变量。这些是细微的更改，但有助于提高代码的简洁性和可读性。



**（可选）消除重复代码**

一旦应用正确运行，您就可以寻找其他机会来清理代码，使其更简洁。例如，当您不在服务费用中输入值时，应用会将 `tipResult` 更新为一个空字符串 `""`。当存在值时，您可以使用 `NumberFormat` 设置其格式。此功能可以在应用中的其他位置使用，例如，显示小费 `0.0` 而不是空字符串。

为了减少非常相似的代码的重复，您可以将这两行代码提取到它们自己的函数中。此辅助函数可以将 `Double` 形式的小费金额作为输入、设置其格式，并更新屏幕上的 `tipResult` `TextView`。

1. 识别 `MainActivity.kt` 中的重复代码。这些代码行可以在 `calculateTip()` 函数中使用多次，一次用于 `0.0` 的情况，一次用于一般情况。

```
val formattedTip = NumberFormat.getCurrencyInstance().format(0.0)binding.tipResult.text = getString(R.string.tip_amount, formattedTip)
```

1. 将重复代码移至其自己的函数。对代码的一项更改是采用小费参数，这样代码就可以在多个位置使用。

```
private fun displayTip(tip : Double) {   val formattedTip = NumberFormat.getCurrencyInstance().format(tip)   binding.tipResult.text = getString(R.string.tip_amount, formattedTip)}
```

1. 更新 `calculateTip()` 函数以使用 `displayTip()` 辅助函数并检查 `0.0`。

```
MainActivity.ktprivate fun calculateTip() {    ...        // If the cost is null or 0, then display 0 tip and exit this function early.        if (cost == null || cost == 0.0) {            displayTip(0.0)            return        }    ...    val roundUp = binding.roundUpSwitch.isChecked    if (roundUp) {        tip = kotlin.math.ceil(tip)    }    // Display the formatted tip value on screen    displayTip(tip)}
```

**备注**

虽然应用已经可以正常运行，但还没有准备好投入使用。您需要进行更多测试。而且，您还需要从视觉上稍加润色，并遵循 Material Design 准则。您还会在接下来的 Codelab 中学习如何更改应用主题和应用图标。



### 小结

- 视图绑定可让您更轻松地编写可与应用中的界面元素交互的代码
- Kotlin 中的 `Double` 数据类型可存储十进制数字
- 使用 `RadioGroup` 的 `checkRadioButtonId` 属性查找选中了哪个 `RadioButton`
- 使用 `NumberFormat.getCurrencyInstance()` 获取用于将数字格式设置为货币的格式设置工具
- 您可以使用 `%s` 等字符串参数来创建动态字符串，这些字符串仍可以轻松地翻译成其他语言
- 测试非常重要！
- 您可以使用 Android Studio 中的 **Logcat** 排查应用崩溃等问题
- 堆栈轨迹显示调用的方法列表。如果代码生成异常，这会很有用。
- 异常指示代码没有预料到的问题
- `Null` 表示“无值”
- 并非所有代码都可以处理 `null` 值，因此使用它时应格外小心
- 依次选择 **Analyze > Inspect Code**，以获取关于改进代码的建议





## 5. 设计和颜色

**Material Design**

[Material Design](https://material.io/design/introduction) 深受物质世界及其纹理（包括物体如何反射光和投射阴影）启发构建而成。它提供了一些准则，指导如何以具有可读性、吸引力和一致性的方式构建应用界面。借助 [Material Theming](https://material.io/design/material-theming/overview.html#material-theming)，您可以依据关于自定义颜色、排版和形状的指南，针对应用调整 Material Design。Material Design  附带有内置基准主题，您可按原样使用这些主题。然后，您可以根据自己的喜好对其进行不同程度的自定义，使 Material 中的设计适合您的应用。

**有关颜色的一些知识**

无论是在现实世界还是在数字化领域，颜色无处不在。首先要知道的是，用户看到颜色的方式不尽相同，因此为应用选择颜色尤为重要，这有助于用户有效地使用您的应用。选择具有足够色彩对比度的颜色只是[构建无障碍功能更出色的应用](https://developer.android.com/guide/topics/ui/accessibility)的一个环节。

![47b4f1f5984b079b.png](https://developer.android.com/codelabs/basic-android-kotlin-training-change-app-theme/img/47b4f1f5984b079b.png)

[颜色](https://developer.android.com/reference/kotlin/android/graphics/Color)可以表示为 3 个十六进制数 #00-#FF (0-255)，分别代表该颜色的红色、绿色和蓝色 (RGB) 分量。数字越大，该分量就越多。

![730ee7b8c4496433.png](https://developer.android.com/codelabs/basic-android-kotlin-training-change-app-theme/img/730ee7b8c4496433.png)

请注意，定义颜色时还可以添加一个 alpha 值 #00-#FF，它表示透明度（#00 = 0% = 完全透明，#FF = 100% =  完全不透明）。若添加 alpha 值，则该值为 4 个十六进制数 (ARGB) 中的第一个。如果未添加 alpha 值，系统会假定 #FF =  100%，即不透明。

然而，您无需自己生成这些十六进制数。系统提供了一些工具，可帮助您选择颜色，它们会为您生成这些数值。

您可能已在 Android 应用的 `colors.xml` 文件中看到了一些示例，其中包括 100% 黑色（R=#00、G=#00、B=#00）和 100% 白色（R=#FF, G=#FF、B=#FF）：

```
<color name="black">#FF000000</color><color name="white">#FFFFFFFF</color>
```

### 小结

- 使用 Material [Color Tool](https://material.io/resources/color/) 选择应用主题的颜色。
- 您也可以使用 [Material palette 生成器](https://material.io/design/color/the-color-system.html#tools-for-picking-colors)来帮助选择调色板。
- 在 `colors.xml` 文件中声明颜色资源，以便更轻松地重复使用它们。
- 深色主题可减少耗电量，并使您的应用在弱光环境下更易于阅读。



## 6 更改应用图标

设置启动图标的目标是，无论设备型号或屏幕密度如何，您的启动器图标看起来都非常出色（清晰、简洁）。具体而言，屏幕像素密度是指屏幕上每英寸的像素数（或每英寸的点数 (dpi)）。对于中密度设备 (mdpi)，屏幕上每英寸有 160 个点，而超超超高密度设备 (xxxhdpi) 的屏幕上每英寸有 640  个点。

为适应不同屏幕密度的设备，您需要提供不同版本的应用图标。

**浏览启动器图标文件**

1. 如需查看图标的显示效果，请在 Android Studio 中打开您的项目。如果您的应用是通过模板创建的，那么您应该具有已由 Android Studio 提供的默认启动器图标。

2. 在**“Project”窗口**中，切换到 **Project** 视图。系统会根据项目文件在计算机上保存时所采用的文件结构，向您显示这些文件。

   ![4f9aa3d93f41669.png](https://developer.android.com/codelabs/basic-android-kotlin-training-change-app-icon/img/4f9aa3d93f41669.png)

3. 转到资源目录 (**app > src > main > res**)，然后展开一些 `mipmap` 文件夹。您应将 Android 应用的启动器图标资源放到这些 `mipmap` 文件夹中。

![4809cedb440baf9a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-change-app-icon/img/4809cedb440baf9a.png)

`mdpi`、`hdpi`、`xhdpi` 等是密度限定符，您可以将其附加到资源目录的名称（例如 `mipmap`）上，以表明其中的资源适用于特定屏幕密度的设备。以下是 Android 上的[密度限定符](https://developer.android.com/training/multiscreen/screendensities#TaskProvideAltBmp)列表：

- `mdpi` - 适用于中密度屏幕（约 160dpi）的资源
- `hdpi` - 适用于高密度屏幕（约 240dpi）的资源
- `xhdpi` - 适用于超高密度屏幕（约 320dpi）的资源
- `xxhdpi` - 适用于超超高密度屏幕（约 480dpi）的资源
- `xxxhdpi` - 适用于超超超高密度屏幕（约 640dpi）的资源
- `nodpi` - 不能缩放的资源（无论屏幕的像素密度是多少）
- `anydpi` - 可针对任何密度进行缩放的资源

**注意**：您可能会好奇，为何启动器图标资源位于 `mipmap` 目录中，而其他应用资源位于 `drawable` 目录中。这是因为，某些启动器显示的应用图标尺寸可能会比设备默认密度级别提供的应用图标尺寸要大。例如，在 hdpi 设备上，某些设备启动器可能需要改用 xhdpi 版本的应用图标。



如果您点击图片文件，将会看到预览。`ic_launcher.png` 文件包含图标的方形版本，而 `ic_launcher_round.png` 文件包含图标的圆形版本。每个资源目录中均提供了这两个版本。

例如，以下便是 **res > mipmap-xxxhdpi > ic_launcher_round.png** 的预览效果。另请注意，相应资源的尺寸位于右上角。此图片的尺寸为 192px x 192px。

![f3a9121a119fe71a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-change-app-icon/img/f3a9121a119fe71a.png)

另外，以下是 **res > mipmap-mdpi > ic_launcher_round.png** 的预览效果。它的尺寸仅为 48px x 48px。

![e76f2f5200934151.png](https://developer.android.com/codelabs/basic-android-kotlin-training-change-app-icon/img/e76f2f5200934151.png)

如您所见，这些位图图片文件由一个固定的像素网格组成。它们针对特定的屏幕分辨率而创建。因此，如果您调整它们的尺寸，图标质量将会降低。

如果您缩小某个位图图片，由于您是去掉一些像素信息，它可能看起来还不错。如果您大幅放大某个位图图片，它可能会显得模糊不清，因为 Android 将需要推测并填补缺少的像素信息。

**注意**：为了避免应用图标模糊不清，请务必针对每个密度级别（`mdpi`、`hdpi`、`xhdpi` 等…）提供不同的应用图标位图图片。请注意，设备屏幕密度不会刚好是 160dpi、240dpi、320dpi 等…Android 将会根据当前的屏幕密度，按最近的较大密度级别选择资源，然后再将其缩小。



## 7 打造更精巧的用户体验

### ①Material 组件

[Material 组件](https://material.io/components)是常见的界面微件，可让您更轻松地在应用中实施 Material 样式。本文档提供了有关如何使用和自定义 Material Design 组件的信息。每个组件都有通用的 Material  Design 准则，对于 Android 上可用的组件有 Android  平台特定的指南。如果所选平台中不存在某个组件，加标签的图表可为您提供足够的信息来重新创建相应组件。

![c4a4db857bb36c3f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/c4a4db857bb36c3f.png)

通过使用 Material 组件，您的应用将与用户设备上的其他应用一起以更一致的方式运行。这样一来，在一个应用中学到的界面模式就可以沿用到下一个应用中。因此，用户将能更快地学会如何使用您的应用。建议尽可能使用 [Material 组件](https://medium.com/androiddevelopers/we-recommend-material-design-components-81e6d165c2dd)（而不是非 Material 微件）。您将在下一个任务中了解到，Material 组件更灵活，可自定义程度更高。

Material Design 组件 (MDC) 库需要作为依赖项添加到项目中。如果您使用的是 Android Studio 4.1 或更高版本，那么在默认情况下，您的项目中应该已经包含此代码行。在应用的 `build.gradle` 文件中，确保此依赖项包含在该库的最新版本中。如需了解更多详情，请参阅 Material 网站上的[使用入门](https://material.io/develop/android/docs/getting-started)页面。

app/build.gradle

```
dependencies {    ...    implementation 'com.google.android.material:material:<version>'}
```

### ②添加图标

在此任务中，您将向应用中添加三个矢量可绘制对象图标：

1. “Cost of Service”文本字段费用旁边的图标

2. 服务问题旁边的图标

3. “round up tip”提示旁边的图标

   以下是该应用的最终版本的屏幕截图。添加图标后，您可以调整布局以适应这些图标的放置位置。注意，添加图标后，字段和“CALCULATE”按钮会移到右侧。

   ![8c4225390dd1fb20.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/8c4225390dd1fb20.png)

   

   

   **添加矢量可绘制对象资源**

   您可以直接在 Android Studio 中的 **Asset Studio** 中将这些图标创建为矢量可绘制对象。

4. 打开应用窗口左侧的 **Resource Manager** 标签页。

5. 点击 + 图标，然后选择 **Vector Asset**。

   ![6a692157a2ada3f6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/6a692157a2ada3f6.png)

6. 对于 **Asset Type**，请确保选中加标签 **Clip Art** 的单选按钮。

   ![698ab1c8dc2d1714.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/698ab1c8dc2d1714.png)

7. 点击 **Clip Art:** 旁边的按钮，选择其他剪贴画图片。在显示的提示中，在出现的窗口中输入“call made”。您将使用此箭头图标表示“round up tip”选项。选中该图标，然后点击 **OK**。

   ![50b0008ed6ab8d6d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/50b0008ed6ab8d6d.png)

8. 将图标重命名为 `ic_round_up`。（建议您在命名图标文件时使用前缀 ic_）。您可以将 **Size** 保留为 24 dp x 24 dp，将 **Color** 设置为黑色 000000。

9. 点击 **Next**。

10. 接受默认目录位置，然后点击 **Finish**。

    ![9f522a73be34ecf6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/9f522a73be34ecf6.png)

11. 对其他两个图标重复步骤 2 - 7：

    - **服务问题图标**：搜索“room service”图标，并将其另存为 `ic_service`。
    - **服务费用图标**：搜索“store”图标，并将其另存为 `ic_store`。

    ![3c895747fbfa3793.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/3c895747fbfa3793.png)

12. 完成上述操作后，**Resource Manager** 看起来将类似于以下屏幕截图。您还将在 `res/drawable` 文件夹中列出这三个矢量可绘制对象（`ic_round_up`、`ic_service` 和 `ic_store`）。





**支持较低版本的 Android**

您刚刚在应用中添加了矢量可绘制对象，但请务必注意，在 Android 平台上，直到 [Android 5.0（API 级别 21）](https://developer.android.com/guide/topics/graphics/vector-drawable-resources)才添加了对矢量可绘制对象的支持。

根据您的项目设置，Tip Time 应用的最低 SDK 版本是 API 19。这意味着，应用可以在搭载 Android 平台版本 19 或更高版本的 Android 设备上运行。

如需让您的应用在这些较低版本的 Android 上正常工作（称为向后兼容性），请将 `vectorDrawables` 元素添加到应用的 `build.gradle` 文件。这样，您就能够在低于 API 21 的平台版本上使用矢量可绘制对象，而无需在构建项目时将其转换为 PNG。如需了解更多详情，请参阅[此处](https://developer.android.com/guide/topics/graphics/vector-drawable-resources#vector-drawables-backward-solution)。

```
app/build.gradleandroid {  defaultConfig {    ...    vectorDrawables.useSupportLibrary = true   }   ...}
```

正确配置项目后，您现在可以开始将图标添加到布局中。



### ③样式和主题

[样式](https://medium.com/androiddevelopers/android-styling-themes-vs-styles-ebe05f917578)是单一类型微件的视图属性值的集合。例如，`TextView` 样式可以指定字体颜色、字体大小和背景色等。通过将这些属性提取到样式中，您可以轻松地将样式应用于布局中的多个视图，并在一个位置对样式进行维护。

在此任务中，您首先需要为文本视图、单选按钮和开关微件创建样式。



#### **创建样式**

1. 在 **res > values** 目录中创建一个名为 `styles.xml` 的新文件（如果尚不存在此文件）。如需进行创建，请右键点击 **values** 目录，然后依次选择 **New > Values Resource File**。将其命名为 `styles.xml`。新文件将包含以下内容。

   ```
   <?xml version="1.0" encoding="utf-8"?><resources></resources>
   ```

2. 创建新的 `TextView` 样式，使文本在整个应用中保持一致。在 `styles.xml` 中定义一次样式，然后就可以将其应用于布局中的所有 `TextViews`。虽然可以从头开始定义样式，但您也可以从 MDC 库中的现有 `TextView` 样式进行扩展。

   

   设置组件样式时，您通常应从正在使用的微件类型的父样式进行扩展。这一点很重要，原因有两个：首先，它可确保在您的组件上设置所有重要的默认值；其次，您的样式将继续继承今后父样式的所有更改。

   您可以随意命名您的样式，但建议采用以下惯例。如果继承自父 Material 样式，请以并行方式命名样式，将 `MaterialComponents` 替换为应用的名称 (`TipTime`)。这会将您的更改移动到其自己的命名空间中，从而消除 Material 组件引入新样式时可能出现的冲突。示例：

   您的样式名称：`Widget.TipTime.TextView` 继承自父样式：`Widget.MaterialComponents.TextView`

   将其添加到 `styles.xml` 文件中 `resources` 起始标记和结束标记之间。

   ```
   <style name="Widget.TipTime.TextView" parent="Widget.MaterialComponents.TextView"></style>
   ```

   

3. 设置 `TextView` 样式，以便它替换以下属性：`android:minHeight,android:gravity,` 和 `android:textAppearance.`

   `android:minHeight` 将 `TextView` 的最小高度设置为 48dp。根据 [Material Design 准则](https://material.io/components/lists#specs)，任何行的最小高度都应为 48dp。

   

   您可以通过设置 `android:gravity` 属性使文本在 `TextView` 中垂直居中。（如以下屏幕截图所示。）重力值用于控制视图内内容的位置。由于实际文本内容的高度不会占据完整的 48dp，因此值 `center_vertical` 会在 `TextView` 中将文本垂直居中（但不会更改其水平位置）。其他可能的重力值包括 `center`、`center_horizontal`、`top` 和 `bottom`。您可以随意尝试其他重力值来查看对文本的影响。

   ![bd89f5a76d67ada6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/bd89f5a76d67ada6.png)

   将文本外观属性值设置为 `?attr/textAppearanceBody1`。TextAppearance 是围绕文本大小、字体和其他属性预制的一组样式。如需了解 Material 提供的其他可能的文本外观，请参阅此[类型缩放列表](https://material.io/develop/android/theming/typography)。

   ```
   <style name="Widget.TipTime.TextView" parent="Widget.MaterialComponents.TextView">    <item name="android:minHeight">48dp</item>    <item name="android:gravity">center_vertical</item>    <item name="android:textAppearance">?attr/textAppearanceBody1</item></style>
   ```

   

4. 通过为 `activity_main.xml` 中的每个 `TextView` 添加样式属性，将 `Widget.TipTime.TextView` 样式应用于 `service_question` `TextView`。

   ```
   <TextView    android:id="@+id/service_question"    style="@style/Widget.TipTime.TextView"    ... />
   ```

   添加样式前，`TextView` 看起来如下所示，采用较小字号的灰色字体：

   ![5cd99583da77efba.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/5cd99583da77efba.png)

   添加样式后，`TextView` 看起来如下所示。现在，此 `TextView` 看起来与布局的其余部分更加一致。

   ![296a89a6015d9e15.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/296a89a6015d9e15.png)

   

5. 将相同的 `Widget.TipTime.TextView` 样式应用于 `tip_result` `TextView`。

   ```
   <TextView    android:id="@+id/tip_result"    style="@style/Widget.TipTime.TextView"    ... />
   ```

   ![c45860bda6761be7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/c45860bda6761be7.png)

   

   

   **注意**：如果您在样式中指定属性（例如将 `android:textSize` 设置为 `18sp`），并在布局文件中指定相同的属性（例如将 `android:textSize` 设置为 `14sp`），则您在布局中设置的值 (`14sp`) 实际上将应用于您在屏幕上看到的内容。

   

   

6. 此外，还应将相同的文本样式应用于开关中的文本标签。但是，您无法为 `SwitchMaterial` 微件设置 `TextView` 样式。`TextView` 样式仅可应用于 `TextViews`。因此，请为开关创建一个新的样式。这些属性在 `minHeight`、`gravity` 和 `textAppearance` 方面相同。此处唯一的区别在于样式名称和父样式，因为您现在继承的是 MDC 库中的 `Switch` 样式。样式的名称还应反映父样式的名称。

   您的样式名称：`Widget.TipTime.CompoundButton.Switch`。继承自父样式：`Widget.MaterialComponents.CompoundButton.Switch`

   ```
   <style name="Widget.TipTime.CompoundButton.Switch" parent="Widget.MaterialComponents.CompoundButton.Switch">   <item name="android:minHeight">48dp</item>   <item name="android:gravity">center_vertical</item>   <item name="android:textAppearance">?attr/textAppearanceBody1</item></style>
   ```

   您还可以在此样式中指定特定于开关的其他属性，但在您的应用中，没有必要这样做。

   

7. 单选按钮文本是您要确保文本在视觉保持上一致的最后一个位置。您不能对 `RadioButton` 微件应用 `TextView` 样式或 `Switch` 样式。相反，您必须为单选按钮创建新的样式。您可以从 MDC 库的 `RadioButton` 样式进行扩展。

   

   创建此样式时，请同时在单选按钮文本和圆圈视觉元素之间添加一些内边距。`paddingStart` 是您尚未使用的新属性。内边距是视图内容与视图边界之间的间距。`paddingStart` 属性仅在组件起始位置设置内边距。查看在单选按钮上设置 0dp 和 8dp `paddingStart` 的区别。

   ![e1cef41d95740600.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/e1cef41d95740600.png)

   ![25f75f5c36085e76.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/25f75f5c36085e76.png)

   ```
   <style name="Widget.TipTime.CompoundButton.RadioButton"parent="Widget.MaterialComponents.CompoundButton.RadioButton">   <item name="android:paddingStart">8dp</item>   <item name="android:textAppearance">?attr/textAppearanceBody1</item></style>
   ```

   

8. （可选）创建 `dimens.xml` 文件以提高常用值的可管理性。您可以采用与创建上述 `styles.xml` 文件相同的方式创建文件。选择值目录，右键点击并依次选择 **New > Values Resource File**。

在这个小型应用中，您重复进行了两次最小高度设置。目前这完全是可管理的，但如果有 4 个、6 个、10 个或更多的组件共用一个值，这就会变得难以掌控。记住分别更改所有组件非常乏味且容易出错。您可以在 **res > values** 中再创建一个名为 `dimens.xml` 的实用资源文件，用于存储您可以命名的常见维度。通过将常用值标准化为命名维度，可以更轻松地管理应用。TipTime 很小，所以我们不会在这个可选步骤之外使用它。不过，对于您可能会与设计团队合作处理的生产环境中的更复杂应用，您可以借助 `dimens.xml` 更频繁地轻松更改这些值。

```
dimens.xml<resources>   <dimen name="min_text_height">48dp</dimen></resources>
```

您将更新 `styles.xml` 文件以使用 `@dimen/min_text_height`，而不是直接使用 `48dp`。

```
...<style name="Widget.TipTime.TextView" parent="Widget.MaterialComponents.TextView">    <item name="android:minHeight">@dimen/min_text_height</item>    <item name="android:gravity">center_vertical</item>    <item name="android:textAppearance">?attr/textAppearanceBody1</item></style>...
```



#### 向您的主题添加这些样式

您可能已经注意到，您还未将新的 `RadioButton` 和 `Switch` 样式应用到相应的微件。原因在于，您将使用主题属性在应用主题中设置 `radioButtonStyle` 和 `switchStyle`。我们再来回顾一下什么是主题。

[主题](https://medium.com/androiddevelopers/android-styling-themes-vs-styles-ebe05f917578)是命名资源（称为主题属性）的集合，以后可在样式、布局等中加以引用。您可以为整个应用、activity 或视图层次结构指定主题，而不仅仅是针对单个 `View.` 指定主题。之前，您已通过设置主题属性（例如 `colorPrimary` 和 `colorSecondary`）在 `themes.xml` 中修改应用的主题，更改后的主题将在整个应用及其组件中使用。

`radioButtonStyle` 和 `switchStyle` 是您可以设置的其他主题属性。您为这些主题属性提供的样式资源将应用到每个单选按钮以及相应主题所适用的视图层次结构中的每个开关。

此外，还有适用于 `textInputStyle` 的主题属性，其中指定的样式资源将应用于应用中的所有文本输入字段。如需使 `TextInputLayout` 看起来像一个框状文本字段（如 Material Design 准则中所示），可使用 MDC 库中定义为 `Widget.MaterialComponents.TextInputLayout.OutlinedBox` 的 `OutlinedBox` 样式。以下是您将使用的样式。

![b00a91da56e6f6e2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/b00a91da56e6f6e2.png)

1. 修改 `themes.xml` 文件，以使主题引用所需的样式。设置主题属性的方式与在之前的一个 Codelab 中声明 `colorPrimary` 和 `colorSecondary` 主题属性的方式相同。但此次，相关主题属性是 `textInputStyle`、`radioButtonStyle` 和 `switchStyle`。您将使用您之前为 `RadioButton` 和 `Switch` 创建的样式以及 Material `OutlinedBox` 文本字段的样式。

   

   将以下内容复制到 `res/values/themes.xml` 内应用主题的样式标记中。

   ```
   <item name="textInputStyle">@style/Widget.MaterialComponents.TextInputLayout.OutlinedBox</item><item name="radioButtonStyle">@style/Widget.TipTime.CompoundButton.RadioButton</item><item name="switchStyle">@style/Widget.TipTime.CompoundButton.Switch</item>
   ```

   

2. 您的 `res/values/themes.xml` 文件看起来应如下所示。您可以根据需要在 XML 中添加注释（使用 `<!-` 和 `-->` 表示）。

   ```
   <resources xmlns:tools="http://schemas.android.com/tools">    <!-- Base application theme. -->    <style name="Theme.TipTime" parent="Theme.MaterialComponents.DayNight.DarkActionBar">        ...        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>        <!-- Text input fields -->        <item name="textInputStyle">@style/Widget.MaterialComponents.TextInputLayout.OutlinedBox</item>        <!-- Radio buttons -->        <item name="radioButtonStyle">@style/Widget.TipTime.CompoundButton.RadioButton</item>        <!-- Switches -->        <item name="switchStyle">@style/Widget.TipTime.CompoundButton.Switch</item>    </style></resources>
   ```

   

3. 务必对 **themes.xml (night)** 中的深色主题进行同样的更改。您的 `res/values-night/themes.xml` 文件看起来应如下所示：

   ```
   <resources xmlns:tools="http://schemas.android.com/tools">    <!-- Application theme for dark theme. -->    <style name="Theme.TipTime" parent="Theme.MaterialComponents.DayNight.DarkActionBar">        ...        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>        <!-- Text input fields -->        <item name="textInputStyle">@style/Widget.MaterialComponents.TextInputLayout.OutlinedBox</item>        <!-- For radio buttons -->        <item name="radioButtonStyle">@style/Widget.TipTime.CompoundButton.RadioButton</item>        <!-- For switches -->        <item name="switchStyle">@style/Widget.TipTime.CompoundButton.Switch</item>    </style></resources>
   ```

   

4. 运行应用并查看更改。文本字段的 `OutlinedBox` 样式看起来更加美观，并且所有文本现在看起来都是一致的！

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/31ac15991713b031.png" alt="31ac15991713b031.png" style="zoom:50%;" />   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/3e861407146c9ed4.png" alt="3e861407146c9ed4.png" style="zoom:50%;" />





## 8. 提升用户体验

即将完成应用修改时，您不仅应使用预期的工作流测试您的应用，还应在其他用户场景中进行测试。您可能会发现，对代码进行一些细微更改，就能极大地改善用户体验。

### ①旋转设备

1. 将您的设备旋转为横屏模式您可能需要先启用**自动旋转**设置。（该设置位于设备的[**快速设置**](https://support.google.com/android/answer/9083864?hl=zh-CN)或**设置 > 显示 > 高级 > 自动旋转屏幕**选项下）。

   

   ![f2edb1ae9926d5f1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/f2edb1ae9926d5f1.png)

   然后，在模拟器中，您可以使用模拟器选项（位于设备右上角）来将屏幕向右或向左旋转。

   ![da8aee11166adf41.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/da8aee11166adf41.png)

   

2. 您会注意到，某些界面组件（包括 **CALCULATE** 按钮）会被截断。这样显然会阻止您使用该应用！

   

   ![d73499f9c9d2b330.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/d73499f9c9d2b330.png)

3. 如需解决此错误，请在 `ConstraintLayout` 周围添加一个 `ScrollView`。您的 XML 看起来大致如下。

   ```
   <ScrollView   xmlns:android="http://schemas.android.com/apk/res/android"   xmlns:app="http://schemas.android.com/apk/res-auto"   xmlns:tools="http://schemas.android.com/tools"   android:layout_height="match_parent"   android:layout_width="match_parent">   <androidx.constraintlayout.widget.ConstraintLayout       android:layout_width="match_parent"       android:layout_height="wrap_content"       android:padding="16dp"       tools:context=".MainActivity">       ...   </ConstraintLayout></ScrollView>
   ```

   

4. 再次运行并测试应用。将设备旋转为横屏模式时，您应该可以滚动界面来访问“CALCULATE”按钮并查看小费结果。此修复不仅适用于横屏模式，也适用于其他可能具有不同维度的 Android 设备。现在，无论设备屏幕尺寸如何，用户都可以滚动布局。





### ②按下 Enter 键时隐藏键盘

您可能已经注意到，输入服务费用后，键盘始终保持显示状态。为了更好地访问“CALCULATE”按钮，每次都需要手动隐藏键盘，这样有点麻烦。相反，应使键盘在按 Enter 键时自动隐藏。

![e2c3a3dbc40218a2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/e2c3a3dbc40218a2.png)

对于文本字段，您可以定义键监听器，以便在点按某些键时响应事件。键盘上每个可能的输入选项都包含一个与之关联的按键代码，包括 `Enter` 键。请注意，屏幕键盘也称为软键盘，与实体键盘不同。

![1c95d7406d3847fe.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/1c95d7406d3847fe.png)

在此任务中，在文本字段上设置键监听器，以在按下 `Enter` 键时监听。检测到该事件后，隐藏键盘。

1. 复制此辅助方法并将其粘贴到 `MainActivity` 类中。您可以将其插入到 `MainActivity` 类的右大括号前面。`handleKeyEvent()` 是一个私有辅助函数，用于在 `keyCode` 输入参数等于 `KeyEvent.``KEYCODE_ENTER` 时隐藏屏幕键盘。[InputMethodManager](https://developer.android.com/reference/android/view/inputmethod/InputMethodManager) 用于控制是显示还是隐藏软键盘，并且允许用户选择显示哪一个软键盘。如果键事件处理成功，此方法会返回 true，否则返回 false。

   ```
   MainActivity.ktprivate fun handleKeyEvent(view: View, keyCode: Int): Boolean {   if (keyCode == KeyEvent.KEYCODE_ENTER) {       // Hide the keyboard       val inputMethodManager =           getSystemService(Context.INPUT_METHOD_SERVICE) as InputMethodManager       inputMethodManager.hideSoftInputFromWindow(view.windowToken, 0)       return true   }   return false}
   ```

   

2. 现在，在 `TextInputEditText` 微件上附加一个键监听器。记住，您可以通过绑定对象 `binding.costOfServiceEditText.` 访问 `TextInputEditText` 微件。

   在 `costOfServiceEditText` 上调用 [`setOnKeyListener()`](https://developer.android.com/reference/kotlin/android/view/View#setOnKeyListener(android.view.View.OnKeyListener)) 方法并传入 `OnKeyListener`。这类似于使用 `binding.calculateButton.setOnClickListener { calculateTip() }.` 在应用中为“CALCULATE”按钮设置点击监听器的方式。

   在视图上设置键监听器的代码稍微复杂一些，但一般思路是，[`OnKeyListener`](https://developer.android.com/reference/kotlin/android/view/View.OnKeyListener) 有一个 `onKey()` 方法，该方法在按下按键时触发。`onKey()` 方法需要 3 个输入参数：视图、按下的按键的代码以及按键事件（您不会使用该按键事件，因此可以将之命名为“`_`”）。调用 `onKey()` 方法时，应调用 `handleKeyEvent()` 方法并传递视图参数和按键代码参数。编写此代码的语法为：`view, keyCode, _ -> handleKeyEvent(view, keyCode).`。实际上，该语法称为 lambda 表达式，在后续单元中，您将详细了解 lambda。

   添加相应代码，以在 activity 的 `onCreate()` 方法内的文本字段中设置键监听器。这是因为创建布局后，您需要在用户开始与 activity 交互之前附加键监听器。

   ```
   MainActivity.ktoverride fun onCreate(savedInstanceState: Bundle?) {   ...   setContentView(binding.root)   binding.calculateButton.setOnClickListener { calculateTip() }   binding.costOfServiceEditText.setOnKeyListener { view, keyCode, _ -> handleKeyEvent(view, keyCode)   }}
   ```

   

3. 测试新更改是否有效。运行应用并输入服务费用。按键盘上的 Enter 键，这样软键盘应该会隐藏。



### ③在启用 TalkBack 的情况下测试您的应用

基于您在本课程中学到的内容，您希望构建可供尽可能多的用户访问的应用。有些用户可能会使用 [TalkBack](https://support.google.com/accessibility/android/answer/6283677?hl=zh-CN) 访问您的应用并在其中导航。TalkBack 是 Android 设备随附的 Google 屏幕阅读器。TalkBack 会为您提供语音反馈，这样即使您不看屏幕也能轻松使用设备。

启用 TalkBack 后，请确保用户可以完成应用中计算小费的用例。

1. 按照这些[说明](https://support.google.com/accessibility/android/answer/6007100)在您的设备上启用 TalkBack。
2. 返回 **Tip Time** 应用。
3. 按照这些[说明](https://developer.android.com/guide/topics/ui/accessibility/testing#explore_your_app_with_talkback)，通过 TalkBack 探索您的应用。向右滑动可按顺序浏览屏幕元素，向左滑动即可按相反顺序浏览。点按任意位置两次即可选择。确认您可以通过滑动手势访问应用的所有元素。
4. 确保 TalkBack 用户能够导航到屏幕上的每一项，输入服务费用，更改小费选项，计算小费，以及听到播报的小费。请注意，不会为图标提供语音反馈，因为您已将这些图标标记为 `importantForAccessibility="no"`。

如需详细了解如何进一步减少您的应用使用障碍，请参阅这些[原则](https://developer.android.com/guide/topics/ui/accessibility/principles)。



### （可选）调整矢量可绘制对象的色调

在这一可选任务中，您将根据主题主色对图标进行色调调节，以使图标在浅色主题下与深色主题下有所不同（如下所示）。此更改是对界面的完美补充，使得图标与应用主题更统一。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/77092f702beb1cfb.png" alt="77092f702beb1cfb.png" style="zoom:50%;" />         <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/80a390087905eb29.png" alt="80a390087905eb29.png" style="zoom:50%;" />

正如我们在前文提到的那样，`VectorDrawables` 与位图图像相比有一个优势：即可以对图标进行缩放和色调调节。下面是表示铃铛图标的 XML。需要注意两个不同的颜色属性：`android:tint` 和 `android:fillColor`。

```
ic_service.xml<vector xmlns:android="http://schemas.android.com/apk/res/android"   android:width="24dp"   android:height="24dp"   android:viewportWidth="24"   android:viewportHeight="24"   android:tint="?attr/colorControlNormal"> <path     android:fillColor="@android:color/white"     android:pathData="M2,17h20v2L2,19zM13.84,7.79c0.1,-0.24 0.16,-0.51 0.16,-0.79 0,-1.1 -0.9,-2 -2,-2s-2,0.9 -2,2c0,0.28 0.06,0.55 0.16,0.79C6.25,8.6 3.27,11.93 3,16h18c-0.27,-4.07 -3.25,-7.4 -7.16,-8.21z"/></vector>
```

![bdddc76d0ca06573.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/bdddc76d0ca06573.png)

如果存在着色，它将覆盖可绘制对象的所有 `fillColor` 指令。在此例中，白色会被 `colorControlNormal` 主题属性覆盖。`colorControlNormal` 是微件正常状态（未选中/未激活状态）的颜色。目前是灰色。

我们可以对应用进行的一种视觉增强操作是根据应用主题主色对可绘制对象进行色调调节。对于浅色主题，该图标将会显示为 `@color/green`；而在深色主题下，该图标将显示为 `@color/green_light`，即 `?attr/colorPrimary`。根据应用主题主色对可绘制对象进行色调调节可以使布局中的元素显得更加统一和连贯。这也使我们不必复制浅色主题和深色主题的图标集。只有 1 组矢量可绘制对象，且色调将根据 `colorPrimary` 主题属性而变化。

更改 `ic_service.xml` 中 `android:tint` 属性的值

```
android:tint="?attr/colorPrimary"
```

在 Android Studio 中，该图标现在将显示正确的色调。

![148a05c44b515c25.png](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience/img/148a05c44b515c25.png)

`colorPrimary` 主题属性所指向的值因浅色与深色主题而异。

重复此操作，以更改其他矢量可绘制对象的色调。

```
ic_store.xml<vector ...   android:tint="?attr/colorPrimary">   ...</vector>ic_round_up.xml<vector ...   android:tint="?attr/colorPrimary">   ...</vector>
```

1. 运行应用。验证图标在浅色和深色主题中是否显示不同。
2. 在最后的清理步骤中，请记得重新格式化应用中的所有 XML 和 Kotlin 代码文件。

恭喜！您已完成小费计算器应用的构建！您一定对您构建的内容十分自豪吧。希望这会为您奠定基础，助力您构建更美观、功能更强大的应用！

## 9 (6-8小结)

- 尽可能使用 Material Design 组件，以便遵循 Material Design 准则并实现更多自定义功能。
- 添加图标以便用户以直观的方式了解应用的各个部分如何工作。
- 使用 `ConstraintLayout` 可以确定元素在布局中的位置。
- 测试应用在各种极端情况下的情形（例如在横屏模式下旋转应用），并根据需要进行改进。
- 对您的代码添加注释，帮助阅读代码的其他人了解您的方法。
- 重新格式化您的代码并清理代码，以使其尽可能简洁。



## 10 在 Kotlin 中使用列表

### ①列表简介

在之前的 Codelab 中，您已经了解了 Kotlin 中的基本数据类型（例如 `Int`、`Double`、`Boolean` 和 `String`）。利用它们可以在变量中存储某种类型的值。但是，如果您想存储多个值，该怎么办？这便是 `List` 数据类型的用武之地。

列表是指按特定顺序排列的项的集合。Kotlin 中有两种类型的列表：

- 只读列表：`List` 一经创建便无法再修改。
- 可变列表：`MutableList` 创建之后可以进行修改，这意味着您可以添加、移除或更新其元素。

使用 `List` 或 `MutableList` 时，您必须指定它可以包含的元素类型。例如，`List<Int>` 可存储整数列表，而 `List<String>` 则可存储字符串列表。如果您在程序中定义了 `Car` 类，就可以创建 `List<Car>` 用于存储 `Car` 对象实例列表。

了解列表的最佳方式就是尝试使用它们。

```
val numbers: List<Int> = listOf(1, 2, 3, 4, 5, 6)
```



**访问列表元素**

列表特有的功能是，您可以根据索引（一个表示元素位置的整数）访问列表中的每个元素。下面是我们创建的 `numbers` 列表的示意图，其中显示了每个元素及其相应的索引。

![cb6924554804458d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-lists/img/cb6924554804458d.png)

索引实际上是相对于首个元素的偏移量。比如，当您输入 `list[2]` 时，您不是在请求列表中的第二个元素，而是在请求相对于首个元素偏移 2 个位置的元素。因此，`list[0]` 表示首个元素（零偏移），`list[1]` 表示第二个元素（偏移量为 1），`list[2]` 表示第三个元素（偏移量为 2），以此类推。

将以下代码添加到 `main()` 函数中现有代码之后。执行完每个步骤之后都运行一下代码，以便验证输出内容是否符合您的预期。

1. 输出列表中位于索引 0 处的首个元素。您可以使用所需的索引调用 `get()` 函数（如 `numbers.get(0)`）；或者，您也可以使用简写语法，用方括号将索引括起来（如 `numbers[0]`）。

   ```
   println("First element: ${numbers[0]}")
   ```

2. 接下来，输出列表中位于索引 1 处的第二个元素。

   ```
   println("Second element: ${numbers[1]}")
   ```

   列表的有效索引值（“索引”）从 0 开始，到最后一个索引（即列表的大小减 1）结束。这就表示，您的 `numbers` 列表的索引为 0 到 5。

3. 输出列表的最后一个元素，可以通过 `numbers.size - 1` 来计算其索引，得出的结果应为 `5`。访问位于第 5 个索引处的元素应返回 `6` 作为输出。

   ```
   println("Last index: ${numbers.size - 1}")println("Last element: ${numbers[numbers.size - 1]}")
   ```

   

4. Kotlin 还支持对列表执行 `first()` 和 `last()` 操作。尝试调用 `numbers.first()` 和 `numbers.last()`，并查看输出结果。

   ```
   println("First: ${numbers.first()}")println("Last: ${numbers.last()}")
   ```

   您会看到，`numbers.first()` 返回列表的首个元素，而 `numbers.last()` 返回列表的最后一个元素。

5. 另一个实用的列表操作是 `contains()` 方法，它可以查明指定的元素是否在列表中。例如，如果您有一份公司员工姓名列表，您可以使用 `contains()` 方法来查明指定的姓名是否在列表中。

   在 `numbers` 列表中，使用列表中的某个整数调用 `contains()` 方法。`numbers.contains(4)` 会返回值 `true`。然后，使用不在列表中的某个整数调用 `contains()` 方法。`numbers.contains(7)` 会返回 `false`。

   ```
   println("Contains 4? ${numbers.contains(4)}")println("Contains 7? ${numbers.contains(7)}")
   ```

6. 完成后的代码应如下所示。注释为可选。

   ```
   fun main() {    val numbers = listOf(1, 2, 3, 4, 5, 6)    println("List: $numbers")    println("Size: ${numbers.size}")    // Access elements of the list    println("First element: ${numbers[0]}")    println("Second element: ${numbers[1]}")    println("Last index: ${numbers.size - 1}")    println("Last element: ${numbers[numbers.size - 1]}")    println("First: ${numbers.first()}")    println("Last: ${numbers.last()}")    // Use the contains() method    println("Contains 4? ${numbers.contains(4)}")    println("Contains 7? ${numbers.contains(7)}")}
   ```

7. 运行您的代码。输出如下所示。

   ```
   List: [1, 2, 3, 4, 5, 6]Size: 6First element: 1Second element: 2Last index: 5Last element: 6First: 1Last: 6Contains 4? trueContains 7? false
   ```

   

**列表是只读的**

1. 删除 Kotlin 园地中的代码，并替换为以下代码。`colors` 列表被初始化为以 `Strings` 形式表示的 3 种颜色的列表。

   ```
   fun main() {    val colors = listOf("green", "orange", "blue")}
   ```

   

2. 请记住，您不能在只读 `List` 中添加或更改元素。我们来看看，如果您尝试向列表中添加项，或者通过将列表中的某个元素设置为新值来修改该元素，会发生什么。

   ```
   colors.add("purple")colors[0] = "yellow"
   ```

   

3. 运行代码，您会收到多条错误消息。实质上，这些错误的意思就是 `add()` 方法不适用于 `List`，您不能更改元素的值。

   ![dd21aaccdf3528c6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-lists/img/dd21aaccdf3528c6.png)

4. 移除错误的代码。

   您已经亲眼看到，无法更改只读列表。不过，有一些列表操作虽然不会更改列表，但会返回新的列表。`reversed()` 和 `sorted()` 就是其中的两个操作。`reversed()` 函数会返回一个元素按照倒序排列的新列表；而 `sorted()` 函数则会返回一个元素按照升序排列的新列表。

5. 添加代码，以使 `colors` 列表按照倒序排列。输出结果。这是一个新列表，其中包含按照倒序排列的 `colors` 的元素。

6. 添加第二行代码，以输出原始的 `list` 列表，这样您就可以看到原始列表并未更改。

   ```
   println("Reversed list: ${colors.reversed()}")println("List: $colors")
   ```

7. 以下便是输出的两个列表。

   ```
   Reversed list: [blue, orange, green]List: [green, orange, blue]
   ```

8. 添加代码，以使用 [`sorted()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/sorted.html) 函数返回按照升序排列的 `List`。

   ```
   println("Sorted list: ${colors.sorted()}")
   ```

   输出结果为按照字母顺序排列的新颜色列表。棒极了！

   ```
   Sorted list: [blue, green, orange]
   ```

   

9. 您还可以尝试对未排序的数字列表使用 `sorted()` 函数。

   ```
   val oddNumbers = listOf(5, 3, 7, 1)println("List: $oddNumbers")println("Sorted list: ${oddNumbers.sorted()}")List: [5, 3, 7, 1]Sorted list: [1, 3, 5, 7]
   ```

**注意**：您不用记住所有可能的列表操作。在 Android Studio 中开发应用时，如果您使用列表和其他数据类型，Android Studio 会向您显示适用于这些数据类型的函数和属性，如以下屏幕截图中所示。

![eb91ba297431db0d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-lists/img/eb91ba297431db0d.png)

现在，您已经明白了能够创建列表的好处。不过，如果在创建列表后可以对其进行修改就更棒了，因此，接下来我们来了解可变列表。



### ②可变列表简介

可变列表是指在创建后可以修改的列表。您可以添加、移除或更改其中的项。同时还可以执行可对只读列表执行的所有操作。可变列表的类型为 [`MutableList`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-list/)，您可以通过调用 [`mutableListOf()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/mutable-list-of.html) 来创建此类列表。



**创建 MutableList**

1. 删除 `main()` 中的现有代码。

2. 在 `main()` 函数中，创建一个空的可变列表，并将其赋值给名为 `entrees` 的 `val` 变量。

   ```
   val entrees = mutableListOf()
   ```

   如果您尝试运行代码，会出现以下错误。

   ```
   Not enough information to infer type variable T
   ```

   如前所述，当您创建 `MutableList` 或 `List` 时，Kotlin 会尝试根据传递的参数来推断列表包含的元素的类型。例如，如果您编写 `listOf("noodles")`，Kotlin 会推断出您想要创建一个 `String` 列表。在初始化没有元素的空列表时，Kotlin 无法推断元素类型，因此您必须明确指定类型。为此，您可以在 `mutableListOf` 或 `listOf` 后的尖括号内添加相应类型。（在[文档](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/mutable-list-of.html)中，您可能会看到这显示为 `<T>`，其中 `T` 代表类型参数）。

3. 更正变量声明，指明您想要创建一个 `String` 类型的可变列表。

   ```
   val entrees = mutableListOf<String>()
   ```

   另一种更正此错误的方法是，预先指定变量的数据类型。

   ```
   val entrees: MutableList<String> = mutableListOf()
   ```

   **注意**：您可以为可变列表使用 `val`，因为 `entrees` 变量包含对列表的引用，即使列表内容发生变化，该引用也会保持不变。

4. 输出列表。

   ```
   println("Entrees: $entrees")
   ```

5. 输出会显示 `[]`，表示列表为空。

   ```
   Entrees: []
   ```



#### Ⅰ向列表中添加元素

当您添加、移除和更新元素时，可变列表会变得很有趣。

1. 通过 `entrees.add("noodles").` 将 `"noodles"` 添加到列表中。如果成功将该元素添加到列表中，[`add()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-list/add.html) 函数会返回 `true`；否则，返回 `false`。

2. 输出列表，以确认已成功添加 `"noodles"`。

   ```
   println("Add noodles: ${entrees.add("noodles")}")println("Entrees: $entrees")
   ```

   输出结果如下：

   ```
   Add noodles: trueEntrees: [noodles]
   ```

3. 将另一个项 `"spaghetti"` 添加到列表中。

   ```
   println("Add spaghetti: ${entrees.add("spaghetti")}")println("Entrees: $entrees")
   ```

   生成的 `entrees` 列表现在包含两个项。

   ```
   Add spaghetti: trueEntrees: [noodles, spaghetti]
   ```

   您可以不使用 `add()` 逐个添加元素，而使用 [`addAll()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-list/add-all.html) 一次添加多个元素，并将其传递到列表中。

4. 创建一个 `moreItems` 列表。您不需要更改此列表，因此可将其设置为 `val` 且不可变。

   ```
   val moreItems = listOf("ravioli", "lasagna", "fettuccine")
   ```

5. 使用 `addAll()`，将新列表中的所有项添加到 `entrees` 中。输出生成的列表。

   ```
   println("Add list: ${entrees.addAll(moreItems)}")println("Entrees: $entrees")
   ```

   输出结果显示列表添加成功。`entrees` 列表现在共包含 5 个项。

   ```
   Add list: trueEntrees: [noodles, spaghetti, ravioli, lasagna, fettuccine]
   ```

6. 现在，尝试向此列表中添加一个数字。

   ```
   entrees.add(10)
   ```

   此操作失败，并显示以下错误：

   ```
   The integer literal does not conform to the expected type String
   ```

   这是因为 `entrees` 列表需要的是 `String` 类型的元素，而您试图添加 `Int` 类型的元素。请记住，只能向列表中添加正确数据类型的元素，否则会出现编译错误。这是 Kotlin 通过类型安全确保代码更加安全的一种方法。

7. 移除错误的代码行，以便代码能够正常编译。

#### Ⅱ从列表中移除元素

1. 调用 [`remove()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-list/remove.html) 以便从列表中移除 `"spaghetti"`。再次输出列表。

   ```
   println("Remove spaghetti: ${entrees.remove("spaghetti")}")println("Entrees: $entrees")
   ```

2. 移除 `"spaghetti"` 会返回 true，因为该元素存在于列表中，可以成功移除。该列表现在只剩下 4 个项。

   ```
   Remove spaghetti: trueEntrees: [noodles, ravioli, lasagna, fettuccine]
   ```

3. 如果尝试移除列表中不存在的项，会发生什么？尝试使用 `entrees.remove("rice")` 从列表中移除 `"rice"`。

   ```
   println("Remove item that doesn't exist: ${entrees.remove("rice")}")println("Entrees: $entrees")
   ```

   `remove()` 方法会返回 `false`，因为该元素不存在，因此无法移除。列表保持不变，仍然只有 4 个项。输出结果如下：

   ```
   Remove item that doesn't exist: falseEntrees: [noodles, ravioli, lasagna, fettuccine]
   ```

4. 您还可以指定要移除的元素的索引。使用 [`removeAt()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-list/remove-at.html) 移除位于索引 `0` 处的项。

   ```
   println("Remove first element: ${entrees.removeAt(0)}")println("Entrees: $entrees")
   ```

   `removeAt(0)` 的返回值为已从列表中移除的首个元素 (`"noodles"`)。`entrees` 列表现在剩下 3 个项。

   ```
   Remove first element: noodlesEntrees: [ravioli, lasagna, fettuccine]
   ```

5. 如果要清除整个列表，您可以调用 [`clear()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-list/clear.html)。

   ```
   entrees.clear()println("Entrees: $entrees")
   ```

   输出结果现在显示了一个空列表。

   ```
   Entrees: []
   ```

6. Kotlin 提供了 [`isEmpty()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-collection/is-empty.html) 函数来检查列表是否为空。请尝试输出 `entrees.isEmpty().`

   ```
   println("Empty? ${entrees.isEmpty()}")
   ```

   输出结果应为 true，因为列表当前为空，没有任何元素。

   ```
   Empty? true
   ```

   如果您想要对列表执行某项操作或访问某个元素，但需要先确认列表不为空，`isEmpty()` 方法就会非常有用。

以下是您针对可变列表编写的所有代码。注释为可选。

```
fun main() {    val entrees = mutableListOf<String>()    println("Entrees: $entrees")    // Add individual items using add()    println("Add noodles: ${entrees.add("noodles")}")    println("Entrees: $entrees")    println("Add spaghetti: ${entrees.add("spaghetti")}")    println("Entrees: $entrees")    // Add a list of items using addAll()    val moreItems = listOf("ravioli", "lasagna", "fettuccine")    println("Add list: ${entrees.addAll(moreItems)}")    println("Entrees: $entrees")    // Remove an item using remove()    println("Remove spaghetti: ${entrees.remove("spaghetti")}")    println("Entrees: $entrees")    println("Remove item that doesn't exist: ${entrees.remove("rice")}")    println("Entrees: $entrees")    // Remove an item using removeAt() with an index    println("Remove first element: ${entrees.removeAt(0)}")    println("Entrees: $entrees")    // Clear out the list    entrees.clear()    println("Entrees: $entrees")    // Check if the list is empty    println("Empty? ${entrees.isEmpty()}")}
```



### ③循环遍历列表

如需对列表中的每个项执行操作，您可以循环遍历该列表（也称为“遍历列表”）。循环可用于 `Lists` 和 `MutableLists`。



#### Ⅰ  **While 循环**

有一种类型的循环是 [`while`](https://kotlinlang.org/docs/reference/control-flow.html#while-loops) 循环。在 Kotlin 中，`while` 循环以 `while` 关键字开头。这类循环包含一个代码块（位于大括号内），只要括号中的表达式为  true，该代码块就会反复不停地执行下去。为了防止代码永久执行下去（即无限循环），该代码块必须包含用于更改表达式的值的逻辑，以便表达式最终变为  false，进而停止执行循环。这时，您就可以退出 `while` 循环，并继续执行该循环之后的代码。

```
while (expression) {    // While the expression is true, execute this code block}
```

**注意**：`while` 循环不一定要包含列表（点击[此处](https://play.kotlinlang.org/byExample/02_control_flow/02_Loops)查看示例），但它对于列表来说非常有用。

使用 `while` 循环来遍历列表。创建一个变量来跟踪您当前在列表中查看的 `index`。您每查看一个元素，此 `index` 变量都会增加 1，直到达到列表的最后一个索引，然后您便会退出循环。

1. 删除 Kotlin 园地中的现有代码，然后您就会得到一个空的 `main()` 函数。

2. 假设您正在组织一场派对。创建一个列表，其中每个元素代表一个家庭回复的宾客人数。第一个家庭表示，他们家会有 2 人参加。第二个家庭表示，他们家会有 4 人参加；等等。

   ```
   val guestsPerFamily = listOf(2, 4, 1, 3)
   ```

3. 计算总共会有多少人参加派对。请编写一个循环来找到答案。针对宾客总数创建一个 `var`，并将其初始化为 `0`。

   ```
   var totalGuests = 0
   ```

4. 如前所述，初始化 `index` 变量的 `var`。

   ```
   var index = 0
   ```

5. 编写一个 `while` 循环，以遍历列表。条件是只要 `index` 值小于列表大小，便继续执行代码块。

   ```
   while (index < guestsPerFamily.size) {}
   ```

6. 在该循环中，会获取列表中位于当前 `index` 处的元素，并将其加到宾客总数变量中。请注意，`totalGuests += guestsPerFamily[index]` 与 `totalGuests = totalGuests + guestsPerFamily[index].` 的作用相同。

   请注意，循环的最后一行使用 `index++` 使 `index` 变量按 1 递增，以便循环的下一次迭代查看列表中的下一个家庭。

   ```
   while (index < guestsPerFamily.size) {    totalGuests += guestsPerFamily[index]    index++}
   ```

7. 在 `while` 循环之后，您可以输出结果。

   ```
   while ... {    ...}println("Total Guest Count: $totalGuests")
   ```

8. 运行程序，输出结果如下所示。您可以通过手动合计列表中的数字来验证输出的结果是否正确。

   ```
   Total Guest Count: 10
   ```

以下是完整的代码段：

```
val guestsPerFamily = listOf(2, 4, 1, 3)var totalGuests = 0var index = 0while (index < guestsPerFamily.size) {    totalGuests += guestsPerFamily[index]    index++}println("Total Guest Count: $totalGuests")
```

**注意**：对变量执行简单操作并将结果存回变量的做法很常见，于是我们针对此提供了简化的运算符，即 `+=`。对于减法、乘法和除法同样有这种简化的运算符，它们分别是：`-=`、`*=` 和 `/=`。有关更多详情，请点击[此处](https://kotlinlang.org/docs/reference/operator-overloading.html#assignments)。

使用 `while` 循环时，您必须编写代码来创建用于跟踪索引的变量、获取列表中位于相应索引处的元素，并更新该索引变量。遍历列表还有一种更加快速、简洁的方式，那就是使用 `for` 循环！



#### Ⅱ  **For 循环**

[`for`](https://kotlinlang.org/docs/reference/control-flow.html#for-loops) 循环是另一种类型的循环。它可以更轻松地遍历列表。在 Kotlin 中，这种循环以 `for` 关键字开头，其代码块含在大括号中。执行代码块的条件在圆括号中指定。

```
for (number in numberList) {   // For each element in the list, execute this code block}
```

在此示例中，变量 `number` 被设置为等于 `numberList` 的首个元素，并开始执行代码块。然后，`number` 变量自动更新为 `numberList` 的下一个元素，并再次执行代码块。这种操作会针对列表中的每个元素重复执行，直到达到 `numberList` 的末尾。

1. 删除 Kotlin 园地中的现有代码，并替换为以下代码：

   ```
   fun main() {    val names = listOf("Jessica", "Henry", "Alicia", "Jose")}
   ```

2. 添加一个 `for` 循环，以输出 `names` 列表中的所有项。

   ```
   for (name in names) {    println(name)}
   ```

   相对于必须用 `while` 循环编写，这种方法要简单得多！

3. 输出结果如下

   ```
   JessicaHenryAliciaJose
   ```

   一种常见的列表操作是对列表中的每个元素执行某种操作。

4. 修改循环，以同时输出人员姓名中包含的字符数。提示：您可以使用 `String` 的 [`length`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/length.html) 属性来确定该 `String` 中的字符数。

   ```
   val names = listOf("Jessica", "Henry", "Alicia", "Jose")for (name in names) {    println("$name - Number of characters: ${name.length}")}
   ```

   输出结果如下：

   ```
   Jessica - Number of characters: 7Henry - Number of characters: 5Alicia - Number of characters: 6Jose - Number of characters: 4
   ```

   循环中的代码并未更改原始 `List`，而只是影响了输出结果。

   您可以编定指令来指明应对 1 个列表项执行的操作，然后对每个列表项执行该代码，这种方法非常简洁！使用循环可避免输入大量重复的代码。

   

   **注意**：以下是关于使用 `for` 循环可以完成的操作的另一些示例，包括为它们指定范围以执行特定步骤（而不是每次递增 1）。

   ```
   for (item in list) print(item) // Iterate over items in a listfor (item in 'b'..'g') print(item) // Range of characters in an alphabetfor (item in 1..5) print(item) // Range of numbersfor (item in 5 downTo 1) print(item) // Going backwardfor (item in 3..6 step 2) print(item) // Prints: 35
   ```

   如需查看更多示例，请参阅本 Codelab 末尾列出的文档。

   

   **注意**：循环是一种控制流结构（就像您之前学习的 `if`/`else` 和 `when` 表达式一样），它指定了一个关于应如何执行代码的特定流程。

   

   以下是 `Item`、`Noodles`、`Vegetables` 和 `Order` 类的解决方案代码。`main()` 函数还展示了如何使用这些类。有多种方法可以实现此程序，因此您的代码有可能略有不同。

   ```
   open class Item(val name: String, val price: Int)class Noodles : Item("Noodles", 10) {    override fun toString(): String {        return name    }}class Vegetables(vararg val toppings: String) : Item("Vegetables", 5) {    override fun toString(): String {        if (toppings.isEmpty()) {            return "$name Chef's Choice"        } else {            return name + " " + toppings.joinToString()        }    }}class Order(val orderNumber: Int) {    private val itemList = mutableListOf<Item>()    fun addItem(newItem: Item): Order {        itemList.add(newItem)        return this    }    fun addAll(newItems: List<Item>): Order {        itemList.addAll(newItems)        return this    }    fun print() {        println("Order #${orderNumber}")        var total = 0        for (item in itemList) {            println("${item}: $${item.price}")            total += item.price        }        println("Total: $${total}")    }}fun main() {    val ordersList = mutableListOf<Order>()    // Add an item to an order    val order1 = Order(1)    order1.addItem(Noodles())    ordersList.add(order1)    // Add multiple items individually    val order2 = Order(2)    order2.addItem(Noodles())    order2.addItem(Vegetables())    ordersList.add(order2)    // Add a list of items at one time    val order3 = Order(3)    val items = listOf(Noodles(), Vegetables("Carrots", "Beans", "Celery"))    order3.addAll(items)    ordersList.add(order3)    // Use builder pattern    val order4 = Order(4)        .addItem(Noodles())        .addItem(Vegetables("Cabbage", "Onion"))    ordersList.add(order4)    // Create and add order directly    ordersList.add(        Order(5)            .addItem(Noodles())            .addItem(Noodles())            .addItem(Vegetables("Spinach"))    )    // Print out each order    for (order in ordersList) {        order.print()        println()    }}
   ```



### ④小结

Kotlin 提供了相关功能来帮助您通过 Kotlin  标准库更轻松地管理和操控数据集合。集合就是指具有相同数据类型的多个对象。Kotlin 中有几种不同的基本集合类型：列表、集和映射。本  Codelab 主要介绍了列表，在之后的 Codelab 中，您还将详细了解集和映射。

- 列表是特定类型元素的有序集合（例如 `Strings.` 列表）。
- 索引是反映元素位置的整数位置（例如 `myList[2]`）。
- 在列表中，首个元素位于索引 0 处（例如 `myList[0]`），最后一个元素位于索引 `myList.size-1` 处（例如 `myList[myList.size-1]` 或 `myList.last()`）。
- 有两种类型的列表：`List` 和 `MutableList.`
- `List` 是只读的，一但初始化就无法再修改。不过，您可以应用 `sorted()` 和 `reversed()` 等操作，这些操作可在不更改原始列表的情况下返回新的列表。
- `MutableList` 在创建后可以修改，例如添加、移除或修改元素。
- 您可以使用 `addAll()` 向可变列表添加一个项列表。
- 使用 `while` 循环可反复执行代码块，直到表达式的结果为 false 并退出循环。

```
while (expression) {// While the expression is true, execute this code block}
```

- 使用 `for` 循环可遍历列表中的所有项：

```
for (item in myList) {// Execute this code block for each element of the list}
```

- 利用 `vararg` 修饰符可向函数或构造函数传递可变数量的参数。



## 11 使用 RecyclerView 显示可滚动列表

### ①添加自我肯定话语字符串

1. 在 **Project** 窗口中，依次打开 **app > res > values > strings.xml**。此文件目前只有一个资源，即应用的名称。
2. 在 `strings.xml` 中，将以下自我肯定话语添加为单独的字符串资源。将其分别命名为 `affirmation1`、`affirmation2`，依此类推。

自我肯定话语的文字稿

```
I am strong.I believe in myself.Each day is a new opportunity to grow and be a better version of myself.Every challenge in my life is an opportunity to learn from.I have so much to be grateful for.Good things are always coming into my life.New opportunities await me at every turn.I have the courage to follow my heart.Things will unfold at precisely the right time.I will be present in all the moments that this day brings.
```

完成后，`strings.xml` 文件应如下所示。

```
<resources>    <string name="app_name">Affirmations</string>    <string name="affirmation1">I am strong.</string>    <string name="affirmation2">I believe in myself.</string>    <string name="affirmation3">Each day is a new opportunity to grow and be a better version of myself.</string>    <string name="affirmation4">Every challenge in my life is an opportunity to learn from.</string>    <string name="affirmation5">I have so much to be grateful for.</string>    <string name="affirmation6">Good things are always coming into my life.</string>    <string name="affirmation7">New opportunities await me at every turn.</string>    <string name="affirmation8">I have the courage to follow my heart.</string>    <string name="affirmation9">Things will unfold at precisely the right time.</string>    <string name="affirmation10">I will be present in all the moments that this day brings.</string></resources>
```

现在，您已添加了字符串资源，可以在代码中将其引用为 `R.string.affirmation1` 或 `R.string.affirmation2` 了。

### ②创建新软件包

按照逻辑组织代码可以帮助您和其他开发者理解、维护和扩展代码。就像您可以将文书整理成文件和文件夹一样，您同样可以将代码组织成文件和软件包。



**什么是软件包？**

1. 在 Android Studio 的 **Project** 窗口 (**Android**) 中，查看 **app > java** 下的 Affirmations 应用的新项目文件。它们应该与下面的屏幕截图相似。图中显示了三个软件包：一个用于您的代码 (**com.example.affirmations**)，另外两个用作测试文件

   （**com.example.affirmations (androidTest)** 和 **com.example.affirmations (test)**）。

   ![809a0d77a0759dc5.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/809a0d77a0759dc5.png)

2. 请注意，软件包的名称由几个单词组成，单词间以句点进行分隔。

   软件包的使用方式有两种。

   - 为代码的不同部分创建不同的软件包。例如，开发者通常会将处理数据的类和构建界面的类分成不同的软件包。
   - 在代码中使用来自其他软件包的代码。为了使用来自其他软件包的类，您需要在构建系统的依赖项中定义这些类。此外，使用 `import` 将其导入代码中也是一种标准做法。如此一来，您就可以使用这些类的简短名称（例如 `TextView`）而无需使用其完全限定名称（例如 `android.widget.TextView`）。举例来说，您已对 `sqrt` (`import kotlin.math.sqrt`) 和 `View` (`import android.view.View`) 等类使用过 `import` 语句。

   在 Affirmations 应用中，除了导入 Android 类和 Kotlin 类之外，您还需要将应用分为多个软件包。即使应用所用的类并不太多，最好也使用软件包将类按功能分组。

   

   **为软件包命名**

   您可以对软件包随意命名，只要是全局唯一名称即可；任何其他已发布的软件包都不能同名。由于已有软件包的数量非常庞大，要随机想出唯一的名称也非常困难；因此，为了更易于创建和理解软件包名称，编程人员遵循相应的命名惯例。

   - 软件包名称通常采用从一般到具体的结构，名称的每个部分均采用小写字母，各部分之间以句点分隔。重要提示：句点只是名称的组成部分。它既不表示代码中的层次结构，也并非一定要遵循某种文件夹结构！
   - 由于互联网域名具有全局唯一性，因此使用域名（通常是您的域名或您企业的域名）作为名称的第一个部分是一种惯例。
   - 您可以选择软件包的名称，用它来表示软件包的内容以及软件包彼此间的关系。
   - 对于我们此处所用的这种代码示例，`com.example` 后跟应用名称是常用的命名方式。

   以下是一些预定义软件包名称及其内容的示例：

   - `kotlin.math` - 数学函数和常量。
   - `android.widget` - 视图，例如 `TextView`。

   **注意**：虽然软件包的名称显示为层次结构，而且在 Android Studio 的 Android **Project** 窗口中也按照文件夹层次结构排列，但实际上可执行代码中并不存在层次结构。这就像图书馆虽然会采用编号系统对图书进行分类和整理，但图书仍在同一个书架上，您可以取出其中任意一本图书。

   

**创建软件包**

1. 在 Android Studio 的 **Project** 窗格中，右键点击 **app > java > com.example.affirmations**，然后依次选择 **New > Package**。

   ![39f35a81a574b7ee.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/39f35a81a574b7ee.png)

2. 在 **New Package** 弹出式窗口中，注意建议的软件包名称前缀。建议的软件包名称的第一个部分是右键点击的软件包的名称。虽然使用软件包名称不会创建一个软件包层次结构，但我们可以通过重复使用一部分名称来说明内容之间的关系及其组织方式！

3. 在弹出式窗口中，将 **model** 附加到建议的软件包名称末尾。开发者通常使用 **model** 作为对数据建模的类或表示数据的类的软件包名称。

   ![3d392f8da53adc6f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/3d392f8da53adc6f.png)

4. 按 **Enter** 键。系统将在 **com.example.affirmations**（根）软件包下创建一个新软件包。这个新软件包将包含应用中定义的任何与数据相关的类。

   

**创建 Affirmation 数据类**

在此任务中，您将创建一个名为 `Affirmation.` 的类。一个 `Affirmation` 对象实例代表一句自我肯定话语，并包含这句自我肯定话语字符串的资源 ID。

1. 右键点击 **com.example.affirmations.model** 软件包，然后依次选择 **New > Kotlin File/Class**。

   ![d9b07905f456ab1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/d9b07905f456ab1.png)

2. 在弹出式窗口中，选择 **Class**，然后输入 `Affirmation` 作为类的名称。系统将在 `model` 软件包中创建一个名为 `Affirmation.kt` 的新文件。

3. 在类定义前添加 `data` 关键字，使 `Affirmation` 成为数据类。这样做会出错，因为数据类必须至少定义一个属性。

   ```
   Affirmation.ktpackage com.example.affirmations.modeldata class Affirmation {}
   ```

   在创建 `Affirmation` 的实例时，您需要传入自我肯定话语字符串的资源 ID。资源 ID 是一个整数。

   

4. 将 `val` 整数参数 `stringResourceId` 添加到 `Affirmation` 类的构造函数中。这样就可以消除错误了。

```
package com.example.affirmations.modeldata class Affirmation(val stringResourceId: Int)
```



**创建要作为数据源的类**

应用中显示的数据可能来自不同的来源（例如，来自应用项目内，或者来自需要连接到互联网才能下载数据的外部来源）。因此，数据格式未必正好是您需要的格式。应用的其余部分本身不应该关心数据的来源或数据的原始格式。您可以也应该在单独的 `Datasource` 类中隐藏此数据准备工作，由该类来为应用准备数据。

准备数据是一项需要单独处理的工作，因此请将 `Datasource` 类放在单独的 **data** 软件包中。

1. 在 Android Studio 的 **Project** 窗口中，右键点击 **app > java > com.example.affirmations**，然后依次选择 **New > Package**。

2. 输入 `data` 作为软件包名称的最后一部分。

3. 右键点击 `data` 软件包，然后选择 **new Kotlin File/Class**。

4. 输入 `Datasource` 作为类名称。

5. 在 `Datasource` 类中，创建一个名为 `loadAffirmations()` 的函数。

   `loadAffirmations()` 函数需要返回 `Affirmations` 的列表。为此，您可以创建一个列表，并使用每个资源字符串的 `Affirmation` 实例填充该列表。

6. 将 `List<Affirmation>` 声明为 `loadAffirmations()` 方法的返回值类型。

7. 在 `loadAffirmations()` 的主体中，添加 `return` 语句。

8. 在 `return` 关键字之后，调用 `listOf<>()` 创建一个 `List`。

9. 在尖括号 `<>` 内，将列表项的类型指定为 `Affirmation`。根据需要导入 `com.example.affirmations.model.Affirmation`。

10. 在圆括号内创建 `Affirmation`，传入 `R.string.affirmation1` 作为资源 ID，如下所示。

    ```
    Affirmation(R.string.affirmation1)
    ```

11. 将其余 `Affirmation` 对象添加到所有自我肯定话语的列表，以英文逗号分隔。完成后的代码应如下所示。

    Datasource.kt

    ```
    package com.example.affirmations.dataimport com.example.affirmations.Rimport com.example.affirmations.model.Affirmationclass Datasource {    fun loadAffirmations(): List<Affirmation> {        return listOf<Affirmation>(            Affirmation(R.string.affirmation1),            Affirmation(R.string.affirmation2),            Affirmation(R.string.affirmation3),            Affirmation(R.string.affirmation4),            Affirmation(R.string.affirmation5),            Affirmation(R.string.affirmation6),            Affirmation(R.string.affirmation7),            Affirmation(R.string.affirmation8),            Affirmation(R.string.affirmation9),            Affirmation(R.string.affirmation10)        )    }}
    ```



**[可选] 在 TextView 中显示自我肯定话语列表的大小**

如需验证您能否创建自我肯定话语列表，您可以调用 `loadAffirmations()` 并在 Empty Activity 应用模板附带的 `TextView` 中显示返回的自我肯定话语列表的大小。

1. 在 `layouts/activity_main.xml` 中，为模板附带的 `TextView` 指定 `textview` 作为 `id`。

2. 在 `MainActivity` 中，在 `onCreate()` 方法中的现有代码之后，获取对 `textview` 的引用。

   ```
   val textView: TextView = findViewById(R.id.textview)
   ```

3. 然后，添加代码以创建自我肯定话语列表并显示其大小。创建一个 `Datasource`，调用 `loadAffirmations()`，获取返回的列表的大小并将其转换为字符串，然后将其指定为 `textView` 的 `text`。

   ```
   textView.text = Datasource().loadAffirmations().size.toString()
   ```

4. 运行应用。屏幕应如下所示。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/b4005973d4a0efc8.png" alt="b4005973d4a0efc8.png" style="zoom:50%;" />

5. 删除您刚在 `MainActivity` 中添加的代码。



### ③将 RecyclerView 添加到应用

在此任务中，您将设置一个 `RecyclerView` 来显示 `Affirmations` 的列表。

创建和使用 `RecyclerView` 需要编写许多代码段。您可以将其想象成劳动分工。下图所示为其概览，至于每段代码的详情，则有待您在实现过程中逐一了解。

- **列表项** - 要显示的列表的一个数据项。代表应用中的一个 `Affirmation` 对象。
- **Adapter** - 获取数据并准备数据以供 `RecyclerView` 显示。
- **ViewHolder** - 供 `RecyclerView` 用于和重用于显示自我肯定话语的视图池。
- **RecyclerView** - 屏幕上的视图。

![4e9c18b463f00bf7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/4e9c18b463f00bf7.png)



**将 RecyclerView 添加到布局中**

Affirmations 应用由一个名为 `MainActivity` 的 activity 及其名为 `activity_main`.`xml` 的布局文件组成。首先，您需要将 `RecyclerView` 添加到 `MainActivity` 的布局中。

1. 打开 `activity_main.xml` (**app > res > layout > activity_main.xml**)。

2. 切换到 **Split 视图**（如果您尚未使用该视图）。

   ![7e7c3e8429267dac.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/7e7c3e8429267dac.png)

3. 删除 `TextView`。

   当前布局使用的是 `ConstraintLayout`。如果想在布局中放置多个子视图，那么 `ConstraintLayout` 就是理想而又灵活的选择。不过，因为您的布局只有一个子视图 `RecyclerView`，所以您可以切换到更简单的名为 `FrameLayout` 的 `ViewGroup`，这才是只包含一个子视图时应该使用的选择。

   ![9e6f235be5fa31a8.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/9e6f235be5fa31a8.png)

4. 在 XML 文件中，将 `ConstraintLayout` 替换为 `FrameLayout`。完成后的布局应如下所示。

   ```
   activity_main.xml<?xml version="1.0" encoding="utf-8"?><FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    tools:context=".MainActivity"></FrameLayout>
   ```

5. 切换到 **Design** 视图。

6. 在 **Palette** 中，选择 **Containers**，然后找到 **RecyclerView**。

7. 将 **RecyclerView** 拖放到布局中。

8. 如果系统显示 **Add Project Dependency** 弹出式窗口，请阅读里面的内容并点击 **OK**。（如果未显示此弹出式窗口，无需执行任何操作。）

9. 等待 Android Studio 完成操作并且 `RecyclerView` 显示在布局中。

10. 根据需要将 `RecyclerView` 的 `layout_width` 和 `layout_height` 属性更改为 `match_parent`，以便 `RecyclerView` 能够填满整个屏幕。

11. 将 `RecyclerView` 的资源 ID 设为 `recycler_view`。

    `RecyclerView` 支持以线性列表或网格等不同方式显示列表项。列表项的排列由 `LayoutManager` 处理。Android 框架针对基本的列表项布局提供了布局管理器。Affirmations 应用以垂直列表的形式显示列表项，因此您可以使用 `LinearLayoutManager`。

12. 切换回 **Code** 视图。在 XML 代码中的 `RecyclerView` 元素内，添加 `LinearLayoutManager` 作为 `RecyclerView` 的布局管理器属性，如下所示。

    ```
    app:layoutManager="LinearLayoutManager"
    ```

    为了能够滚动浏览超出屏幕长度的垂直项目列表，您需要添加一个垂直滚动条。

13. 在 `RecyclerView` 内，添加设为 `vertical` 的 `android:scrollbars` 属性

    ```
    android:scrollbars="vertical"
    ```

    最终的 XML 布局应如下所示：

    ```
    activity_main.xml<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"    xmlns:app="http://schemas.android.com/apk/res-auto"    xmlns:tools="http://schemas.android.com/tools"    android:layout_width="match_parent"    android:layout_height="match_parent"    tools:context=".MainActivity">    <androidx.recyclerview.widget.RecyclerView        android:id="@+id/recycler_view"        android:layout_width="match_parent"        android:layout_height="match_parent"        android:scrollbars="vertical"        app:layoutManager="LinearLayoutManager" /></FrameLayout>
    ```

14. 运行应用。

项目应能不出任何问题地顺利编译和运行。不过，由于缺少一段重要代码，应用中只会显示白色背景。现在，您已将数据源和 `RecyclerView` 添加到布局中，但 `RecyclerView` 尚无有关如何显示 `Affirmation` 对象的信息。



### ④为 RecyclerView 实现 Adapter

应用需要通过某种方式从 `Datasource` 获取数据并为其设置格式，这样才能让每个 `Affirmation` 在 `RecyclerView` 中显示为一个列表项。

Adapter 是一种设计模式，可将数据调整为可供 `RecyclerView` 使用的内容。在本例中，您需要一个能完成以下任务的 Adapter：从 `loadAffirmations()` 返回的列表中获取 `Affirmation` 实例并将其转换为列表项视图，以便在 `RecyclerView.` 中显示它。

当您运行应用时，`RecyclerView` 会使用 Adapter 确定如何在屏幕上显示您的数据。`RecyclerView` 要求 Adapter 为列表中的第一个数据项创建新的列表项视图。有了此视图后，它会要求 Adapter 提供用于绘制该列表项的数据。此过程不断重复，直到 `RecyclerView` 不再需要更多视图来填满屏幕。如果屏幕上一次只能同时容纳 3 个列表项视图，那么 `RecyclerView` 只会要求 Adapter 准备这 3 个列表项视图（而不是全部 10 个列表项视图）。

在此步骤中，您将构建一个 Adapter，用于调整 `Affirmation` 对象实例，使其可在 `RecyclerView` 中显示。

#### Ⅰ  创建 Adapter

Adapter 包含多个部分，您需要编写大量代码，而且这些代码比您在本课程中迄今为止完成的代码更加复杂。如果您刚开始无法完全理解细节也没关系。当您完成使用 `RecyclerView` 的整个应用后，您就能更深入地了解各部分如何组合到一起了。今后，当您使用 `RecyclerView` 创建应用时，您还可以重复使用此代码作为基础。



**为列表项创建布局**

`RecyclerView` 中的每个列表项都有自己的布局，您可以在单独的布局文件中定义这些布局。由于您只需要显示字符串，因此可将 `TextView` 用于列表项布局。

1. 在 **res > layout** 中，新建名为 `list_item.xml` 的空 **File**。
2. 在 **Code** 视图中打开 `list_item.xml`。
3. 添加 `id` 为 `item_title` 的 `TextView`。
4. 针对 `layout_width` 和 `layout_height` 添加 `wrap_content`，如下面的代码所示。

请注意，您不需要对布局使用 `ViewGroup`，因为稍后我们会膨胀此列表项布局并将其作为子视图添加到父 `RecyclerView` 中。

```
list_item.xml<?xml version="1.0" encoding="utf-8"?><TextView xmlns:android="http://schemas.android.com/apk/res/android"    android:id="@+id/item_title"    android:layout_width="wrap_content"    android:layout_height="wrap_content" />
```

或者，您也可以使用 **File > New > Layout Resource File**，将 **File name** 设为 `list_item.xml`，并以 `TextView` 作为 **Root element**。然后，更新生成的代码以匹配上面的代码。

![dbb34ca516c804c6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/dbb34ca516c804c6.png)



#### Ⅱ  创建 ItemAdapter 类

1. 在 Android Studio 的 **Project** 窗格中，右键点击 **app > java > com.example.affirmations**，然后依次选择 **New > Package**。

2. 输入 `adapter` 作为软件包名称的最后一部分。

3. 右键点击 `adapter` 软件包，然后依次选择 **New > Kotlin File/Class**。

4. 输入 `ItemAdapter` 作为类名称，完成创建操作，系统将打开 `ItemAdapter.kt` 文件。

   您需要将一个参数添加到 `ItemAdapter` 的构造函数中，以便将自我肯定话语列表传入 Adapter。

5. 将一个参数添加到 `ItemAdapter` 的构造函数中，该参数是名为 `dataset`、类型为 `List<Affirmation>` 的 `val`。根据需要导入 `Affirmation`。

6. 由于 `dataset` 仅在此类中使用，因此请将其设为 `private`。

   ```
   ItemAdapter.ktimport com.example.affirmations.model.Affirmationclass ItemAdapter(private val dataset: List<Affirmation>) {}
   ```

   `ItemAdapter` 需要有关如何解析字符串资源的信息。这些信息与有关应用的其他信息一起存储在 `Context` 对象实例中，您可将此实例传入 `ItemAdapter` 实例。

7. 将一个参数添加到 `ItemAdapter` 的构造函数中，该参数是名为 `context`、类型为 `Context` 的 `val`。请将其作为构造函数中的第一个参数。

   ```
   class ItemAdapter(private val context: Context, private val dataset: List<Affirmation>) {}
   ```

#### Ⅲ  创建 ViewHolder

`RecyclerView` 不会直接与列表项视图交互，而是处理 `ViewHolders`。一个 `ViewHolder` 代表 `RecyclerView` 中的一个列表项视图，可根据需要对其重复使用。`ViewHolder` 实例存储着对列表项布局中各个视图的引用（因此被命名为“view holder”，意思是视图存储器）。这样，用新数据更新列表项视图就会更轻松。ViewHolder 还会添加一些信息，供 `RecyclerView` 用于在屏幕上高效移动视图。

1. 在 `ItemAdapter` 类中，在 `ItemAdapter` 的右花括号之前，创建一个 `ItemViewHolder` 类。

   ```
   class ItemAdapter(private val context: Context, private val dataset: List<Affirmation>) {    class ItemViewHolder()}
   ```

   - 在一个类中定义另一个类称为创建**嵌套类**。
   - 由于 `ItemViewHolder` 仅由 `ItemAdapter` 使用，因此在 `ItemAdapter` 内创建它可以显示此关系。这并非强制性要求，但这样做有助于其他开发者了解您的程序的结构。

2. 将类型为 `View` 的 `private` `val` `view` 作为参数添加到 `ItemViewHolder` 类构造函数。

3. 将 `ItemViewHolder` 设为 `RecyclerView`.`ViewHolder` 的子类，并将 `view` 参数传入父类构造函数。

4. 在 `ItemViewHolder` 内，定义类型为 `TextView` 的 `val` 属性 `textView`。为其分配您在 `list_item`.`xml` 中定义的 ID 为 `item_title` 的视图。

   ```
   class ItemAdapter(private val context: Context, private val dataset: List<Affirmation>) {    class ItemViewHolder(private val view: View) : RecyclerView.ViewHolder(view) {        val textView: TextView = view.findViewById(R.id.item_title)    }}
   ```

#### Ⅳ  替换 Adapter 方法

1. 添加代码以从抽象类 `RecyclerView.Adapter` 扩展您的 `ItemAdapter`。在尖括号中，将 `ItemAdapter.ItemViewHolder` 指定为 ViewHolder 类型。

   ```
   class ItemAdapter(    private val context: Context,    private val dataset: List<Affirmation>) : RecyclerView.Adapter<ItemAdapter.ItemViewHolder>() {    class ItemViewHolder(private val view: View) : RecyclerView.ViewHolder(view) {        val textView: TextView = view.findViewById(R.id.item_title)    }}
   ```

   您会看到一条错误消息，因为您需要从 `RecyclerView.Adapter` 实现一些抽象方法。

2. 将光标放在 `ItemAdapter` 上，然后按 **Command+I**（在 Windows 上，则请按 **Control+I**）。系统将列出您需要实现的方法：`getItemCount()`、`onCreateViewHolder()` 和 `onBindViewHolder()`。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/7a8a383a8633094b.png" alt="7a8a383a8633094b.png" style="zoom:50%;" />

3. 使用 **Shift+click** 将三个函数全部选中，然后点击 **OK**。

   这样就会使用正确的参数创建这三个方法的桩，如下所示。

   ```
   override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ItemViewHolder {    TODO("Not yet implemented")}override fun getItemCount(): Int {    TODO("Not yet implemented")}override fun onBindViewHolder(holder: ItemViewHolder, position: Int) {    TODO("Not yet implemented")}
   ```

   您应该不会再看到错误消息。接下来，您需要实现这些方法，使其能对您的应用正确发挥作用。

   

#### Ⅴ  实现 getItemCount()

`getItemCount()` 方法需要返回数据集的大小。应用的数据位于您传入 `ItemAdapter` 构造函数的 `dataset` 属性中，您可以使用 `size` 获取其大小。

将 `getItemCount()` 替换为：

```
override fun getItemCount(): Int {    return dataset.size}
```

下面是更简洁的编写方式：

```
override fun getItemCount() = dataset.size
```

#### Ⅵ  实现 onCreateViewHolder()

`onCreateViewHolder()` 方法由布局管理器调用，用于为 `RecyclerView` 创建新的 ViewHolder（如果不存在可重复使用的 ViewHolder）。请注意，一个 ViewHolder 代表一个列表项视图。

`onCreateViewHolder()` 方法接受两个参数并返回一个新的 `ViewHolder`。

- `parent` 参数，即新列表项视图将作为子视图附加到的视图组。父项是 `RecyclerView`。
- `viewType` 参数，当同一个 `RecyclerView` 中存在多种列表项视图类型时，此参数可发挥重要作用。如果在 `RecyclerView` 内显示不同的列表项布局，就会有不同的列表项视图类型。您只能循环使用列表项视图类型相同的视图。针对您的情况而言，只有一个列表项布局和一个列表项视图类型，因此您不必担心此参数。

1. 在 `onCreateViewHolder()` 方法中，从提供的上下文（`parent` 的 `context`）中获取 `LayoutInflater` 的实例。布局膨胀器知道如何将 XML 布局膨胀为视图对象的层次结构。

   ```
   val adapterLayout = LayoutInflater.from(parent.context)
   ```

2. 获取 `LayoutInflater` 对象实例后，添加一个句点，后跟另一个方法调用以膨胀实际的列表项视图。传入 XML 布局资源 ID `R.layout.list_item` 和 `parent` 视图组。第三个布尔值参数是 `attachToRoot`。此参数需为 `false`，因为 `RecyclerView` 会在需要的时候替您将此列表项添加到视图层次结构中。

   ```
   val adapterLayout = LayoutInflater.from(parent.context)       .inflate(R.layout.list_item, parent, false)
   ```

   现在，`adapterLayout` 存储着对列表项视图的引用（稍后我们可从中找到子视图，例如 `TextView`）。

3. 在 `onCreateViewHolder()` 中，返回根视图为 `adapterLayout` 的新 `ItemViewHolder` 实例。

   ```
   return ItemViewHolder(adapterLayout)
   ```

   以下就是截至目前为止 `onCreateViewHolder()` 的代码。

   ```
   override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ItemViewHolder {    // create a new view    val adapterLayout = LayoutInflater.from(parent.context)        .inflate(R.layout.list_item, parent, false)    return ItemViewHolder(adapterLayout)}
   ```



#### Ⅶ  实现 onBindViewHolder()

需要替换的最后一个方法是 `onBindViewHolder()`。此方法由布局管理器调用，以便替换列表项视图的内容。

`onBindViewHolder()` 方法有两个参数：其一是先前由 `onCreateViewHolder()` 方法创建的 `ItemViewHolder`；其二是一个 `int`，它代表当前列表项的 `position`。在此方法中，您将根据位置从数据集中找到正确的 `Affirmation` 对象。

1. 在 `onBindViewHolder()` 内，创建一个 `val` `item` 并获取 `dataset` 中位于给定 `position` 的列表项。

   ```
   val item = dataset[position]
   ```

   最后，您需要更新 ViewHolder 引用的所有视图，以便反映此列表项的正确数据。在本例中，只有一个视图：`ItemViewHolder` 内的 `TextView`。设置 `TextView` 的文本以显示此列表项的 `Affirmation` 字符串。

2. 有了 `Affirmation` 对象实例，您可以通过调用 `item.stringResourceId` 查找相应的字符串资源 ID。不过，这是一个整数，您需要查找它与实际字符串值的映射。

   在 Android 框架中，您可以使用字符串资源 ID 调用 `getString()`，它会返回与其关联的字符串值。`getString()` 是 `Resources` 类中的一个方法，您可以通过 `context` 获取 `Resources` 类的实例。

   这意味着，您可以调用 `context.resources.getString()` 并传入字符串资源 ID。返回的字符串可在 `holder` `ItemViewHolder` 中设为 `textView` 的 `text`。简言之，这一行代码会更新 ViewHolder 以显示这句自我肯定话语字符串。

   ```
   holder.textView.text = context.resources.getString(item.stringResourceId)
   ```

   完成后的 `onBindViewHolder()` 方法应如下所示。

   ```
   override fun onBindViewHolder(holder: ItemViewHolder, position: Int) {    val item = dataset[position]    holder.textView.text =  context.resources.getString(item.stringResourceId)}
   ```

以下是完成后的 Adapter 代码。

```
ItemAdapter.ktpackage com.example.affirmations.adapterimport android.content.Contextimport android.view.LayoutInflaterimport android.view.Viewimport android.view.ViewGroupimport android.widget.TextViewimport androidx.recyclerview.widget.RecyclerViewimport com.example.affirmations.Rimport com.example.affirmations.model.Affirmation/** * Adapter for the [RecyclerView] in [MainActivity]. Displays [Affirmation] data object. */class ItemAdapter(    private val context: Context,    private val dataset: List<Affirmation>) : RecyclerView.Adapter<ItemAdapter.ItemViewHolder>() {    // Provide a reference to the views for each data item    // Complex data items may need more than one view per item, and    // you provide access to all the views for a data item in a view holder.    // Each data item is just an Affirmation object.    class ItemViewHolder(private val view: View) : RecyclerView.ViewHolder(view) {        val textView: TextView = view.findViewById(R.id.item_title)    }    /**     * Create new views (invoked by the layout manager)     */    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ItemViewHolder {        // create a new view        val adapterLayout = LayoutInflater.from(parent.context)            .inflate(R.layout.list_item, parent, false)        return ItemViewHolder(adapterLayout)    }    /**     * Replace the contents of a view (invoked by the layout manager)     */    override fun onBindViewHolder(holder: ItemViewHolder, position: Int) {        val item = dataset[position]        holder.textView.text = context.resources.getString(item.stringResourceId)    }    /**     * Return the size of your dataset (invoked by the layout manager)     */    override fun getItemCount() = dataset.size}
```

现在，您已实现了 `ItemAdapter`，接下来您需要指示 `RecyclerView` 使用此 Adapter。



#### Ⅷ  修改 MainActivity 以使用 RecyclerView

最后，您需要使用 `Datasource` 和 `ItemAdapter` 类在 `RecyclerView` 中创建和显示列表项。您可以在 `MainActivity` 中执行此操作。

1. 打开 `MainActivity.kt`。

2. 在 `MainActivity,` 中，转到 `onCreate()` 方法。在调用 `setContentView(R.layout.activity_main).` 之后，插入以下步骤中所述的新代码。

3. 创建 `Datasource` 的实例，并对其调用 `loadAffirmations()` 方法。将返回的自我肯定话语列表存储在名为 `myDataset` 的 `val` 中。

   ```
   val myDataset = Datasource().loadAffirmations()
   ```

4. 创建一个名为 `recyclerView` 的变量，并使用 `findViewById()` 查找对布局中 `RecyclerView` 的引用。

   ```
   val recyclerView = findViewById<RecyclerView>(R.id.recycler_view)
   ```

5. 为了指示 `recyclerView` 使用您创建的 `ItemAdapter` 类，请创建一个新的 `ItemAdapter` 实例。`ItemAdapter` 应该有两个参数：此 activity 的上下文 (`this`) 和 `myDataset` 中的自我肯定话语。

6. 将 `ItemAdapter` 对象分配给 `recyclerView` 的 `adapter` 属性。

   ```
   recyclerView.adapter = ItemAdapter(this, myDataset)
   ```

7. 由于 activity 布局中的 `RecyclerView` 布局大小是固定的，因此您可以将 `RecyclerView` 的 `setHasFixedSize` 参数设为 `true`。只有在提高性能时才需要使用此设置。如果您知道内容的更改不会更改 `RecyclerView` 的布局大小，请使用此设置。

   ```
   recyclerView.setHasFixedSize(true)
   ```

8. 完成后，`MainActivity` 的代码应与下面的代码类似。

   ```
   MainActivity.ktpackage com.example.affirmationsimport android.os.Bundleimport androidx.appcompat.app.AppCompatActivityimport androidx.recyclerview.widget.RecyclerViewimport com.example.affirmations.adapter.ItemAdapterimport com.example.affirmations.data.Datasourceclass MainActivity : AppCompatActivity() {    override fun onCreate(savedInstanceState: Bundle?) {        super.onCreate(savedInstanceState)        setContentView(R.layout.activity_main)        // Initialize data.        val myDataset = Datasource().loadAffirmations()        val recyclerView = findViewById<RecyclerView>(R.id.recycler_view)        recyclerView.adapter = ItemAdapter(this, myDataset)        // Use this setting to improve performance if you know that changes        // in content do not change the layout size of the RecyclerView        recyclerView.setHasFixedSize(true)    }}
   ```

9. 运行应用。屏幕上应显示自我肯定话语字符串的列表。

![427c10d4f29d769d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-recyclerview-scrollable-list/img/427c10d4f29d769d.png)

祝贺您！您刚刚创建了一个使用 `RecyclerView` 和自定义 Adapter 显示数据列表的应用。请花些时间检查您创建的代码，了解不同组件能否协同工作。

此应用已有显示自我肯定话语所需的全部组件，但还不能说已完全准备好投入使用。界面还可以稍加改进。在下一个 Codelab 中，您将改进代码、学习如何在应用中添加图像并完善界面。

### ⑤小结

- `RecyclerView` 微件可帮助您显示数据列表。
- `RecyclerView` 使用 Adapter 模式来调整和显示数据。
- `ViewHolder` 为 `RecyclerView` 创建并存储视图。
- `RecyclerView` 附带内置 `LayoutManagers`。`RecyclerView` 将列表项的布局工作委托给 `LayoutManagers`。

为实现 Adapter，请执行以下操作：

- 为 Adapter 创建一个新类，例如 `ItemAdapter`。
- 创建用于代表单个列表项视图的自定义 `ViewHolder` 类。从 `RecyclerView.ViewHolder` 类进行扩展。
- 修改 `ItemAdapter` 类，以便从 `RecyclerView`.`Adapter` 类通过自定义 `ViewHolder` 类进行扩展。
- 在 Adapter 内实现以下方法：`getItemsCount()`、`onCreateViewHolder()` 和 `onBindViewHolder()`。



## 12 向列表项添加图片

### ①在 Affirmation 类中添加对图片的支持

在此步骤中，您将在 `Affirmation` 数据类中添加一个属性来存储图片资源 ID 的值。这样，单个 `Affirmation` 对象实例将包含自我肯定话语文本的资源 ID 和自我肯定话语图片的资源 ID。

1. 打开 `model` 软件包中的 `Affirmation`.`kt` 文件。
2. 通过添加另一个名为 `imageResourceId` 的 `Int` 参数，修改 `Affirmation` 类的构造函数。

### ②使用资源注解

`stringResourceId` 和 `imageResourceId` 都是整数值。虽然这看起来没有问题，但调用方可能会意外地以错误的顺序传入参数（首先传入 `imageResourceId`，而不是 `stringResourceId`）。

为避免此问题，您可以使用资源注解。注解很有用，因为它们可以向类、方法或参数添加额外的信息。注解始终使用 @ 符号进行声明。在本例中，向字符串资源 ID 属性添加 `@StringRes` 注解，并向可绘制资源 ID 属性添加 `@DrawableRes` 注解。这样一来，如果您提供错误类型的资源 ID，就会收到警告。

1. 向 `stringResourceId.` 添加 `@StringRes` 注解。

2. 向 `imageResourceId` 添加 `@DrawableRes` 注解。

3. 确保在文件的顶部且在软件包声明后面添加导入代码 `androidx.annotation.DrawableRes` 和 `androidx.annotation.StringRes`。

   ```
   Affirmation.ktpackage com.example.affirmations.modelimport androidx.annotation.DrawableResimport androidx.annotation.StringResdata class Affirmation(   @StringRes val stringResourceId: Int,   @DrawableRes val imageResourceId: Int)
   ```

### ③初始化带图片的自我肯定话语列表

现在，您已更改 `Affirmation` 类的构造函数，接下来需要更新 `Datasource` 类。向初始化的每个 `Affirmation` 对象传入一个图片资源 ID。

1. 打开 `Datasource`.`kt`。您应该会看到 `Affirmation` 的每次实例化都有一个错误。
2. 对于每个 `Affirmation`，将图片的资源 ID 添加为参数，如 `R.drawable.image1`。

```
Datasource.ktpackage com.example.affirmations.dataimport com.example.affirmations.Rimport com.example.affirmations.model.Affirmationclass Datasource() {    fun loadAffirmations(): List<Affirmation> {        return listOf<Affirmation>(            Affirmation(R.string.affirmation1, R.drawable.image1),            Affirmation(R.string.affirmation2, R.drawable.image2),            Affirmation(R.string.affirmation3, R.drawable.image3),            Affirmation(R.string.affirmation4, R.drawable.image4),            Affirmation(R.string.affirmation5, R.drawable.image5),            Affirmation(R.string.affirmation6, R.drawable.image6),            Affirmation(R.string.affirmation7, R.drawable.image7),            Affirmation(R.string.affirmation8, R.drawable.image8),            Affirmation(R.string.affirmation9, R.drawable.image9),            Affirmation(R.string.affirmation10, R.drawable.image10)        )    }}
```

### ④向列表项布局添加 ImageView

如需为列表中的每句自我肯定话语显示一张图片，您需要向项布局添加 `ImageView`。由于您现在有两个视图（`TextView` 和 `ImageView`），因此需要将其作为子视图放在 `ViewGroup` 中。如需在垂直列中排列视图，您可以使用 `LinearLayout`。`LinearLayout` 会在一个方向上（垂直或水平）对齐所有子视图。

![c8c81dc5ba25de16.png](https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/c8c81dc5ba25de16.png)

1. 依次打开 **res > layout > list_item.xml**。围绕现有的 `TextView` 添加 `LinearLayout`，并将 `orientation` 属性设置为 `vertical`。

2. 将 `xmlns schema` 声明行从 `TextView` 元素移至 `LinearLayout` 元素以消除错误。

   ```
   list_item.xml<?xml version="1.0" encoding="utf-8"?><LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"    android:layout_width="match_parent"    android:layout_height="wrap_content"    android:orientation="vertical">    <TextView        android:id="@+id/item_title"        android:layout_width="wrap_content"        android:layout_height="wrap_content" /></LinearLayout>
   ```

3. 在 `LinearLayout,` 内的 `TextView,` 前面，添加资源 ID 为 `item_image` 的 `ImageView`。

4. 将 `ImageView` 的宽度设置为 `match_parent`，并将其高度设置为 `194dp`。根据屏幕大小，此值应该在任何给定的时间都会在屏幕上显示几张卡片。

5. 将 `scaleType` 设置为 `centerCrop.`。

6. 将 `importantForAccessibility` 属性设置为 `no`，因为图片用于装饰目的。

   ```
       <ImageView        android:layout_width="match_parent"        android:layout_height="194dp"        android:id="@+id/item_image"        android:importantForAccessibility="no"        android:scaleType="centerCrop" />
   ```

### ⑤更新 ItemAdapter 以设置图片

1. 打开 `adapter/ItemAdapter`.`kt` (**app > java > adapter > ItemAdapter**)。

2. 转到 `ItemViewHolder` 类。

3. `ItemViewHolder` 实例应在列表项布局中存储对 `TextView` 的引用以及对 `ImageView` 的引用。做出以下更改。

   在 `textView` 属性的初始化下面，添加一个名为 `imageView.` 的 `val`。使用 `findViewById()` 查找对 `ImageView`（ID 为 `item_image`）的引用，并将其赋值给 `imageView` 属性。

   ```
   ItemAdapter.ktclass ItemViewHolder(private val view: View): RecyclerView.ViewHolder(view) {    val textView: TextView = view.findViewById(R.id.item_title)    val imageView: ImageView = view.findViewById(R.id.item_image)}
   ```

4. 在 `ItemAdapter` 中查找 `onBindViewHolder()` 函数。

5. 之前，您已将自我肯定话语的 `stringResourceId` 设置到 `ItemViewHolder` 中的 `textView` 上。现在，将自我肯定话语项的 `imageResourceId` 设置到列表项视图的 `ImageView` 上。

       override fun onBindViewHolder(holder: ItemViewHolder, position: Int) {    val item = dataset[position]    holder.textView.text = context.resources.getString(item.stringResourceId)    holder.imageView.setImageResource(item.imageResourceId)}

6. 运行应用并滚动浏览自我肯定话语列表。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/6606afd4cc96e6fa.png" alt="6606afd4cc96e6fa.png" style="zoom: 50%;" />

   有了图片，应用看起来更漂亮了！不过，您仍然可以改进应用界面。在下一部分中，您将对应用进行细微的调整以改进界面。



### ⑥美化界面

**添加内边距**

首先，在列表中的项之间添加一些空白。

**提示**：您可以在 XML 中进行布局更改（如此处所示），也可以在 **Design** 视图的 **Attributes** 面板中进行更改，只要您愿意，哪种方式都行。

1. 打开 `list_item`.`xml` (**app > res > layout > item_list.xml**)，然后向现有的 `LinearLayout` 添加 `16dp` 内边距。

   ```
   list_item.xml<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"    android:layout_width="match_parent"    android:layout_height="wrap_content"    android:orientation="vertical"    android:padding="16dp">
   ```

2. 向 `item_title` `TextView` 添加 `16dp` 内边距。

3. 在 `TextView` 中，将 `textAppearance` 属性设置为 `?attr/textAppearanceHeadline6`。[`textAppearance`](https://developer.android.com/guide/topics/ui/look-and-feel/themes#textappearance) 是用于定义文本专用样式的属性。如需了解其他可能的预定义文本外观值，请参阅[关于常见主题属性的博文](https://medium.com/androiddevelopers/android-styling-common-theme-attributes-8f7c50c9eaba)中的 TextAppearances 部分。

   ```
       <TextView        android:id="@+id/item_title"        android:layout_width="wrap_content"        android:layout_height="wrap_content"        android:padding="16dp"        android:textAppearance="?attr/textAppearanceHeadline6" />
   ```

4. 运行应用。您觉得列表看起来更好了吗？

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/d45467a2dee40a99.png" alt="d45467a2dee40a99.png" style="zoom:50%;" />





**使用卡片**

现在仍然很难分辨一张图片是属于它上面还是下面的自我肯定话语文本。为了解决此问题，您可以使用**卡片**视图。卡片视图提供了一种简单的方法来包含一组视图，同时又能为容器提供一致的样式。如需更多关于如何使用卡片的 Material Design 指导，请参阅这篇[关于卡片的指南](https://material.io/develop/android/components/cards)。

1. 围绕现有的 `LinearLayout.` 添加 `MaterialCardView`。
2. 再次将架构声明从 `LinearLayout` 移入 `MaterialCardView`。
3. 将 `MaterialCardView` 的 `layout_width` 设置为 `match_parent`，并将 `layout_height` 设置为 `wrap_content`。
4. 添加 `8dp` 的 `layout_margin`。
5. 移除 `LinearLayout` 中的内边距，这样就不会有太多的空白。
6. 现在，再次运行应用。使用 `MaterialCardView` 之后，您可以更好地将每句自我肯定话语区分开来了吗？

```
list_item.xml<?xml version="1.0" encoding="utf-8"?><com.google.android.material.card.MaterialCardView xmlns:android="http://schemas.android.com/apk/res/android"    android:layout_width="match_parent"    android:layout_height="wrap_content"    android:layout_margin="8dp">    <LinearLayout        android:layout_width="match_parent"        android:layout_height="wrap_content"        android:orientation="vertical">        <ImageView            android:id="@+id/item_image"            android:layout_width="match_parent"            android:layout_height="194dp"            android:importantForAccessibility="no"            android:scaleType="centerCrop" />        <TextView            android:id="@+id/item_title"            android:layout_width="wrap_content"            android:layout_height="wrap_content"            android:padding="16dp"            android:textAppearance="?attr/textAppearanceHeadline6" />    </LinearLayout></com.google.android.material.card.MaterialCardView>
```

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/82e5266c758d253e.png" alt="82e5266c758d253e.png" style="zoom:50%;" />



**更改应用主题颜色**

默认应用主题颜色可能不像您可以做出的一些其他选择那样令人平静。在此任务中，您会将应用主题颜色更改为蓝色。您随后可以按照自己的想法再次更改颜色！

您可以从此[链接](https://material.io/resources/color/#!/?view.left=0&view.right=0)的 Material Design 调色板中找到预定义的蓝色色调。

在此 Codelab 中，您将使用 Material Design 调色板中的以下颜色：

- blue_200：`#FF90CAF9`
- blue_500：`#FF2196F3`
- blue_700：`#FF1976D2`

**添加颜色资源**

在一个集中的位置（即在 `colors.xml` 文件中）定义应用中使用的颜色。

1. 打开 `colors.xml` (**res > color > colors.xml**)。
2. 针对上面定义的蓝色向该文件中添加新的颜色资源。

```
<color name="blue_200">#FF90CAF9</color><color name="blue_500">#FF2196F3</color><color name="blue_700">#FF1976D2</color>
```



**更改主题颜色**

现在，您已经有了新的颜色资源，接下来可以在主题中使用它们了。

1. 打开 `themes.xml` (**res > values > themes > themes.xml**)。

2. 找到 `<!-- Primary brand color. -->` 部分。

3. 添加或更改 `colorPrimary` 以使用 `@color/blue_500`。

4. 添加或更改 `colorPrimaryVariant` 以使用 `@color/blue_700`。

   ```
   <item name="colorPrimary">@color/blue_500</item><item name="colorPrimaryVariant">@color/blue_700</item>
   ```

5. 运行应用。您应该会看到应用栏颜色变成了蓝色

6. 

**更新深色主题颜色**

最好为应用的[深色主题](https://material.io/design/color/dark-theme.html)选择饱和度更低的颜色。

1. 打开深色主题 `themes.xml` 文件 (**themes > themes.xml (night)**)。

2. 添加或更改 `colorPrimary` 和 `colorPrimaryVariant` 主题属性，如下所示。

   ```
   <item name="colorPrimary">@color/blue_200</item><item name="colorPrimaryVariant">@color/blue_500</item>
   ```

3. 运行应用。

4. 在设备的**设置**中，开启**深色主题**。

5. 应用会切换到**深色主题**，验证它是否看起来像下面的屏幕截图。

   **注意**：**应用栏颜色**您可能想知道为什么您为深色主题指定的主色未显示在应用栏中。深色应用栏是设计使然。在深色主题中，应用栏和其他较大的区域默认情况下显示为深色背景 (`colorSurface`)，而不是主色。这是因为，Material 深色主题建议在较大的界面上少使用浅色。按钮或其他小符号将显示定义的主色。

6. 此时，您还可以在 `colors.xml` 文件中移除未使用的颜色（例如，在默认应用主题中使用的紫色资源）。



### ⑦更改应用图标

作为最后一步，您将更新应用图标。

1. 下载应用图标文件 [`ic_launcher_foreground.xml`](https://raw.githubusercontent.com/google-developer-training/android-basics-kotlin-affirmations-app-solution/main/app/src/main/res/drawable/ic_launcher_foreground.xml) 和 [`ic_launcher_background.xml`](https://raw.githubusercontent.com/google-developer-training/android-basics-kotlin-affirmations-app-solution/main/app/src/main/res/drawable-v24/ic_launcher_background.xml)。如果您的浏览器显示了相应的文件，请依次选择**文件 > 网页另存为…**，以将其保存到计算机上，而不必下载文件。

2. 在 Android Studio 中，删除两个文件，即 `drawable/ic_launcher_background.xml` 和 `drawable-v24/ic_launcher_foreground.xml` 文件，因为这些文件用于以前的应用图标。您可以取消选中 **Safe delete (with usage search)** 框。

3. 然后右键点击 **res > drawable** 文件夹，再依次选择 **New > Image Asset**。

   ![396caeeb2055bb47.png](https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/396caeeb2055bb47.png)

4. 在 **Configure Image Asset** 窗口中，确保选择了 **Foreground layer**。

   ![950577849db82497.png](https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/950577849db82497.png)

5. 在它下面，找到 **Path** 标签。

6. 点击 **Path** 文本框内的文件夹图标。

7. 找到并打开您下载到计算机上的 `ic_launcher_foreground`.`xml` 文件。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/b4c558bd7f56b802.png" alt="b4c558bd7f56b802.png" style="zoom:50%;" />

8. 切换到 **Background Layer** 标签页。

9. 点击 **Path** 文本框内的 **Browse** 图标。

10. 在计算机上查找并打开 `ic_launcher_background`.`xml` 文件。不需要进行其他更改。

11. 点击 **Next**。

    <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/37e59b725e8912e6.png" alt="37e59b725e8912e6.png" style="zoom: 33%;" />

12. 在 **Confirm Icon Path** 对话框中，点击 **Finish**。可以覆盖现有图标。

13. 为了遵循最佳做法，您可以将新的矢量可绘制对象 `ic_launcher_foreground`.`xml` 和 `ic_launcher_background`.`xml` 移入一个名为 `drawable-anydpi-v26` 的新资源目录。[自适应图标](https://developer.android.com/guide/practices/ui_guidelines/icon_design_adaptive)是在 API 26 中引入的，因此这些资源只会用在搭载 API 26 及更高版本（针对任何 dpi）的设备上。

14. 如果 `drawable-v24` 目录中没有剩下任何内容，请删除该目录。

15. 运行应用并注意应用抽屉中漂亮的新应用图标！

    <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/4d98b85bf939b279.png" alt="4d98b85bf939b279.png" style="zoom:50%;" />

16. 作为最后一步，请不要忘记为项目中的 Kotlin 和 XML 文件重新设置格式，以使代码更简洁并遵循样式准则。

恭喜！您创建了一个鼓舞人心的 Affirmations 应用。

| ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/8b68aab540a41192.png) | ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-display-list-cards/img/a41cf254103443ab.png) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |

利用这些关于如何在 Android 应用中显示数据列表的知识，您接下来可以构建什么呢？



### ⑧小结

- 如需在 `RecyclerView` 中显示其他内容，请修改底层数据模型类和数据源。然后，更新列表项布局和适配器以将该数据设置到视图上。
- 使用资源注解帮助确保将正确类型的资源 ID 传入类构造函数。
- 使用 **Material Components for Android 库**让应用更轻松地遵循建议的 Material Design 准则。
- 使用 `MaterialCardView` 在 Material 卡片中显示内容。
- 在颜色和间距方面对应用进行细微的视觉调整可使应用看起来更精美且更一致。



# 三 屏幕之间导航

## 1 Kotlin 中的集合

### ① 了解集合

[集合](https://kotlinlang.org/docs/reference/collections-overview.html)是一组相关项，例如一系列字词或一组员工记录。集合中包含的项可以有序也可以无序，可以具有唯一性也可以不具唯一性。您已经学过一种类型的集合，那就是列表。列表项是有序的，但不必是唯一的。

与列表一样，Kotlin 也会区分可变集合和不可变集合。Kotlin 提供了许多函数，用于添加或删除项以及查看和操控集合。

**创建列表**

在此任务中，您将复习如何创建数字列表并对其排序。

1. 打开 [Kotlin 园地](https://developer.android.com/training/kotlinplayground)。
2. 将任意代码替换为以下代码：

```
fun main() {    val numbers = listOf(0, 3, 8, 4, 0, 5, 5, 8, 9, 2)    println("list:   ${numbers}")}
```

点按绿色箭头运行程序，并查看显示的结果：

```
list:   [0, 3, 8, 4, 0, 5, 5, 8, 9, 2]
```

1. 该列表包含 0 到 9 之间的 10 个数字。有些数字多次出现，而有些则根本没有显示。
2. 列表项的顺序很重要：第一项是 `0`，第二项是 `3`，依此类推。除非您做出更改，否则列表项将保持此顺序不变。
3. 回想之前的 Codelab 内容可知，列表中有许多内置函数，例如返回按升序排序的列表副本的 `sorted()`。在 `println()` 之后，将一行代码添加到程序中，用于输出经过排序的列表副本：

```
println("sorted: ${numbers.sorted()}")
```

再次运行程序并查看结果：

```
list:   [0, 3, 8, 4, 0, 5, 5, 8, 9, 2]sorted: [0, 0, 2, 3, 4, 5, 5, 8, 8, 9]
```

对数字进行排序后，更容易看出每个数字在列表中出现的次数或者是否根本没有显示



### ②详细了解集

Kotlin 中另一种类型的集合是[集](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-set/)。集是一组相关项，但与列表不同，其中不能存在任何重复项，而且顺序也不重要。某个项可以在集中也可以不在集中，但如果在集中，那么集中只能包含该项一个的副本。这与数学中“一套”的概念相似。比如，您看过一套书，即使您反复读其中的一本书，也不能改变这本书属于这一套书的事实。

1. 将以下几行代码添加到程序中，以将列表转换为集：

   ```
   val setOfNumbers = numbers.toSet()println("set:    ${setOfNumbers}")
   ```

2. 运行程序并查看结果：

   ```
   list:   [0, 3, 8, 4, 0, 5, 5, 8, 9, 2]sorted: [0, 0, 2, 3, 4, 5, 5, 8, 8, 9]set:    [0, 3, 8, 4, 5, 9, 2]
   ```

   结果中包含原列表中的所有数字，但每个数字都只出现了一次。请注意，这些数字的顺序与原列表中的顺序相同，但这个顺序对集来说并不重要。

3. 定义一个可变集和一个不可变集，并通过添加下列几行代码使用同一组数字（但数字的顺序不同）对其进行初始化：

   ```
   val set1 = setOf(1,2,3)val set2 = mutableSetOf(3,2,1)
   ```

4. 添加一行代码以输出两个集是否相等：

   ```
   println("$set1 == $set2: ${set1 == set2}")
   ```

5. 运行程序并查看新的结果：

   ```
   [1, 2, 3] == [3, 2, 1]: true
   ```

   即使一个集可变一个集不可变，而且两个集中的项顺序不同，这两个集也被视为相等，因为它们包含完全相同的一组项。

   您可能会对集执行的一项主要操作是使用 [`contains()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-set/#functions) 函数检查某个特定项是否包含在集中。您以前看过 `contains()`，但当时是将其用于列表。

6. 将以下这行代码添加到程序中，用于输出 `7` 是否包含在集中：

   ```
   println("contains 7: ${setOfNumbers.contains(7)}")
   ```

7. 运行程序并查看更多结果：

   ```
   contains 7: false
   ```

   您也可以尝试使用一个包含在集中的值对其进行测试。

   ```
       All of the code above:fun main() {    val numbers = listOf(0, 3, 8, 4, 0, 5, 5, 8, 9, 2)    println("list:   ${numbers}")    println("sorted: ${numbers.sorted()}")    val setOfNumbers = numbers.toSet()    println("set:    ${setOfNumbers}")    val set1 = setOf(1,2,3)    val set2 = mutableSetOf(3,2,1)    println("$set1 == $set2: ${set1 == set2}")    println("contains 7: ${setOfNumbers.contains(7)}")}
   ```

   与数学中的集一样，在 Kotlin 中，您也可以使用 [`intersect()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/intersect.html) 或 [`union()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/union.html) 执行求两个集的交集 (∩) 或并集 (∪) 等运算。



### ③详细了解映射

您在此 codelab 中要了解的最后一种类型的集合是[映射](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-map/)或字典。映射是一组键值对，用于在给定特定键的情况下轻松查找值。键具有唯一性，每个键只映射到一个值，但值可以重复。映射中的值可以是字符串、数字或对象，甚至可以是列表或集等其他集合。

![31796d892f69470d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/31796d892f69470d.png)

当您有成对数据并可根据键来识别每对数据时，映射将非常有用。键“映射到”对应的值。

1. 在 Kotlin 园地中，使用以下代码替换所有代码，以创建一个可变映射，用于存储人名及其年龄：

   ```
   fun main() {    val peopleAges = mutableMapOf<String, Int>(        "Fred" to 30,        "Ann" to 23    )    println(peopleAges)}
   ```

   这将创建一个从 `String`（键）到 `Int`（值）的可变映射，初始化包含两个条目的映射，并输出项。

2. 运行程序并查看结果：

   ```
   {Fred=30, Ann=23}
   ```

3. 如需将更多条目添加到该映射中，可以使用 [`put()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/-mutable-map/put.html) 函数，传入键和值

   ```
   peopleAges.put("Barbara", 42)
   ```

4. 您还可以使用简写表示法来添加条目：

   ```
   peopleAges["Joe"] = 51
   ```

   以下是上面的所有代码：

   ```
   fun main() {    val peopleAges = mutableMapOf<String, Int>(        "Fred" to 30,        "Ann" to 23    )    peopleAges.put("Barbara", 42)    peopleAges["Joe"] = 51    println(peopleAges)}
   ```

5. 运行程序并查看结果：

   ```
   {Fred=30, Ann=23, Barbara=42, Joe=51}
   ```

6. 在 `println()` 之前，添加以下这行代码：

   ```
   peopleAges["Fred"] = 31
   ```

7. 运行程序并查看结果：

   ```
   {Fred=31, Ann=23, Barbara=42, Joe=51}
   ```

   键 `"Fred"` 不会再次添加，但其映射到的值会更新为 `31`。

   可以看出来，映射可以快速将键映射到值，在代码中非常有用！



### ④使用集合

虽然不同类型的集合具有不同的特性，但它们有许多相同的行为。如果是可变集合，那么您可以添加或移除项。您可以枚举所有项、查找特定项，有时还可以将一种类型的集合转换为另一种类型。您先前就进行过这样的转换，使用 [`toSet()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.sequences/to-set.html) 将 `List` 转换为 `Set`。以下是使用集合时可以用到的一些实用函数。



**forEach**

假设您要输出 `peopleAges` 中的项，并且包括人名和年龄。例如：`"Fred is 31, Ann is 23,..."`，等等。您在之前的某个 Codelab 中曾学过 `for` 循环，因此您可以使用 `for (people in peopleAges) { ... }` 编写一个循环。

不过，枚举集合中的所有对象是一项常见的操作，所以 Kotlin 提供了 [`forEach()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/for-each.html) 来遍历所有项并对每个项执行操作。

1. 在园地中，在 `println()` 之后添加以下代码：

   ```
   peopleAges.forEach { print("${it.key} is ${it.value}, ") }
   ```

   它与 `for` 循环类似，但更简洁一点。`forEach` 使用特殊标识符 `it`，而不是由您为当前项指定变量。

   请注意，调用 `forEach()` 方法时不需要添加圆括号，只需将代码传入花括号 `{}` 即可。

2. 运行程序并查看更多结果：

   ```
   Fred is 31, Ann is 23, Barbara is 42, Joe is 51,
   ```

结果已非常接近您想要的内容，只是末尾多了一个英文逗号。

将集合转换为字符串是一项常见的操作，末尾多出分隔符也是一个常见问题。您将在后面的步骤中了解如何处理此问题。



**map**

[`map()`](https://kotlinlang.org/docs/reference/collection-transformations.html#mapping) 函数（不应与上面的映射或字典集合混淆）对集合中的每个项应用转换。

1. 在程序中，将 `forEach` 语句替换为以下这行代码：

   ```
   println(peopleAges.map { "${it.key} is ${it.value}" }.joinToString(", ") )
   ```

2. 运行程序并查看更多结果：

   ```
   Fred is 31, Ann is 23, Barbara is 42, Joe is 51
   ```

输出的内容正确，并且没有额外的英文逗号！一行代码中包含的内容非常多，所以我们要更详细地介绍一下。

- `peopleAges.map` 对 `peopleAges` 中的每个项应用转换，并以转换后的项创建一个新集合
- 花括号 `{}` 中的部分定义了要对每个项应用的转换。转换接受键值对并将其转换为字符串，例如将 `<Fred, 31>` 转换为 `Fred is 31`
- `joinToString(", ")` 将转换后的集合中的每个项添加到字符串中并以 `,` 分隔，而且它还知道不要在最后一个项后添加此分隔符
- 所有上述代码都以 `.`（点运算符）链接到一起，正如您在之前的 Codelab 中对函数调用和属性访问所做的一样



**filter**

集合的另一项常见操作是查找符合特定条件的项。[`filter()`](https://kotlinlang.org/docs/reference/collection-filtering.html) 函数根据表达式返回集合中的匹配项。

1. 在 `println()` 之后，添加以下这几行代码：

   ```
   val filteredNames = peopleAges.filter { it.key.length < 4 }println(filteredNames)
   ```

   同样请注意，调用 `filter` 不需要圆括号，`it` 表示列表中的当前项。

2. 运行程序并查看更多结果：

   ```
   {Ann=23, Joe=51}
   ```

在本例中，表达式会获取键（一个 `String`）的长度并检查其是否小于 4。任何匹配项（即名称少于 4 个字符的项）都被添加到新集合中。

对映射应用过滤条件时返回的类型是一个新映射 (`LinkedHashMap`)。您可以对该映射执行其他处理，也可以将其转换为列表等其他类型的集合。



### ⑤了解 lambda 和高阶函数

**lambda**

上面这段代码中的模式看起来熟悉吗？

```
peopleAges.forEach { print("${it.key} is ${it.value}") }
```

代码中有一个变量 (`peopleAges`) 和对其调用的一个函数 (`forEach`)。函数名称后不是用圆括号括起来的参数，而是用花括号 `{}` 括起来的一些代码。同样的模式也出现在前面使用 `map` 和 `filter` 函数的代码中。这里对 `peopleAges` 变量调用了 `forEach` 函数，并使用花括号中的代码。

这就像在花括号中编写一小段函数，但没有函数名称。这种想法（没有名称但可立即用作表达式的函数）是一个非常有用的概念，称为 lambda 表达式，简称 lambda。

由此引出一个重要的主题，那就是如何借助 Kotlin 以有效的方式与函数交互。您可以将函数存储在变量和类中，将函数作为参数传递，甚至可以返回函数。您可以像处理 `Int` 或 `String` 等其他类型的变量那样处理它们。



**函数类型**

为了支持这种行为，Kotlin 提供了函数类型，供您根据函数的输入参数和返回值定义特定类型的函数。它显示为以下格式：

函数类型示例：`(Int) -> Int`

具有上述函数类型的函数必须接受类型为 `Int` 的参数并返回类型为 `Int` 的值。在函数类型表示法中，参数列于圆括号中（如有多个参数，以英文逗号分隔）。接着是一个箭头 `->`，后跟返回值类型。

哪种类型的函数满足此条件？您可以用一个 lambda 表达式将整数输入的值乘以三，如下所示。在 lambda 表达式的语法中，参数在前（以红色框突出显示），后跟函数箭头，再跟函数主体（以紫色框突出显示）。lambda 中的最后一个表达式是返回值。

![252712172e539fe2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/252712172e539fe2.png)

您甚至可以将 lambda 存储在变量中，如下图所示。该语法与声明基本数据类型的变量（如 `Int`）时使用的语法类似。请注意变量名称（黄色框）、变量类型（蓝色框）和变量值（绿色框）。`triple` 变量存储了一个函数。其类型为函数类型 `(Int) -> Int`，值为 lambda 表达式 `{ a: Int -> a * 3}`。

1. 在园地中试一试此代码。定义并调用 `triple` 函数，向其传递一个数字（例如 5）。![4d3f2be4f253af50.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/4d3f2be4f253af50.png)

2. 生成的输出应如下所示：

   ```
   fun main() {    val triple: (Int) -> Int = { a: Int -> a * 3 }    println(triple(5))}15
   ```

   

3. 在花括号中，您可以省略对参数的显式声明 (`a: Int`) 也省略函数箭头 (`->`)，而只包含函数主体。更新 `main` 函数中声明的 `triple` 函数并运行代码。

   ```
   val triple: (Int) -> Int = { it * 3 }
   ```

4. 输出应该相同，但是现在 lambda 编写得更简洁！如需查看 lambda 的更多示例，请查看此[资源](https://play.kotlinlang.org/byExample/04_functional/02_Lambdas)。

   ```
   15
   ```



**高阶函数**

现在，您已经开始明白 Kotlin 中的函数操控方式的灵活性，接下来我们要介绍另一个非常有用的概念，高阶函数。这个概念就是指将一个函数（在本例中为 lambda）传递给另一个函数，或从另一个函数返回一个函数。

因此，`map`、`filter` 和 `forEach` 函数都是高阶函数的例子，因为它们都接受函数作为参数。（在传递给此 `filter` 高阶函数的 lambda 中，可以省略仅有的一个参数和箭头符号，还可以使用 `it` 参数。）

```
peopleAges.filter { it.key.length < 4 }
```

下面是一个新高阶函数的示例：`sortedWith()`。

如果要对字符串列表排序，可以使用集合的内置 `sorted()` 方法。但是，如果要按字符串的长度对列表排序，就需要编写一些代码来获取两个字符串的长度并对其进行比较。在 Kotlin 中，您可以将一个 lambda 传递给 `sortedWith()` 方法来做到这一点。

**注意**：如需比较两个对象来进行排序，惯例是在第一个对象小于第二个对象时返回小于 0 的值，在两个对象相等时返回 0，在第一个对象大于第二个对象时返回大于 0 的值。

1. 在园地中，使用以下代码创建一个名称列表，并输出按名称排序的该列表：

   ```
   fun main() {    val peopleNames = listOf("Fred", "Ann", "Barbara", "Joe")    println(peopleNames.sorted())}
   ```

   

2. 现在，将一个 lambda 传递给 `sortedWith()` 函数，输出按名称长度排序的该列表。lambda 应接受同一类型的两个参数，并返回一个 `Int`。在 `main()` 函数中的 `println()` 语句后添加以下这行代码。

   ```
   println(peopleNames.sortedWith { str1: String, str2: String -> str1.length - str2.length })
   ```

3. 运行程序并查看结果。

   ```
   [Ann, Barbara, Fred, Joe][Ann, Joe, Fred, Barbara]
   ```

传递给 `sortedWith()` 的 lambda 有两个参数：`str1`（是一个 `String`）和 `str2`（也是一个 `String`）。其后是函数箭头，后跟函数主体。

![7005f5b6bc466894.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/7005f5b6bc466894.png)

请注意，lambda 中的最后一个表达式是返回值。在本例中，它将返回第一个字符串的长度与第二个字符串的长度之间的差（是一个 `Int`）。这与排序需要返回的值一致：如果 `str1` 的长度小于 `str2`，将返回一个小于 0 的值。如果 `str1` 和 `str2` 长度相同，将返回 0。如果 `str1` 的长度大于 `str2`，将返回一个大于 0 的值。通过一系列比较（一次比较两个 `Strings`），`sortedWith()` 函数会输出一个列表，其中的名称按长度递增的顺序排列。





**Android 中的 OnClickListener 和 OnKeyListener**

将此与您迄今学过的 Android 知识联系起来，可以发现您在之前的 Codelab 中已经使用过 lambda，例如，当您为 Tip Calculator 应用中的按钮设置点击监听器时：

```
calculateButton.setOnClickListener{ calculateTip() }
```

使用 lambda 设置点击监听器非常简单、方便。下面显示了采用长格式编写上述代码的方式，并与简写版本进行了比较。您不必了解长格式版本的所有细节，但是要注意两个版本之间的一些模式。

![29760e0a3cac26a2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/29760e0a3cac26a2.png)

请注意，lambda 的函数类型与 `OnClickListener` 中的 `onClick()` 方法相同（接受一个 `View` 参数并返回 `Unit`，这意味着没有返回值）。

我们之所以能够简化代码，要归功于 Kotlin 中的 SAM（单一抽象方法）转换。Kotlin 将 lambda 转换为 `OnClickListener` 对象，由其实现单一抽象方法 `onClick()`。您只需确保 lambda 函数类型与抽象函数的函数类型匹配即可。

由于 lambda 中从不使用 `view` 参数，因此可以省略该参数。如此一来，lambda 中就只包含函数主体。

```
calculateButton.setOnClickListener { calculateTip() }
```

这些概念比较难掌握，请耐心学习，您需要付出一些时间并积累经验才能领会。我们再来看一个例子。回想一下，您在 Tip Calculator 应用中对“Cost of service”文本字段设置了按键监听器，因此屏幕键盘可在按 Enter 键时隐藏。

```
costOfServiceEditText.setOnKeyListener { view, keyCode, event -> handleKeyEvent(view, keyCode) }
```

当您查找 [`OnKeyListener`](https://developer.android.com/reference/android/view/View.OnKeyListener) 时，抽象方法具有以下参数 `onKey(View v, int keyCode, KeyEvent event)` 并返回一个 `Boolean`。得益于 Kotlin 中的 SAM 转换，您可以将 lambda 传入 `setOnKeyListener()`。只需确保 lambda 的函数类型为 `(View, Int, KeyEvent) -> Boolean`。

下图显示了上面使用的 lambda 表达式。其参数包括 view、keyCode 和 event。函数主体由 `handleKeyEvent(view, keyCode)` 构成，它使用传入的参数并返回一个 `Boolean`。

![f73fe767b8950123.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/f73fe767b8950123.png)

**注意**：如果不在函数主体中使用 lambda 参数，可将其命名为 `_`，使代码更易读、更简洁。此代码的行为相同。

```
costOfServiceEditText.setOnKeyListener { view, keyCode, _ -> handleKeyEvent(view, keyCode) }
```



### ⑥ 创建单词列表

假设您要创建一个 Android 应用来玩文字游戏或学习词汇。该应用可能与下图类似，为字母表中的每个字母提供一个按钮：

![45d7aa76e7c2c20e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-collections/img/45d7aa76e7c2c20e.png)

点击字母 **A** 会调出一个简短的列表，包含以字母 A 开头的一些单词，余者依此类推。

您需要一个单词集合，但应该是哪种类型的集合呢？如果该应用将包含以字母表中每个字母开头的一些单词，您就需要通过一种办法来查找或整理以给定字母开头的所有单词。为提高挑战性，您还需要在用户每次运行应用时从集合中选择不同的单词。

首先，从单词列表开始。在真实的应用中，您需要使用更长的单词列表，并包含以字母表中所有字母开头的单词，但现在使用一个简短的列表足以。

1. 使用以下代码替换 Kotlin 园地中的代码：

   ```
   fun main() {    val words = listOf("about", "acute", "awesome", "balloon", "best", "brief", "class", "coffee", "creative")}
   ```

2. 如需获取以字母 B 开头的单词的集合，可以将 `filter` 与 lambda 表达式结合使用。添加以下几行代码：

   ```
   val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }println(filteredWords)
   ```

   如果字符串以指定的字符串开头，[`startsWith()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/starts-with.html) 函数将返回 true。您也可以指示它忽略大小写，因此“b”将与“b”或“B”匹配。

3. 运行程序并查看结果：

   ```
   [balloon, best, brief]
   ```

4. 请注意，应用需要随机显示单词。借助 Kotlin 集合，您可以使用 [`shuffled()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/shuffled.html) 函数随机打乱集合中的项并创建集合的副本。将过滤后的单词也改为打乱顺序：

   ```
   val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }    .shuffled()
   ```

5. 运行程序并查看新的结果：

   ```
   [brief, balloon, best]
   ```

   由于单词是随机打乱的，因此您看到的单词可能顺序不同。

6. 您并不需要使用所有单词（尤其是在实际单词列表很长的情况下），只需使用几个单词即可。您可以使用 [`take()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/take.html) 函数获取集合中的前 N 个项。使过滤后的单词只包含打乱后的前两个单词：

   ```
   val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }    .shuffled()    .take(2)
   ```

7. 运行程序并查看新的结果：

   ```
   [brief, balloon]
   ```

   同样，由于单词是随机打乱的，因此每次运行程序时看到的单词可能都不同。

8. 最后，对于需要对每个字母的随机单词列表进行排序的应用，与之前一样，您可以使用 [`sorted()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/sorted.html) 函数返回包含已排序项的集合的副本：

   ```
   val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }    .shuffled()    .take(2)    .sorted()
   ```

9. 运行程序并查看新的结果：

   ```
   [balloon, brief]
   ```

   上面的所有代码汇总如下：

   ```
   fun main() {    val words = listOf("about", "acute", "awesome", "balloon", "best", "brief", "class", "coffee", "creative")    val filteredWords = words.filter { it.startsWith("b", ignoreCase = true) }        .shuffled()        .take(2)        .sorted()    println(filteredWords)}
   ```

10. 尝试更改代码，创建只含一个以字母 c 开头的随机单词的列表。您必须对上面的代码做出哪些更改

    ```
    val filteredWords = words.filter { it.startsWith("c", ignoreCase = true) }    .shuffled()    .take(1)    .sorted()
    ```

    在实际应用中，您需要对字母表中的每个字母应用过滤器，不过现在您已经知道如何生成每个字母的单词列表了！

    集合功能强大且非常灵活，不仅作用广泛，而且不拘泥于通过一种方式发挥作用。随着您越来越深入地了解编程，您将了解如何判定适合解决手头问题的集合类型以及处理该问题的最佳方式。

    lambda 和高阶函数让集合的使用变得更方便、更简洁。以下概念非常有用，所以我们一再强调这些概念。



### ⑦小结

- 集合是一组相关项
- 集合可以是可变的，也可以是不可变的
- 集合可以有序，也可以无序
- 集合可要求项具有唯一性，也可允许重复
- Kotlin 支持不同类型的集合，包括列表、集和映射
- Kotlin 提供了许多用于处理和转换集合的函数，包括 `forEach`、`map`、`filter`、`sorted` 等
- lambda 是没有名称但可立即作为表达式传递的函数。例如，{ a: Int -> a * 3 }
- 高阶函数是指将一个函数传递给另一个函数，或从另一个函数返回一个函数



## 2 activity 和 intent

**下载此 Codelab 的起始代码**

此 Codelab 提供了起始代码，供您使用此 Codelab 中所教的功能对其进行扩展。起始代码可能包含您在之前的 Codelab 中已经熟悉的代码，也可能包含您不熟悉的代码，您可以在后续 Codelab 中了解相关信息。

如果您从 GitHub 下载起始代码，那么请注意，文件夹名称为 `android-basics-kotlin-words-app-starter`。在 Android Studio 中打开项目时，请选择此文件夹。

```
起始代码网址**：https://github.com/google-developer-training/android-basics-kotlin-words-app/tree/starter**GitHub 中的分支名称**：starter
```

在继续之前，请花点时间熟悉一下项目。您应该已经熟悉了上一单元介绍的所有概念。目前，该应用由两个 activity 组成，每个 activity 均包含一个 recycler 视图和一个适配器。

![f1e0ec543698f945.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/f1e0ec543698f945.png)

具体而言，您将处理以下文件：

1. `LetterAdapter` 由 `MainActivity` 中的 `RecyclerView` 使用。每个字母都是一个具有 `onClickListener` 的按钮，该监听器目前为空。您将在此监听器中处理按下按钮的操作，以导航到 `DetailActivity`。
2. `WordAdapter` 由 `DetailActivity` 中的 `RecyclerView` 使用，以显示单词列表。尽管您还无法导航到此屏幕，但要知道，每个单词还有一个相应的具有 `onClickListener` 的按钮。您将在此监听器中添加能够导航到浏览器的代码，以便显示相应单词的定义。
3. `MainActivity` 也需要进行一些更改。在此，您将通过实现选项菜单来显示按钮，从而使用户能够在列表和网格布局之间进行切换。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/ce3474dba2a9c1c8.png" alt="ce3474dba2a9c1c8.png" style="zoom:33%;" />

熟悉到目前为止的项目之后，请继续下一部分，您将了解 intent。

### ①  intent 简介

现在，您已设置好初始项目，接下来我们讨论一下 intent，以及如何在应用中使用它们。

intent 是用于表示要执行的某些操作的对象。intent 最常见（但肯定不是唯一）的用途是启动 activity。intent 分为两种类型：**隐式**和**显式**。**显式 intent** 非常具体，使用这类 intent 时您知道要启动的具体 activity，通常是您自己应用中的屏幕。

**隐式 intent** 更抽象一些，您可以通过这类 intent  告知系统要执行的操作类型（例如打开链接、撰写电子邮件或拨打电话），系统则负责确定如何执行相应请求。在操作过程中，您可能已经见过这两类  intent，但自己并不知道。通常情况下，如果要显示自己应用中的 activity，您可以使用显式 intent。

| <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/7edb0777b033c159.png" alt="img"  /> | <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/c465ef280fe3792a.png" alt="img"  /> |
| ------------------------------------------------------------ | :----------------------------------------------------------- |

但是，对于不一定涉及当前应用的操作（例如，您发现了一个有趣的 Android 文档页面，想与好友分享），则应使用**隐式 intent**。您可能会看到如下所示的菜单，询问使用哪个应用来分享页面。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/e9c77033d9224170.png" alt="e9c77033d9224170.png" style="zoom:33%;" />

您可以使用显式 intent 来执行操作或显示自己应用中的屏幕，并对整个流程负责。隐式 intent 一般用来执行涉及其他应用的操作，并依赖系统来确定最终结果。您将在 Words 应用中使用这两类 intent。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/702236c6e2276f91.png" alt="702236c6e2276f91.png" style="zoom:33%;" />



### ②设置显式 intent

现在，您可以实现自己的首个 intent 了。在第一个屏幕上，当用户点按某个字母时，系统应将他们转到包含单词列表的第二个屏幕。`DetailActivity` 已经实现，因此您现在只需要使用一个 intent 来启动它即可。因为应用明确知道应启动哪个 activity，所以应使用显式 intent。

只需简单几步，即可创建和使用 intent：

1. 打开 `LetterAdapter.kt` 并向下滚动到 `onBindViewHolder()`。在用于设置按钮文本的代码行下方，为 `holder.button` 设置 `onClickListener`。

   ```
   holder.button.setOnClickListener {}
   ```

2. 然后，获取对 `context` 的引用。

   ```
   val context = holder.view.context
   ```

3. 创建一个 `Intent`，并传入 context 以及目标 activity 的类名称。

   ```
   val intent = Intent(context, DetailActivity::class.java)
   ```

   您想要显示的 activity 的名称是使用 `DetailActivity::class.java` 指定的。实际的 `DetailActivity` 对象会在后台创建。

4. 调用 `putExtra` 方法，并传入“letter”作为第一个参数，传入按钮文本作为第二个参数。

   ```
   intent.putExtra("letter", holder.button.text.toString())
   ```

   什么是 extra？请记住，intent 只是一组指令，目前还没有目标 activity 的实例。而 extra 是一段数据（例如一个数字或一个字符串），系统会为其指定名称，以便日后检索。这类似于在调用函数时传递参数。由于 `DetailActivity` 可以针对任何字母显示，您需要告知它显示哪个字母。

   此外，您觉得为什么需要调用 `toString()`？按钮文本已经是字符串了，对吗？

   在某种程度上，是的。它实际上是 `CharSequence` 类型，被称为“接口”。目前，您不需要了解有关 Kotlin 接口的任何内容，只要知道通过这种方式可以确保某种类型（例如字符串）会实现特定函数和属性就行。您可以将 `CharSequence` 视为一种更通用的表示方式，代表一种类似于字符串的类。按钮的 `text` 属性可以是字符串，也可以是同样为 `CharSequence` 的任何对象。不过，`putExtra()` 方法可以接受 `String`，而不仅仅是任何 `CharSequence`，因此需要调用 `toString()`。

5. 对 context 对象调用 `startActivity()` 方法，并传入 `intent`。

   ```
   context.startActivity(intent)
   ```

   现在，运行应用并尝试点按某个字母。系统会显示详情屏幕！但是，无论用户点按哪个字母，详情屏幕始终会显示字母 A 对应的单词。您仍需要在详情 activity 中执行一些操作，以便它针对作为 `intent` extra 传递的任意字母显示相应单词。



### ③设置 DetailActivity

您刚刚创建了您的首个显式 intent！现在，来处理详情屏幕。

在 `DetailActivity` 的 `onCreate` 方法中，在对 `setContentView` 的调用之后，将硬编码的字母替换为用于获取从 `intent` 传入的 `letterId` 的代码。

```
val letterId = intent?.extras?.getString("letter").toString()
```

此处涉及的内容较多，因此我们逐一了解各个部分：

首先，`intent` 属性来自哪里？它不是 `DetailActivity` 的属性，相反，它可以是任意 activity 的属性。它会保留对用于启动相应 activity 的 intent 的引用。

extra 属性为 `Bundle` 类型，您可能已经猜到，它提供了一种访问传入相应 intent 的所有 extra 的方式。

这两种属性都使用问号进行了标记。这是为什么？原因在于，`intent` 和 `extras` 属性可为 null，这意味着它们可能有值，也可能没有值。有时，您可能希望某个变量为 `null`。实际上，`intent` 属性可能并不是 `Intent`（如果 activity 不是通过 intent 启动），extra 属性也可能并不是 `Bundle`，而是一个名为 `null` 的值。在 Kotlin 中，`null` 表示没有值。相应对象可能已存在，也可能为 `null`。如果您的应用尝试在 `null` 对象上访问属性或调用函数，应用将会崩溃。为了安全地访问此值，可以在名称后添加“`?`”。如果 `intent` 为 `null`，您的应用甚至不会尝试访问 extra 属性；如果 `extras` 为 null，您的代码甚至不会尝试调用 `getString()`。

如何知道哪些属性需要添加问号以确保其为 null 时的安全性？您可以根据类型名称后跟的是问号还是感叹号来判断。

![2009463ce2fd82f2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/2009463ce2fd82f2.png)

最后要注意的是，实际的字母是使用 `getString` 检索的，它会返回 `String?`，因此系统会调用 `toString()` 以确保结果是一个 `String`，而不是 `null`。

现在，当您运行应用并转到详情屏幕时，应该会看到每个字母对应的单词列表。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/c465ef280fe3792a.png" alt="c465ef280fe3792a.png" style="zoom:33%;" />

**清理**

执行 intent 的代码和检索所选字母的代码都将 `extra` 的名称硬编码成了“letter”。尽管此方法适用于此类小型示例，但对于需要跟踪更多 intent extra 的大型应用来说，这并非最佳方法。

虽然您可以只创建一个名为“letter”的常量，但当您向应用添加更多 intent extra 时，代码可能会变得比较庞杂。另外，您应该将此常量放入哪个类呢？请记住，该字符串会同时用于 `DetailActivity` 和 `MainActivity`。您需要一种方法来定义常量，使其能在多个类中使用，同时保持代码的条理性。

幸运的是，Kotlin 中有一种便捷的功能叫[伴生对象](https://kotlinlang.org/docs/reference/object-declarations.html)，可用来分离常量，使它们无需特定类实例即可使用。伴生对象与其他对象类似，例如某个类的实例。但是，在程序使用期间，只会有一个伴生对象实例存在，正因为如此，这有时被称为[单例模式](https://en.wikipedia.org/wiki/Singleton_pattern)。虽然在此 Codelab 之外有大量关于单例模式的用例，但现在，您需要使用伴生对象这种方法来整理常量，使它们可从 `DetailActivity` 外部访问。首先，您将使用伴生对象来重构“letter”extra 的代码。

1. 在 `DetailActivity` 中 `onCreate` 的上方，添加以下代码：

   ```
   companion object {}
   ```

   请注意，这类似于定义类，只不过您使用的是 `object` 关键字。此外还有关键字 `companion`，这意味着它与 `DetailActivity` 类相关联，我们无需为其提供单独的类型名称。

2. 在大括号内，针对 letter 常量添加一个属性。

   ```
   const val LETTER = "letter"
   ```

3. 如需使用新的常量，请更新 `onCreate()` 中的硬编码字母调用，如下所示：

   ```
   val letterId = intent?.extras?.getString(LETTER).toString()
   ```

   再次提醒，请注意，您可以照常使用点表示法引用该常量，但它属于 `DetailActivity`。

4. 切换到 `LetterAdapter`，然后修改对 `putExtra` 的调用，以使用新常量。

   ```
   intent.putExtra(DetailActivity.LETTER, holder.button.text.toString())
   ```

   设置完毕！通过重构，您让自己的代码更易于阅读，且更易于维护。如果此常量或者您添加的任何其他常量需要更改，您只需在一个位置进行更改即可。



### ④设置隐式 intent

在大多数情况下，您显示的都是自己应用中的特定 activity。不过，在某些情况下，您可能并不知道需要启动哪个 activity 或哪个应用。在我们的详情屏幕上，每个单词都是一个按钮，点击后都将显示该单词的用户定义。

在我们的示例中，您将使用 Google 搜索提供的字典功能。不过，您需要启动设备的浏览器来显示搜索页面，而不是向应用添加新的 activity。

因此，您可能需要一个 intent，用来在 Chrome（Android 上的默认浏览器）中加载相应页面，对吗？

不一定。

有些用户可能更喜欢第三方浏览器。或者，用户的手机上附带制造商预安装的浏览器。也可能他们安装了 Google 搜索应用，甚至是第三方字典应用。

您无法确定用户安装了哪些应用，也无法假设他们可能希望以哪种方式查单词。这是一个完美示例，说明了何时应使用隐式 intent。您的应用向系统提供相关信息，说明应执行何种操作，然后由系统确定如何执行该操作，并根据需要提示用户提供任何其他信息。

执行以下操作，创建隐式 intent：

1. 对于此应用，您将在 Google 搜索中搜索相应单词。第一个搜索结果将是该单词的字典定义。由于每次搜索都会使用相同的基准网址，最好将其定义为自己的常量。在 `DetailActivity` 中，修改伴生对象以添加新的常量 `SEARCH_PREFIX`。这便是 Google 搜索的基准网址。

   ```
   companion object {   const val LETTER = "letter"   const val SEARCH_PREFIX = "https://www.google.com/search?q="}
   ```

2. 然后，打开 `WordAdapter`，并在 `onBindViewHolder()` 方法中对按钮调用 `setOnClickListener()`。首先，为搜索查询创建一个 `URI`。当调用 `parse()` 以从某个 `String` 创建 `URI` 时，您需要使用字符串格式，以便将单词附加到 `SEARCH_PREFIX`。

   ```
   holder.button.setOnClickListener {    val queryUrl: Uri = Uri.parse("${DetailActivity.SEARCH_PREFIX}${item}")}
   ```

   如果您想了解什么是 URI，它并非拼写错误，其全称为 Uniform Resource Identifier，表示统一资源标识符。您可能已经知道，网址（全称为 Uniform Resource Locator，表示统一资源定位符）是指向某个网页的字符串。URI 是一个更为宽泛的格式术语。所有网址都是 URI，但并非所有 URI 都是网址。其他 URI（例如，电话号码对应的地址）可能会以 `tel:` 开头，但会被视为 URN（全称为 Uniform Resource Name，表示统一资源名称），而不是网址。用于表示这两种数据的数据类型被称为 `URI`。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/828cef3fdcfdaed.png" alt="828cef3fdcfdaed.png" style="zoom: 33%;" />

   请注意，此处没有引用您自己应用中的任何 activity。您只是提供一个 `URI`，并未指明其最终的使用方式。

3. 定义 `queryUrl` 后，初始化新的 `intent` 对象

   ```
   val intent = Intent(Intent.ACTION_VIEW, queryUrl)
   ```

   您将 `Intent.ACTION_VIEW` 与 `URI` 一同传入，而不是传入 context 和 activity。

   `ACTION_VIEW` 是一个通用 intent，可以接受 URI（在本例中为网址）。然后，系统就会知道应通过在用户的网络浏览器中打开该 URI 来处理此 intent。一些其他 intent 类型包括：

   - `CATEGORY_APP_MAPS` - 启动地图应用
   - `CATEGORY_APP_EMAIL` - 启动电子邮件应用
   - `CATEGORY_APP_GALLERY` - 启动图库（相册）应用
   - `ACTION_SET_ALARM` - 在后台设置闹钟
   - `ACTION_DIAL` - 拨打电话

   如需了解详情，请访问有关一些[常用 intent](https://developer.android.com/guide/components/intents-common) 的文档。

4. 最后，即使您不启动应用中的任何特定 activity，您也需要通过调用 `startActivity()` 并传入 `intent` 来告知系统启动其他应用。

   ```
   context.startActivity(intent)
   ```

   现在，当您启动应用、导航到单词列表并点按其中某个单词时，您的设备应导航到相应网址（或者根据您安装的应用显示选项列表）。

   具体行为会因用户而异，最终都能为所有用户提供无缝的体验，而不会使代码变得复杂。



### ⑤设置菜单和图标

现在，您已经通过添加显式 intent 和隐式 intent 使您的应用实现了全面可导航，接下来该添加菜单选项了，以便用户能够切换列表和网格布局来显示字母。

| ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/7edb0777b033c159.png) | ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/ce3474dba2a9c1c8.png) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

到现在，您可能已经注意到，许多应用的屏幕顶部都有此栏。这被称为应用栏，除了能够显示应用名称外，它还可以进行自定义，并托管大量实用功能（例如，实用操作的快捷方式或溢出菜单）。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/dda2fc115721ca96.png" alt="dda2fc115721ca96.png" style="zoom:25%;" />

针对此应用，尽管我们不会添加功能齐全的菜单，但您将学习如何向应用栏添加自定义按钮，以便用户能够更改布局。

1. 首先，您需要导入两个表示网格视图和列表视图的图标。添加被称为“模块视图”（将其命名为 **ic_grid_layout**）和“列表视图”（将其命名为 **ic_linear_layout**）的剪贴画矢量资源。如果您需要回顾如何添加 Material 图标，请查看[此页面](https://developer.android.com/codelabs/basic-android-kotlin-training-polished-user-experience?continue=https%3A%2F%2Fdeveloper.android.com%2Fcourses%2Fpathways%2Fandroid-basics-kotlin-unit-2-pathway-1%23codelab-https%3A%2F%2Fdeveloper.android.com%2Fcodelabs%2Fbasic-android-kotlin-training-polished-user-experience#3)中的说明。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/44c530717478f2e6.png" alt="44c530717478f2e6.png" style="zoom: 50%;" />

2. 您还需要通过某种方式来告知系统，应用栏中应显示哪些选项以及应使用哪些图标。为此，请右键点击 **res** 文件夹，然后依次选择 **New > Android Resource File**，以添加新的资源文件。将 **Resource Type** 设置为 `Menu`，并将 **File Name** 设置为 `layout_menu`。

   ![c4f83806a1aa121b.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activities-intents/img/c4f83806a1aa121b.png)

3. 点击 **OK**。

4. 打开 **res/Menu/layout_menu**。将 `layout_menu.xml` 的内容替换为以下代码：

   ```
   <menu xmlns:android="http://schemas.android.com/apk/res/android"   xmlns:app="http://schemas.android.com/apk/res-auto">   <item android:id="@+id/action_switch_layout"       android:title="@string/action_switch_layout"       android:icon="@drawable/ic_linear_layout"       app:showAsAction="always" /></menu>
   ```

   菜单文件的结构非常简单。就像布局以用于存储各个视图的布局管理器开头一样，菜单 XML 文件也以包含各个选项的菜单标记开头。

   您的菜单只有一个按钮，该按钮具有以下几个属性：

   - `id`：与视图一样，菜单选项也有一个 ID，以便在代码中加以引用。
   - `title`：在本例中，此文本实际上并不可见，但它可能有助于屏幕阅读器识别菜单。
   - `icon`：默认值为 `ic_linear_layout`。但是，当用户选择按钮后，系统便会切换显示列表和网格图标。
   - `showAsAction`：此属性可告知系统如何显示该按钮。由于该属性被设置为“always”，对应按钮将始终显示在应用栏中，不会成为溢出菜单的一部分。

   当然，仅设置属性并不意味着菜单会执行任何实际的操作。

   您仍然需要在 `MainActivity.kt` 中添加一些代码，才能使菜单正常运行。



### ⑥实现菜单按钮

若想看到菜单按钮的实际应用，需要在 `MainActivity.kt` 中执行一些操作。

1. 首先，最好创建一个属性来跟踪应用所处的布局状态。这样可以简化切换布局按钮的操作。将默认值设置为 `true`，因为系统将默认使用线性布局管理器。

   ```
   private var isLinearLayoutManager = true
   ```

2. 当用户切换按钮时，您需要将项列表转换为项网格。如果您回想一下学到的 recycler 视图相关知识，会发现有许多不同的布局管理器，其中 `GridLayoutManager` 允许在单行中显示多个项

   ```
   private fun chooseLayout() {    if (isLinearLayoutManager) {        recyclerView.layoutManager = LinearLayoutManager(this)    } else {        recyclerView.layoutManager = GridLayoutManager(this, 4)    }    recyclerView.adapter = LetterAdapter()}
   ```

   此处使用了 `if` 语句来分配布局管理器。除了设置 `layoutManager` 之外，此代码还会分配适配器。`LetterAdapter` 既用于列表布局，也用于网格布局。

3. 您最初使用 XML 设置菜单时，您为其提供的是静态图标。但是，切换布局后，您应更新图标以反映新的功能，即可切换回列表布局。在此，您只需根据下次点按按钮时将切换回的布局，设置线性和网格布局图标。

   ```
   private fun setIcon(menuItem: MenuItem?) {   if (menuItem == null)       return   // Set the drawable for the menu icon based on which LayoutManager is currently in use   // An if-clause can be used on the right side of an assignment if all paths return a value.   // The following code is equivalent to   // if (isLinearLayoutManager)   //     menu.icon = ContextCompat.getDrawable(this, R.drawable.ic_grid_layout)   // else menu.icon = ContextCompat.getDrawable(this, R.drawable.ic_linear_layout)   menuItem.icon =       if (isLinearLayoutManager)           ContextCompat.getDrawable(this, R.drawable.ic_grid_layout)       else ContextCompat.getDrawable(this, R.drawable.ic_linear_layout)}
   ```

   图标是根据 `isLinearLayoutManager` 属性有条件地设置的。

   为了使您的应用真正使用菜单，您需要替换另外两个方法。

   - `onCreateOptionsMenu`：用于膨胀选项菜单并执行任何其他设置。
   - `onOptionsItemSelected`：用于在选中按钮后实际调用 `chooseLayout()`。

4. 按以下方式替换 `onCreateOptionsMenu`：

   ```
   override fun onCreateOptionsMenu(menu: Menu?): Boolean {   menuInflater.inflate(R.menu.layout_menu, menu)   val layoutButton = menu?.findItem(R.id.action_switch_layout)   // Calls code to set the icon based on the LinearLayoutManager of the RecyclerView   setIcon(layoutButton)   return true}
   ```

   这里没有什么特别的。膨胀过布局之后，您需要调用 `setIcon()` 以确保系统根据布局准确显示图标。此方法会返回一个 `Boolean`（此处返回的是 `true`），因为您想要创建选项菜单。

5. 只需再添加另外几行代码，即可实现 `onOptionsItemSelected`，如下所示。

   ```
   override fun onOptionsItemSelected(item: MenuItem): Boolean {   return when (item.itemId) {       R.id.action_switch_layout -> {           // Sets isLinearLayoutManager (a Boolean) to the opposite value           isLinearLayoutManager = !isLinearLayoutManager           // Sets layout and icon           chooseLayout()           setIcon(item)           return true       }       //  Otherwise, do nothing and use the core event handling       // when clauses require that all possible paths be accounted for explicitly,       //  for instance both the true and false cases if the value is a Boolean,       //  or an else to catch all unhandled cases.       else -> super.onOptionsItemSelected(item)   }}
   ```

   每次点按菜单项时，系统都会调用此方法，因此务必要检查点按的是哪个菜单项。您在上面使用了 `when` 语句。如果 `id` 与 `action_switch_layout` 菜单项匹配，您就会否定 `isLinearLayoutManager` 的值。然后，调用 `chooseLayout()` 和 `setIcon()`，以便相应地更新界面。

   在运行应用之前，还需要完成一项操作。由于布局管理器和适配器现在是在 `chooseLayout()` 中设置的，您应替换 `onCreate()` 中的相应代码以调用新的方法。完成更改后，`onCreate()` 应如下所示。

   ```
   override fun onCreate(savedInstanceState: Bundle?) {   super.onCreate(savedInstanceState)   val binding = ActivityMainBinding.inflate(layoutInflater)   setContentView(binding.root)   recyclerView = binding.recyclerView   // Sets the LinearLayoutManager of the recyclerview   chooseLayout()}
   ```

   现在，运行您的应用，您应该能够使用菜单按钮在列表视图和网格视图之间进行切换。



### ⑦小结

- 显式 intent 用于导航到应用中的特定 activity。
- 隐式 intent 对应于特定的操作（例如打开链接或共享图片），并让系统来确定执行相应 intent 的方式。
- 借助菜单选项，您可以向应用栏添加按钮和菜单。
- 伴生对象提供了一种将可重复使用的常量与某种类型（而不是该类型的实例）相关联的方式。

执行 intent 的方法如下：

- 获取对 context 的引用。
- 创建一个 `Intent` 对象，并提供 activity 或 intent 类型（具体取决于是显式还是隐式）。
- 通过调用 `putExtra()` 传递任何需要的数据。
- 调用 `startActivity()`，同时传入 `intent` 对象。



## 3 activity 生命周期的阶段

**下载入门应用**

下载 [DessertClicker 起始代码](https://github.com/google-developer-training/android-basics-kotlin-dessert-clicker-app/tree/starter)，并在 Android Studio 中打开它。

如果您使用 GitHub 中的起始代码，请注意文件夹名称为 `android-basics-kotlin-dessert-clicker-app-starter`。在 Android Studio 中打开项目时，请选择此文件夹。

① 探索生命周期方法并添加基本日志记录

每个 activity 都具有生命周期。这个词源于动植物的生命周期，就像这只蝴蝶的生命周期：蝴蝶的不同状态显示了它从出生到完全成年再到死亡的成长过程。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/c685f48ff799f0c9.png" alt="c685f48ff799f0c9.png" style="zoom:33%;" />

同样，activity 生命周期由 activity 可能会经历的不同状态组成：从 activity  首次初始化，到最终销毁，再由系统收回其内存。当用户启动您的应用、在 activity 之间导航、在应用内外部导航时，activity  会切换状态。下图显示了 activity 生命周期的所有状态。顾名思义，这些状态表示 activity 所处的状态。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/c803811f4cb4034b.png" alt="c803811f4cb4034b.png" style="zoom: 50%;" />

在 activity 生命周期状态发生变化时，您通常需要更改某些行为，或者运行一些代码。因此，`Activity` 类本身以及 `Activity` 的任何子类（例如 `AppCompatActivity`）都会实现一组生命周期回调方法。Android 会在 activity 从一种状态切换为另一种状态时调用这些回调，而您可以在自己的 activity 中替换这些方法，通过执行任务来响应这些生命周期状态变化。下图显示了生命周期状态以及可用的可替换回调。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/f6b25a71cec4e401.png" alt="f6b25a71cec4e401.png" style="zoom:50%;" />

请务必了解要在何时调用这些回调，以及在每个回调方法中应执行的操作。但这两个图都很复杂，可能会令人困惑。在此 Codelab 中，您并不只是要了解每种状态和回调的含义，而是需要进行一些检测工作，逐渐了解发生的情况。

### ①**第 1 步：检查 onCreate() 方法并添加日志记录**

为了弄清 Android 生命周期的一些情况，了解何时调用各种生命周期方法会很有帮助。这有助于您找出 DessertClicker 中出现问题的地方。

一种简单的方式是使用 Android 日志记录功能。通过日志记录功能，您可以在应用运行期间向控制台写入简短的消息，并利用它们来显示不同回调的触发时间。

1. 运行 DessertClicker 应用，并在某款甜点的图片上点按多次。请注意 **Desserts Sold** 的值与美元总金额发生的变化。

2. 打开 `MainActivity.kt` 并检查此 activity 的 `onCreate()` 方法：

   ```
   override fun onCreate(savedInstanceState: Bundle?) {...}
   ```

   在 activity 生命周期图中，您可能认出了 `onCreate()` 方法，因为您之前使用过此回调。这便是每个 activity 都必须实现的方法。您可使用 `onCreate()` 方法为 activity 执行所有一次性初始化。例如，在 `onCreate()` 中，您可以膨胀布局、定义点击监听器或设置视图绑定。

   ![9be2255ff49e0af8.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/9be2255ff49e0af8.png)

   系统会在初始化 activity 之后（在内存中创建新的 `Activity` 对象后）立即调用一次 `onCreate()` 生命周期方法。执行 `onCreate()` 后，相应 activity 会被视为已创建。

   **注意**：替换 `onCreate()` 方法时，您必须调用父类实现来完成 activity 的创建，因此您必须立即调用 `super.onCreate()`。这也适用于其他生命周期回调方法。

3. 在 `onCreate()` 方法中，在对 `super.onCreate()` 的调用后，紧接着添加下面一行代码。

   ```
   Log.d("MainActivity", "onCreate Called")
   ```

4. 根据需要导入 `Log` 类（按 `Alt+Enter`，或者在 Mac 上按 `Option+Enter`，然后选择 **Import**）。如果您启用了自动导入功能，系统应该会自动执行此操作。

   ```
   import android.util.Log
   ```

   [`Log`](https://developer.android.com/reference/kotlin/android/util/Log) 类会将消息写入 **Logcat**。**Logcat** 是用于记录消息的控制台。来自 Android 的关于您应用的消息会出现在这里，包括您使用 `Log.d()` 方法或其他 `Log` 类方法显式发送到日志的消息。

   此命令包含三个部分：

   - 日志消息的优先级，即消息的重要性。在本示例中，[`Log.d()`](https://developer.android.com/reference/kotlin/android/util/Log#d) 方法会写入调试消息。`Log` 类中的其他方法包括 [`Log.i()`](https://developer.android.com/reference/kotlin/android/util/Log#i_1)（表示信息性消息）、[`Log.e()`](https://developer.android.com/reference/kotlin/android/util/Log#e(kotlin.String, kotlin.String))（表示错误）、[`Log.w()`](https://developer.android.com/reference/kotlin/android/util/Log#w(kotlin.String, kotlin.String))（表示警告）或 [`Log.v()`](https://developer.android.com/reference/kotlin/android/util/Log#v_1)（表示详细消息）。
   - 日志标签（第一个参数），在本示例中为 `"MainActivity"`。该标签是一个字符串，可让您更轻松地在 Logcat 中找到自己的日志消息。该标签通常是类的名称。
   - 实际的日志消息（第二个参数）是一个简短的字符串，在本示例中为 `"onCreate called"`。

   **注意**：一种比较好的做法是，在类中声明 TAG 常量：

   ```
   const val TAG = "MainActivity"
   ```

   然后在后续对日志方法的调用中使用该名称，如下所示：

   ```
   Log.d(TAG, "onCreate Called")
   ```

   [编译时常量](https://kotlinlang.org/docs/reference/properties.html#compile-time-constants)是个不会改变的值。在变量声明之前使用 `const` 可将其标记为编译时常量。

5. 编译并运行 DessertClicker 应用。当您点按甜点后，应用行为没有出现任何变化。在 Android Studio 中，点击屏幕底部的 **Logcat** 标签页。

   ![ff9c50376701877f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/ff9c50376701877f.png)

6. 在 **Logcat** 窗口的搜索字段中输入 `D/MainActivity`。

   ![bb0b78600cd47789.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/bb0b78600cd47789.png

   Logcat 可能包含很多消息，大多数消息对您而言都无用。您可以通过多种方式过滤 Logcat 条目，但搜索是最简单的方式。由于您在代码中使用了 `MainActivity` 作为日志标签，因此您可以使用该标签来过滤日志。在开头添加 `D/` 表示这是一条调试消息，由 `Log.d()` 创建。

   您的日志消息包含日期、时间、软件包名称 (`com.example.android.dessertclicker`)、您的日志标签（开头为 `D/`）以及实际消息。由于此消息出现在日志中，所以您会知道 `onCreate()` 已执行。



### ②**第 2 步：实现 onStart() 方法**

系统会在调用 `onCreate()` 生命周期方法之后立即调用 `onStart()`。`onStart()` 运行后，您的 activity 会显示在屏幕上。与为初始化 activity 而仅调用一次的 `onCreate()` 不同，`onStart()` 可在 activity 的生命周期内多次调用。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/385df4ce82ae2de9.png" alt="385df4ce82ae2de9.png" style="zoom: 50%;" />

请注意，`onStart()` 需要与相应的 `onStop()` 生命周期方法配对使用。如果用户启动您的应用后又返回设备的主屏幕，相应 activity 会停止，并且不会再在屏幕上显示。

1. 在 Android Studio 中，打开 `MainActivity.kt` 并将光标移到 `MainActivity` 类中，依次选择 **Code > Override Methods**，或按 `Control+o`（在 Mac 上按 `Command+o`）。此时，系统会显示一个对话框，其中包含您可以在此类中替换的所有方法的庞大清单。<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/e1f2460242b2ae.png" alt="e1f2460242b2ae.png" style="zoom:50%;" />

2. 开始输入 `onStart` 以搜索所需的方法。如需滚动到下一个匹配项，请使用向下箭。从列表中选择 `onStart()`，然后点击 **OK** 插入样板替换代码。代码如下所示：

   ```
   override fun onStart() {    super.onStart()}
   ```

3. 在 `MainActivity.kt` 的顶层（也就是类声明 `class` `MainActivity.` 的上方）添加以下常量。

   ```
   const val TAG = "MainActivity"
   ```

4. 在 `onStart()` 方法中，添加一条日志消息：

   ```
   override fun onStart() {   super.onStart()   Log.d(TAG, "onStart Called")}
   ```

5. 编译并运行 DessertClicker 应用，然后打开 **Logcat** 窗格。在搜索字段中输入 `D/MainActivity`，以过滤日志。请注意，`onCreate()` 和 `onStart()` 方法会依次调用，并且您的 activity 会显示在屏幕上。

6. 按设备上的主屏幕按钮，然后使用“最近使用的应用”屏幕返回相应 activity。请注意，activity 会从上次停止的位置恢复，同时使用所有相同的值，并且 `onStart()` 会再次记录到 Logcat 中。另请注意，系统通常不会再次调用 `onCreate()` 方法。

   ```
   16:19:59.125 31107-31107/com.example.android.dessertclicker D/MainActivity: onCreate Called16:19:59.372 31107-31107/com.example.android.dessertclicker D/MainActivity: onStart Called16:20:11.319 31107-31107/com.example.android.dessertclicker D/MainActivity: onStart Called
   ```

**注意**：在尝试使用设备并观察生命周期回调时，您可能会发现在设备旋转时出现了异常行为。此 Codelab 后面会介绍此行为。



### ③**第 3 步：添加更多日志语句**

在此步骤中，您将为所有其他生命周期方法实现日志记录功能。

1. 替换 `MainActivity` 中其余的生命周期方法，然后为每种方法添加日志语句。代码如下：

   ```
   override fun onResume() {   super.onResume()   Log.d(TAG, "onResume Called")}override fun onPause() {   super.onPause()   Log.d(TAG, "onPause Called")}override fun onStop() {   super.onStop()   Log.d(TAG, "onStop Called")}override fun onDestroy() {   super.onDestroy()   Log.d(TAG, "onDestroy Called")}override fun onRestart() {   super.onRestart()   Log.d(TAG, "onRestart Called")}
   ```

2. 再次编译并运行 DessertClicker，然后检查 Logcat。这一次请注意，除了 `onCreate()` 和 `onStart()` 之外，还有一条有关 `onResume()` 生命周期回调的日志消息。

   ```
   2020-10-16 10:27:33.244 22064-22064/com.example.android.dessertclicker D/MainActivity: onCreate Called2020-10-16 10:27:33.453 22064-22064/com.example.android.dessertclicker D/MainActivity: onStart Called2020-10-16 10:27:33.454 22064-22064/com.example.android.dessertclicker D/MainActivity: onResume Called
   ```

   当 activity 从头开始启动时，您会看到系统按顺序调用以下三个生命周期回调：

   - `onCreate()`：用于创建应用。
   - `onStart()`：用于启动相应 activity，并让其在屏幕上显示。
   - `onResume()`：用于使相应 activity 成为焦点，并让用户能够与其互动。

   `onResume()` 方法尽管名称是这样，但会在启动时调用，即使没有要恢复的 activity 也是如此。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/160054d59f67519.png" alt="160054d59f67519.png" style="zoom:50%;" />

### ④ 探索生命周期用例

现在，DessertClicker 应用已设置好日志记录功能，您可以随时通过各种方式开始使用该应用，并且可以探索如何通过触发生命周期回调来响应这些使用行为。

**用例 1：打开和关闭 activity**

您可以先从最基本的用例入手，也就是首次启动您的应用，然后完全关闭应用。

1. 编译并运行 DessertClicker 应用（如果该应用尚未运行）。正如您所看到的，当 activity 首次启动时，系统会调用 `onCreate()`、`onStart()` 和 `onResume()` 回调。

   ```
   2020-10-16 10:27:33.244 22064-22064/com.example.android.dessertclicker D/MainActivity: onCreate Called2020-10-16 10:27:33.453 22064-22064/com.example.android.dessertclicker D/MainActivity: onStart Called2020-10-16 10:27:33.454 22064-22064/com.example.android.dessertclicker D/MainActivity: onResume Called
   ```

2. 多次点按纸杯蛋糕。

3. 点按设备上的**返回**按钮。请注意，在 Logcat 中，系统将按上述顺序调用 `onPause()`、`onStop()` 和 `onDestroy()`。

   ```
   2020-10-16 10:31:53.850 22064-22064/com.example.android.dessertclicker D/MainActivity: onPause Called2020-10-16 10:31:54.620 22064-22064/com.example.android.dessertclicker D/MainActivity: onStop Called2020-10-16 10:31:54.622 22064-22064/com.example.android.dessertclicker D/MainActivity: onDestroy Called
   ```

   在本示例中，使用**返回**按钮会导致 activity（和应用）完全关闭。执行 `onDestroy()` 方法意味着相应 activity 已完全关闭，可以进行垃圾回收。[垃圾回收](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science))是指自动清理您不再使用的对象。调用 `onDestroy()` 后，系统会知道这些资源是可丢弃的，然后开始清理这部分内存。 如果您的代码手动调用该 activity 的 [`finish()`](https://developer.android.com/reference/android/app/Activity.html#finish()) 方法，或者用户强行退出该应用（例如，用户强行退出，或在“最近使用的应用”屏幕关闭该应用），您的 activity  也可能会完全关闭。如果您的应用长时间没有在屏幕上显示，Android 系统也可能会自行关闭您的 activity。Android  这样做是为了节省电量，同时允许其他应用使用您应用的资源。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/2dcc4d9c6478a9f4.png" alt="2dcc4d9c6478a9f4.png" style="zoom:50%;" />

4. 返回 DessertClicker 应用，方法是在[概览屏幕](https://support.google.com/android/answer/9079644?hl=zh-CN)中找到所有打开的应用。（注意，这也称为“最近使用的应用”屏幕或“最近用过的应用”）中找到所有打开的应用。以下是 Logcat 中的日志：

   ```
   2020-10-16 10:31:54.622 22064-22064/com.example.android.dessertclicker D/MainActivity: onDestroy Called2020-10-16 10:38:00.733 22064-22064/com.example.android.dessertclicker D/MainActivity: onCreate Called2020-10-16 10:38:00.787 22064-22064/com.example.android.dessertclicker D/MainActivity: onStart Called2020-10-16 10:38:00.788 22064-22064/com.example.android.dessertclicker D/MainActivity: onResume Called
   ```

   相应 activity 在上一步中已被销毁，因此当您返回该应用时，Android 会启动一个新的 activity 并调用 `onCreate()`、`onStart()` 和 `onResume()` 方法。请注意，前一个 activity 中的 DessertClicker 日志并未保留。

   **注意**：此处的要点是，在单个 activity 实例的生命周期内，`onCreate()` 和 `onDestroy()` 仅调用了一次：`onCreate()` 用于首次初始化应用，`onDestroy()` 则用于清理您的应用所用的资源。

   `onCreate()` 方法是重要的一步；在此方法中，您会执行所有的首次初始化，通过膨胀首次设置其布局，以及对变量进行初始化。



**用例 2：离开和返回 activity**

现在，您已经启动了应用并将其完全关闭，在此过程中，您看到了 activity 首次创建时经历的大部分生命周期状态。此外，您还看到了  activity 在完全关闭和销毁过程中经历的所有生命周期状态。但当用户与其 Android  设备交互时，他们需要在应用之间切换、返回主屏幕、启动新应用以及处理由通话等其他 activity 导致的中断。

每次用户离开您的 activity 时，它都不会关闭：

- 当 activity 不再在屏幕上可见时，就说明该 activity 已置于后台（与之相反的是 activity 位于前台或屏幕上）。
- 当用户返回您的应用时，相应 activity 会重启并再次可见。这部分生命周期称为应用的可见生命周期。

当您的应用位于后台时，为使系统资源和电池续航时间保持正常，应用通常不应活跃运行。您可以使用 `Activity` 生命周期及其回调来了解应用何时切换到后台，以便您暂停任何正在进行的操作。然后，在您的应用进入前台时重启相应操作。

在这一步中，您将查看当应用进入后台以及返回前台时的 activity 生命周期。

在 DessertClicker 应用运行时，点击几次纸杯蛋糕。

按设备上的**主屏幕**按钮，然后在 Android Studio 中观察 Logcat。返回主屏幕的操作会将您的应用置于后台，而不是完全关闭应用。请注意，系统会调用 `onPause()` 方法和 `onStop()` 方法，但不会调用 `onDestroy()`。

```
2020-10-16 10:41:05.383 22064-22064/com.example.android.dessertclicker D/MainActivity: onPause Called2020-10-16 10:41:05.966 22064-22064/com.example.android.dessertclicker D/MainActivity: onStop Called
```

在调用 `onPause()` 后，该应用不会再获得焦点。在 `onStop()` 之后，该应用将不再显示在屏幕上。虽然该 activity 已停止，但 `Activity` 对象仍位于内存中（在后台）。该 activity 尚未销毁。用户可能会返回该应用，因此 Android 会保留您的 activity 资源。![b488b32801220b79.png](https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/b488b32801220b79.png)

使用“最近使用的应用”屏幕返回该应用。请注意，在 Logcat 中，该 activity 使用 `onRestart()` 和 `onStart()` 重启，然后使用 `onResume()` 恢复。

```
2020-10-16 10:42:18.144 22064-22064/com.example.android.dessertclicker D/MainActivity: onRestart Called2020-10-16 10:42:18.158 22064-22064/com.example.android.dessertclicker D/MainActivity: onStart Called2020-10-16 10:42:18.158 22064-22064/com.example.android.dessertclicker D/MainActivity: onResume Called
```

当该 activity 返回前台时，系统不会再次调用 `onCreate()` 方法。相应 activity 对象未被销毁，因此不需要重新创建。系统会调用 `onRestart()` 方法，而不是 `onCreate()`。请注意，这一次该 activity 返回前台时，系统会保留 **Desserts Sold** 数值。

除 DessertClicker 以外，至少启动一个应用，这样设备的“最近使用的应用”屏幕中就会有一些应用。

启动“最近使用的应用”屏幕，然后打开另外一个近期 activity。然后，返回最近用过的应用并让 DessertClicker 返回前台。

请注意，您在 Logcat 这里看到的回调与按主屏幕按钮后看到的相同。当应用进入后台时，系统会调用 `onPause()` 和 `onStop()`，并在应用返回时调用 `onRestart()`、`onStart()` 和 `onResume()`。



**注意**：此处的要点是，当用户导航到该 activity 或离开该 activity 时，系统会多次调用 `onStart()` 和 `onStop()`。

当应用停止并转到后台时，或应用在返回前台后再次启动时，系统会调用这些方法。在这些情况下，如果您需要在应用中执行一些工作，则可以替换相关的生命周期回调方法。

`onRestart()` 又是什么情况呢？`onRestart()` 方法与 `onCreate()` 非常相似。无论是 `onCreate()` 还是 `onRestart()`，都会在相应 activity 变得可见之前调用。`onCreate()` 方法只在第一次被调用，之后会调用 `onRestart()`。`onRestart()` 方法用于放置仅在 activity **不**是首次启动时才需要调用的代码。



**用例 3：隐藏部分 activity**

您已了解，在应用启动并且系统调用 `onStart()` 后，该应用将在屏幕上变得可见。当应用恢复并且系统调用 `onResume()` 后，应用可获得用户焦点，即，用户可以与应用交互。应用在屏幕上完全显示并且具有用户焦点时的这部分生命周期称为“交互式”生命周期。

当应用进入后台后，焦点在 `onPause()` 后便会丢失，并且在 `onStop()` 后，该应用将不再可见。

焦点与可见性之间的区别非常重要，因为 activity 有可能是在屏幕上部分可见，但没有用户焦点。在这一步，您将查看 activity 处于部分可见状态，但没有用户焦点的情况。

1. 在 DessertClicker 应用运行时，点击屏幕右上角的**共享**按钮。

2. 共享 activity 出现在屏幕的下半部分，但相应 activity 在上半部分仍然可见。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/e2319779260eb5ee.png" alt="e2319779260eb5ee.png" style="zoom:33%;" />

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/9ddc8b1dc79b1bff.png" alt="9ddc8b1dc79b1bff.png" style="zoom:33%;" />

   

3. 检查 Logcat，您会注意到，系统仅调用了 `onPause()`。

   ```
   2020-10-16 11:00:53.857 22064-22064/com.example.android.dessertclicker D/MainActivity: onPause Called
   ```

   在此用例中，系统没有调用 `onStop()`，因为相应 activity 仍然部分可见。但是，该 activity 没有用户焦点，并且用户无法与之交互；位于前台的“共享”activity 具有用户焦点。

   为什么这种区别至关重要？单纯的 `onPause()` 导致的中断通常会持续很短时间，然后用户就会返回您的 activity，或者导航到另一个 activity 或应用。通常，您需要持续更新界面，使应用的其余部分不会卡顿。

   在 `onPause()` 中运行的任何代码都会阻止其他内容显示，因此请使 `onPause()` 中的代码保持轻量级。例如，当有来电时，`onPause()` 中的代码可能会延迟来电通知。

4. 在共享对话框之外点击一下，返回应用，您会注意到系统调用了 `onResume()`。

   `onResume()` 和 `onPause()` 都必须处理焦点。当相应 activity 具有焦点时，系统会调用 `onResume()` 方法；当该 activity 失去焦点时，系统会调用 `onPause()`。

   

### ⑤探索配置变更

activity 生命周期管理中的另一个用例也很重要：配置变更会如何影响 activity 生命周期。

当设备的状态发生了根本性改变，以至于系统解决改变的最简单方式就是完全关闭并重建 activity 时，就会发生配置变更。例如，如果用户更改了设备语言，整个布局可能就需要更改为适应不同的文本方向和字符串长度。如果用户将设备插入基座或添加物理键盘，应用布局可能需要利用不同的显示尺寸或布局。如果设备屏幕方向发生变化，比如设备从纵向旋转为横向或反过来，布局可能需要改为适应新的屏幕方向。让我们看看应用在这种情况下的行为。

**设备旋转时出现数据丢失情况**

1. 编译并运行您的应用，然后打开 Logcat。

2. 将设备或模拟器旋转为横屏模式。您可以使用旋转按钮或 `Control` 和箭头键（在 Mac 上，则为 `Command` 和箭头键）来向左或向右旋转模拟器。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/623fce7c623d42bd.png" alt="623fce7c623d42bd.png" style="zoom:33%;" />

3. 检查 Logcat 中的输出。用 `MainActivity` 过滤输出。

   ```
   2021-09-23 22:26:53.941 6636-6636/com.example.android.dessertclicker D/MainActivity: onPause Called2021-09-23 22:26:53.944 6636-6636/com.example.android.dessertclicker D/MainActivity: onStop Called2021-09-23 22:26:53.945 6636-6636/com.example.android.dessertclicker D/MainActivity: onDestroy Called2021-09-23 22:26:53.987 6636-6636/com.example.android.dessertclicker D/MainActivity: onCreate Called2021-09-23 22:26:54.046 6636-6636/com.example.android.dessertclicker D/MainActivity: onStart Called2021-09-23 22:26:54.048 6636-6636/com.example.android.dessertclicker D/MainActivity: onResume Called2021-09-23 22:27:13.276 6636-6636/com.example.android.dessertclicker D/MainActivity: onPause Called2021-09-23 22:27:13.280 6636-6636/com.example.android.dessertclicker D/MainActivity: onStop Called2021-09-23 22:27:13.281 6636-6636/com.example.android.dessertclicker D/MainActivity: onDestroy Called2021-09-23 22:27:13.323 6636-6636/com.example.android.dessertclicker D/MainActivity: onCreate Called2021-09-23 22:27:13.383 6636-6636/com.example.android.dessertclicker D/MainActivity: onStart Called2021-09-23 22:27:13.384 6636-6636/com.example.android.dessertclicker D/MainActivity: onResume Called
   ```

   请注意，设备或模拟器旋转屏幕时，系统会调用所有生命周期回调来关闭相应 activity。然后，在重新创建 activity 时，系统会调用所有生命周期回调来启动相应 activity。

4. 当设备旋转，而相应 activity 被关闭并重新创建时，该 activity 会使用默认值启动 - 已售甜点的数量和收入会归零。



### ⑥使用 onSaveInstanceState() 保存 bundle 数据

`onSaveInstanceState()` 方法是一个回调，用于保存 `Activity` 被销毁后可能需要的任何数据。在生命周期回调图中，系统会在相应 activity 停止后调用 `onSaveInstanceState()`。每当您的应用进入后台时，系统都会调用它。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/c259ab6beca0ca88.png" alt="c259ab6beca0ca88.png" style="zoom:50%;" />

请将 `onSaveInstanceState()` 调用视为一项安全措施；这让您有机会在相应 activity 退出前台时将少量信息保存到 bundle 中。系统现在会保存这些数据，这是因为如果等到关闭应用时再保存，系统可能会面临资源压力。

**注意**：有时，Android 会关闭整个应用进程，包括与应用相关联的每个 activity。Android  会在系统承受压力并面临视觉延迟风险时执行此类关闭操作，因此此时不会运行额外的回调或代码。应用的进程只会在后台静默地关闭。但对用户来说，应用似乎并没有关闭。当用户返回 Android 系统已关闭的应用时，Android 会重启相应应用。您需要确保发生这种情况时不会对用户造成任何数据损失。

每次都保存数据可以确保 bundle 中的更新数据可以根据需要恢复。

1. 在 `MainActivity` 中，替换 `onSaveInstanceState()` 回调，并添加日志语句。

   ```
   override fun onSaveInstanceState(outState: Bundle) {   super.onSaveInstanceState(outState)   Log.d(TAG, "onSaveInstanceState Called")}
   ```

   **注意**：`onSaveInstanceState()` 有两个替换项，一个仅包含 `outState` 参数，另一个包含 `outState` 和 `outPersistentState` 参数。请使用上述代码中包含单个 `outState` 参数的那个替换项。

2. 编译并运行应用，然后点击**主屏幕**按钮，使其进入后台。请注意，`onSaveInstanceState()` 回调是紧接着 `onPause()` 和 `onStop()` 发生的：

   ```
   2021-09-23 22:37:16.588 12321-12321/com.example.android.dessertclicker D/MainActivity: onPause Called2021-09-23 22:37:16.591 12321-12321/com.example.android.dessertclicker D/MainActivity: onStop Called2021-09-23 22:37:16.592 12321-12321/com.example.android.dessertclicker D/MainActivity: onSaveInstanceState Called2021-09-23 22:37:16.592 12321-12321/com.example.android.dessertclicker D/MainActivity: onDestroy Called2021-09-23 22:37:16.636 12321-12321/com.example.android.dessertclicker D/MainActivity: onCreate Called2021-09-23 22:37:16.719 12321-12321/com.example.android.dessertclicker D/MainActivity: onStart Called2021-09-23 22:37:16.720 12321-12321/com.example.android.dessertclicker D/MainActivity: onResume Called
   ```

   

3. 在文件顶部（就在类定义之前）添加下列常量：

   ```
   const val KEY_REVENUE = "revenue_key"const val KEY_DESSERT_SOLD = "dessert_sold_key"
   ```

   您将使用这些键将数据保存到实例状态 bundle 以及从中检索数据。

4. 向下滚动到 `onSaveInstanceState()`，您会注意到 `outState` 参数，其类型为 `Bundle`。

   [`Bundle`](https://developer.android.com/reference/kotlin/android/os/Bundle) 是键值对的集合，其中的键始终为字符串。您可以将简单数据（例如 `Int` 和 `Boolean` 值）放入 bundle 中。由于系统会将此 bundle 保留在内存中，因此最佳做法是让 bundle 中的数据量少一点。此 bundle 的大小也有限，但其大小因设备而异。如果您存储的数据过多，可能会面临应用崩溃并出现 `TransactionTooLargeException` 错误的风险。

5. 在 `onSaveInstanceState()` 中，通过 `putInt()` 方法将 `revenue` 值（整数）放入 bundle 中：

   ```
   outState.putInt(KEY_REVENUE, revenue)
   ```

   `putInt()` 方法（以及 `Bundle` 类中类似的方法，如 `putFloat()` 和 `putString()`）采用两个参数：键的字符串（`KEY_REVENUE` 常量）以及要保存的实际值。

6. 对已售甜点数量重复上述过程：

   ```
   outState.putInt(KEY_DESSERT_SOLD, dessertsSold)
   ```



### ⑦使用 onCreate() 恢复 bundle 数据

activity 状态可以在 `onCreate(Bundle)` 或 [`onRestoreInstanceState(Bundle)`](https://developer.android.com/reference/android/app/Activity#onRestoreInstanceState(android.os.Bundle)) 中恢复（通过 `onSaveInstanceState()` 方法填充的 `Bundle` 将传递给这两种生命周期回调方法）。

1. 向上滚动到 `onCreate()`，并检查方法签名：

   ```
   override fun onCreate(savedInstanceState: Bundle) {
   ```

   请注意，`onCreate()` 会在每次调用时都获取 `Bundle`。当您的 activity 因进程关闭而重启时，您保存的 bundle 会传递给 `onCreate()`。如果您的 activity 重新启动了，那么 `onCreate()` 中的这个 `Bundle` 将是 `null`。因此，如果 bundle 不是 `null`，您就会知道自己是在基于一个先前已知的点重新创建该 activity。

   **注意**：如果重新创建了 activity，`onRestoreInstanceState()` 回调会在 `onStart()` 之后随 bundle 一起调用。大多数情况下，您会将 activity 的状态恢复为 `onCreate()`。但是，由于 `onRestoreInstanceState()` 是在 `onStart()` 之后调用的，因此，如果您在系统调用 `onCreate()` 后需要恢复为某种状态，则可以使用 `onRestoreInstanceState()`。

2. 将此代码添加到 `onCreate()`（紧跟在设置 `binding` 变量的代码之后）：

   ```
   if (savedInstanceState != null) {   revenue = savedInstanceState.getInt(KEY_REVENUE, 0)}
   ```

   通过测试是否有 `null`，可以确定 bundle 中是否存在数据，或者 bundle 是否为 `null`，进而告知您应用是重新启动过，还是在关闭后重新创建过。此测试是从 bundle 恢复数据的常见模式。

   请注意，您在此处使用的键 (`KEY_REVENUE`) 与用于 `putInt()` 的键相同。为确保每次都使用相同的键，最佳做法是将这些键定义为常量。`getInt()` 用于从 bundle 中获取数据，就像您之前使用 `putInt()` 将数据放到 bundle 中一样。`getInt()` 方法采用两个参数：

   - 一个充当键的字符串，例如 `"key_revenue"`（表示收入值）。
   - 相应键在 bundle 中不存在值的情况下的默认值。

   然后，您从 bundle 获取的整数将分配给 `revenue` 变量，并且界面将使用该值。

3. 添加 `getInt()` 方法，以恢复收入和已售甜点数量。

   ```
   if (savedInstanceState != null) {   revenue = savedInstanceState.getInt(KEY_REVENUE, 0)   dessertsSold = savedInstanceState.getInt(KEY_DESSERT_SOLD, 0)}
   ```

4. 编译并运行应用。按纸杯蛋糕至少五次，直到屏幕画面切换到甜甜圈。

5. 旋转设备。请注意，这一次，该应用显示的是来自 bundle 的正确收入和已售甜点数量值。另请注意，甜点已恢复为纸杯蛋糕。您还需要完成另一项工作，才能确保该应用从关闭状态完全恢复为原来的状态。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-activity-lifecycle/img/4179956182ffc634.png" alt="4179956182ffc634.png" style="zoom: 33%;" />

6. 在 `MainActivity` 中，检查 `showCurrentDessert()` 方法。请注意，此方法会根据当前已售的甜点数量以及 `allDesserts` 变量中的甜点清单，决定在 activity 中显示哪张甜点图片。

   ```
   for (dessert in allDesserts) {   if (dessertsSold >= dessert.startProductionAmount) {       newDessert = dessert   }    else break}
   ```

   此方法依赖于已售甜点的数量来选择正确的图片。因此，您无需执行任何操作，即可在 `onSaveInstanceState()` 中将对图片的引用存储到 bundle 内。在该 bundle 中，您已经存储了已售甜点的数量。

7. 在 `onCreate()` 中，在用于从 bundle 恢复状态的代码块中，调用 `showCurrentDessert()`：

   ```
    if (savedInstanceState != null) {   revenue = savedInstanceState.getInt(KEY_REVENUE, 0)   dessertsSold = savedInstanceState.getInt(KEY_DESSERT_SOLD, 0)   showCurrentDessert()}
   ```

8. 编译并运行应用，然后旋转屏幕。请注意，现在，已售甜点数量和总收入的值以及甜点图片均已正确恢复。



### ⑧小结

**activity 生命周期**

- activity 生命周期是 activity 会切换的一组状态。 activity 生命周期在 activity 首次创建时开始，到 activity 被销毁时结束。
- 当用户在 activity 之间以及应用内外导航时，每个 activity 会在 activity 生命周期中的状态之间切换。
- activity 生命周期中的每种状态都有一个对应的回调方法，您可以在 `Activity` 类中替换此类方法。核心的生命周期方法集合包括：[`onCreate()`](https://developer.android.com/reference/android/app/Activity.html#onCreate(android.os.Bundle))[`onStart()`](https://developer.android.com/reference/android/app/Activity.html#onStart())[`onPause()`](https://developer.android.com/reference/android/app/Activity.html#onPause())[`onRestart()`](https://developer.android.com/reference/android/app/Activity.html#onRestart())[`onResume()`](https://developer.android.com/reference/android/app/Activity.html#onResume())[`onStop()`](https://developer.android.com/reference/android/app/Activity.html#onStop())[`onDestroy()`](https://developer.android.com/reference/android/app/Activity.html#onDestroy())
- 如需添加要在 activity 转换为某种生命周期状态时发生的行为，请替换相应状态的回调方法。
- 如需在 Android Studio 中为类添加框架替换方法，请依次选择 **Code > Override Methods**，或按 `Control+o`（在 Mac 上按 `Command+o`）

**使用日志进行记录**

- 借助 Android 日志记录 API（尤其是 [`Log`](https://developer.android.com/reference/android/util/Log) 类），您可以写入要在 Android Studio 内的 Logcat 中显示的简短消息。
- 使用 `Log.d()` 可写入调试消息。此方法采用两个参数：日志标签（通常是类的名称）和日志消息（一个简短的字符串）。
- 使用 Android Studio 中的 **Logcat** 窗口可查看系统日志，包括您写入的消息。

**保留 activity 状态**

- 当您的应用进入后台时（就在系统调用 `onStop()` 之后），应用数据可保存到 bundle 中。系统会自动为您保存一些应用数据（例如 `EditText` 的内容）。
- bundle 是 [`Bundle`](https://developer.android.com/reference/kotlin/android/os/Bundle) 的实例，是键和值的集合。键始终是字符串。
- 使用 `onSaveInstanceState()` 回调可将其他数据保存到您要保留的 bundle 中，即使应用自动关闭也是如此。如需将数据放入 bundle，请使用以 `put` 开头的 bundle 方法，例如 `putInt()`。
- 您可以通过 `onRestoreInstanceState()` 方法从 bundle 中重新获取数据，更常用的方式是使用 `onCreate()`。`onCreate()` 方法有一个用于存储 bundle 的 `savedInstanceState` 参数。
- 如果 `savedInstanceState` 变量为 `null`，则表示 activity 启动时没有状态 bundle，并且没有可以检索的状态数据。
- 如需使用键从 bundle 中检索数据，请使用以 `get` 开头的 `Bundle` 方法，例如 `getInt()`。

**配置变更**

- 当设备的状态发生了根本性改变，以至于系统解决改变的最简单方式就是销毁并重建 activity 时，就会发生配置变更。
- 最常见的配置变更示例是用户将设备从纵向旋转为横屏模式，或者从横向转为纵向模式。当设备语言发生变化或插入硬件键盘时，也会发生配置变更。
- 当发生配置变更时，Android 会调用所有 activity 生命周期的关闭回调。然后，Android 会从头开始重启相应 activity，同时运行所有生命周期启动回调。
- 当 Android 因配置变更而关闭某个应用时，它会使用对 `onCreate()` 可用的状态 bundle 重启相应 activity。
- 与进程关闭一样，系统会通过 `onSaveInstanceState()` 将应用的状态保存到 bundle 中。



## 4 Android Jetpack：导航组件                

### ①fragment 和 Navigation 组件 

在“activity 和 intent”Codelab 中，您在 [Words](https://github.com/google-developer-training/android-basics-kotlin-words-app/tree/activities) 应用中添加了 intent，以便在两个 activity 之间导航。尽管这是一种有用的导航模式，但它只是为您的应用制作动态界面的一部分。许多  Android 应用不需要每个屏幕都有单独的 activity。实际上，许多常见的界面模式（例如标签页）都存在于名为“fragment”的单个  activity 中。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/586ff7b88b0d2455.png" alt="586ff7b88b0d2455.png" style="zoom:33%;" />

[fragment](https://developer.android.com/guide/fragments) 是可重复使用的界面片段；fragment 可以嵌入一个或多个 activity  中并重复使用。在上面的屏幕截图中，点按标签页不会触发用于显示下一个屏幕的 intent。切换标签页只会将上一个 fragment 替换为另一个  fragment。所有这些操作均不会启动另一个 activity。

您甚至可以在一个屏幕上同时显示多个 fragment，例如平板电脑设备的主/从布局。在下面的示例中，左侧导航界面和右侧的内容都可以包含在一个独立的 fragment 内。这两个 fragment 同时存在于同一 activity 中。

![92f1ecb9aadb7797.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/92f1ecb9aadb7797.png)

如您所见，fragment 是构建高质量应用不可或缺的一部分。在此 Codelab 中，您将学习 fragment 的基础知识，并通过转换 Words 应用来使用它们。此外，您还将了解如何使用 Jetpack [Navigation 组件](https://developer.android.com/guide/navigation/navigation-getting-started)，借助名为**导航图**的新资源文件在同一宿主 activity 中的 fragment 之间导航。此 Codelab 结束时，您将掌握在下一款应用中实现 fragment 所需的基本技能。

### ②fragment 和 fragment 生命周期

fragment 就是可重复使用的应用界面片段。与 activity 类似，fragment 具有生命周期并可以响应用户输入。fragment  在屏幕上显示时，会始终包含在 activity 的视图层次结构中。由于 fragment 侧重于可重用性和模块化，因此甚至可以由单个  activity 同时托管多个 fragment。每个 fragment 都管理着自己单独的生命周期。

**fragment 生命周期**

和 activity 一样，fragment 可以初始化以及从内存中移除；在整个存在期间，fragment  也会在屏幕上显示、消失和重新显示。此外，与 activity 类似，fragment  也有具有多种状态的生命周期，并提供了几种可替换的方法来响应它们之间的转换。fragment 生命周期有五种状态，由 [Lifecycle.State](https://developer.android.com/reference/kotlin/androidx/lifecycle/Lifecycle.State) 枚举表示。

- INITIALIZED：fragment 的一个新实例已实例化。
- CREATED：系统已调用第一批 fragment 生命周期方法。在 fragment 处于此状态期间，系统也会创建与其关联的视图。
- STARTED：fragment 在屏幕上可见，但没有焦点，这意味着其无法响应用户输入。
- RESUMED：fragment 可见并已获得焦点。
- DESTROYED：fragment 对象已解除实例化。



此外，与 activity 类似，[`Fragment`](https://developer.android.com/reference/android/app/Fragment) 类还提供了多种可替换的方法来响应生命周期事件。

- `onCreate()`：fragment 已实例化并处于 `CREATED` 状态。不过，其对应的视图尚未创建。
- `onCreateView()`：此方法可用于膨胀布局。fragment 已进入 `CREATED` 状态。
- `onViewCreated()`：此方法在创建视图后调用。在此方法中，您通常会通过调用 `findViewById()` 将特定视图绑定到属性。
- `onStart()`：fragment 已进入 `STARTED` 状态。
- `onResume()`：fragment 已进入 `RESUMED` 状态，现已具有焦点（可响应用户输入）。
- `onPause()`：fragment 已重新进入 `STARTED` 状态。相应界面对用户可见。
- `onStop()`：fragment 已重新进入 `CREATED` 状态。该对象已实例化，但它在屏幕上不再显示。
- `onDestroyView()`：该方法在 fragment 进入 `DESTROYED` 状态之前调用。视图已从内存中移除，但 fragment 对象仍然存在。
- `onDestroy()`：fragment 进入 `DESTROYED` 状态。

下图总结了 fragment 生命周期以及状态之间的转换。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/74470aacefa170bd.png" alt="74470aacefa170bd.png" style="zoom:33%;" />

生命周期状态和回调方法与用于 activity 的方法非常相似。但请注意 `onCreate()` 方法的差异。通过 activity，您可以使用此方法膨胀布局和绑定视图。不过，在 fragment 生命周期中，系统会在创建视图之前调用 `onCreate()`，所以您无法在此处膨胀布局。您可以改为在 `onCreateView()` 中执行此操作。然后，在创建视图后，系统会调用 `onViewCreated()` 方法，您可以在该方法中将属性绑定到特定视图。

虽然这可能听起来理论性很强，但您已经基本了解 fragment 的工作原理以及它们与 activity 的相似之处和不同之处。在此  Codelab 的其余部分，您将实际运用这些知识。首先，您需要迁移之前使用的 Words 应用，以使用基于 fragment  的布局。然后，您可以在单个 activity 内的多个 fragment 之间实现导航。



### ③创建 fragment 和布局文件

和 activity 一样，您添加的每个 fragment 都由两个文件组成：一个用于布局的 XML 文件，以及一个用于显示数据和处理用户互动的 Kotlin 类。您将为字母列表和字词列表添加一个 fragment。

1. 在项目导航器中选择**应用**，添加以下 fragment (**File > New > Fragment > Fragment (Blank)**)，系统应为每个 fragment 生成一个类和布局文件。

   - 对于第一个 fragment，请将 **Fragment Name** 设置为 `LetterListFragment`。**Fragment Layout Name** 应填充为 `fragment_letter_list`。

   ![898650e4cd0b2486.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/898650e4cd0b2486.png)

   - 对于第二个 fragment，请将 **Fragment Name** 设置为 `WordListFragment`。**Fragment Layout Name** 应填充为 `fragment_word_list.xml`。

   ![4f04fca641487da1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/4f04fca641487da1.png)

2. 为两个 fragment 生成的 Kotlin 类包含了很多在实现 fragment 时常用的样板代码。不过，如果您是首次学习 fragment，请直接删除这两个文件中除 `LetterListFragment` 和 `WordListFragment` 类声明以外的所有内容。我们将引导您从头开始实现这些 fragment，以便您了解所有代码的工作原理。删除样板代码后，Kotlin 文件应如下所示。

   **LetterListFragment.kt**

   ```
   package com.example.wordsappimport androidx.fragment.app.Fragmentclass LetterListFragment : Fragment() {}
   ```

   **WordListFragment.kt**

   ```
   package com.example.wordsappimport androidx.fragment.app.Fragmentclass WordListFragment : Fragment() {}
   ```

3. 将 `activity_main.xml` 的内容复制到 `fragment_letter_list.xml` 中，并将 `activity_detail.xml` 的内容复制到 `fragment_word_list.xml` 中。将 `fragment_letter_list.xml` 中的 `tools:context` 更新为 `.LetterListFragment`，并将 `fragment_word_list.xml` 中的 `tools:context` 更新为 `.WordListFragment`。

   完成更改后，fragment 布局文件应如下所示。

   **fragment_letter_list.xml**

   ```
   <?xml version="1.0" encoding="utf-8"?><FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"   xmlns:tools="http://schemas.android.com/tools"   android:layout_width="match_parent"   android:layout_height="match_parent"   tools:context=".WordListFragment">   <androidx.recyclerview.widget.RecyclerView       android:id="@+id/recycler_view"       android:layout_width="match_parent"       android:layout_height="match_parent"       android:clipToPadding="false"       android:padding="16dp" /></FrameLayout>
   ```

   **fragment_word_list.xml**

   ```
   <?xml version="1.0" encoding="utf-8"?><FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"   xmlns:tools="http://schemas.android.com/tools"   android:layout_width="match_parent"   android:layout_height="match_parent"   tools:context=".WordListFragment">   <androidx.recyclerview.widget.RecyclerView       android:id="@+id/recycler_view"       android:layout_width="match_parent"       android:layout_height="match_parent"       android:clipToPadding="false"       android:padding="16dp"       tools:listitem="@layout/item_view" /></FrameLayout>
   ```

### ④ 实现 LetterListFragment

与 activity 一样，您需要膨胀布局并绑定各个视图。使用 fragment 生命周期时，只存在一些细微差别。我们将引导您完成设置 `LetterListFragment` 的流程，然后您将有机会对 `WordListFragment` 执行相同的操作。

如需在 `LetterListFragment` 中实现视图绑定，您首先需要获取对 `FragmentLetterListBinding` 的可为 null 的引用。在 **build.gradle** 文件的 `buildFeatures` 部分下启用 `viewBinding` 属性后，Android Studio 会为每个布局文件生成这样的绑定类。您只需要在 fragment 类中为 `FragmentLetterListBinding` 内的每个视图分配属性即可。

类型应为 `FragmentLetterListBinding?`，其初始值应为 `null`。为何要将它设置为可为 null？由于在调用 `onCreateView()` 之前，您无法膨胀布局。在 `LetterListFragment` 的实例创建（其生命周期以 `onCreate()` 开头）之后，要等待一段时间，此属性才会实际可用。另请注意，fragment 的视图可以在 fragment 的整个生命周期内多次创建和销毁。因此，您还需要在另一个生命周期方法 `onDestroyView()` 中重置该值。

1. 在 `LetterListFragment.kt` 中，首先获取对 `FragmentLetterListBinding` 的引用，并将引用命名为 `_binding`。

   ```
   private var _binding: FragmentLetterListBinding? = null
   ```

   由于它可为 null，因此，每当您访问 `_binding` 的属性（例如 `_binding?.someView`）时，您都需要添加 `?` 以确保 null 安全。不过，这并不意味着您仅仅因为一个 null 值就必须在代码中散放英文问号。如果您确定某个值在您访问时不会为 null，则可以在其类型名称后面加上 `!!`。然后，您可以像访问任何其他属性一样访问它，而不使用 `?` 运算符。

   **注意**：使用 `!!` 将某个变量设置为可为 null 时，最好仅将其用在您知道值不会为 null 的一个或多个位置，就像您知道 `_binding` 在 `onCreateView()` 中进行分配之后会有值一样。以这种方式访问可为 null 的值非常危险，会导致崩溃，因此请尽可能谨慎。

2. 创建一个名为 binding（不加下划线）的新属性，并将其设置为 `_binding!!`。

   ```
   private val binding get() = _binding!!
   ```

   在这里，`get()` 表示此属性仅供获取。也就是说，您可以**获取**该值，但是，该值一旦进行分配之后（如此处所示），就不能再分配给其他属性。

   **注意**：在 Kotlin 以及一般的编程语言中，您通常会遇到以下划线开头的属性名称。这通常表示属性不应直接访问。在本示例中，您可以使用绑定属性访问 `LetterListFragment` 中的视图绑定。不过，您无需在 `LetterListFragment` 之外访问 `_binding` 属性。

3. 如需实现 `onCreate()`，只需调用 `setHasOptionsMenu()` 即可。

   ```
   override fun onCreate(savedInstanceState: Bundle?) {   super.onCreate(savedInstanceState)   setHasOptionsMenu(true)}
   ```

4. 请记住，使用 fragment 时，布局会在 `onCreateView()` 中膨胀。通过膨胀视图、设置 `_binding` 的值并返回根视图，可实现 `onCreateView()`

   ```
   override fun onCreateView(   inflater: LayoutInflater, container: ViewGroup?,   savedInstanceState: Bundle?): View? {   _binding = FragmentLetterListBinding.inflate(inflater, container, false)   val view = binding.root   return view}
   ```

5. 在 `binding` 属性下，为 recycler 视图创建一个属性。

   ```
   private lateinit var recyclerView: RecyclerView
   ```

6. 然后，在 `onViewCreated()` 中设置 `recyclerView` 属性的值，并调用 `chooseLayout()`，就像在 `MainActivity` 中一样。您很快就会将 `chooseLayout()` 方法移至 `LetterListFragment` 中，所以不用担心会出错。

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {   recyclerView = binding.recyclerView   chooseLayout()}
   ```

7. 最后，在 `onDestroyView()` 中，将 `_binding` 属性重置为 `null`，因为相应视图已不存在

   ```
   override fun onDestroyView() {   super.onDestroyView()   _binding = null}
   ```

8. 唯一需要注意的一点是，在使用 fragment 时，`onCreateOptionsMenu()` 方法存在一些细微差别。虽然 `Activity` 类具有名为 `menuInflater` 的全局属性，但 fragment 没有此属性。菜单膨胀器会转而传入 `onCreateOptionsMenu()` 中。另请注意，用于 fragment 的 `onCreateOptionsMenu()` 方法不需要返回语句。按如下所示实现该方法：

   ```
   override fun onCreateOptionsMenu(menu: Menu, inflater: MenuInflater) {   inflater.inflate(R.menu.layout_menu, menu)   val layoutButton = menu.findItem(R.id.action_switch_layout)   setIcon(layoutButton)}
   ```

9. 将 `chooseLayout()`、`setIcon()` 和 `onOptionsItemSelected()` 剩下的代码按原样从 `MainActivity` 中移出。唯一需要注意的区别是，由于与 activity 不同，fragment 不是 [`Context`](https://developer.android.com/reference/android/content/Context)。不能传入 `this`（引用 fragment 对象）作为布局管理器的上下文。不过，fragment 提供了 `context` 属性，您可以改用此属性。其余代码与 `MainActivity` 相同。

   ```
   private fun chooseLayout() {   when (isLinearLayoutManager) {       true -> {           recyclerView.layoutManager = LinearLayoutManager(context)           recyclerView.adapter = LetterAdapter()       }       false -> {           recyclerView.layoutManager = GridLayoutManager(context, 4)           recyclerView.adapter = LetterAdapter()       }   }}private fun setIcon(menuItem: MenuItem?) {   if (menuItem == null)       return   menuItem.icon =       if (isLinearLayoutManager)           ContextCompat.getDrawable(this.requireContext(), R.drawable.ic_grid_layout)       else ContextCompat.getDrawable(this.requireContext(), R.drawable.ic_linear_layout)}override fun onOptionsItemSelected(item: MenuItem): Boolean {   return when (item.itemId) {       R.id.action_switch_layout -> {           isLinearLayoutManager = !isLinearLayoutManager           chooseLayout()           setIcon(item)           return true       }       else -> super.onOptionsItemSelected(item)   }}
   ```

10. 最后，从 `MainActivity` 复制 `isLinearLayoutManager` 属性。将此属性放在 `recyclerView` 属性声明的正下方。

    ```
    private var isLinearLayoutManager = true
    ```

11. 现在，所有功能都已迁移至 `LetterListFragment`，因此所有 `MainActivity` 类都需要膨胀布局，使 fragment 在视图中显示。请直接删除 `MainActivity` 中除 `onCreate()` 以外的所有内容。更改后，`MainActivity` 应仅包含以下内容。

    ```
    override fun onCreate(savedInstanceState: Bundle?) {   super.onCreate(savedInstanceState)   val binding = ActivityMainBinding.inflate(layoutInflater)   setContentView(binding.root)}
    ```



这就是将 `MainActivity` 迁移到 `LettersListFragment` 的过程。迁移 `DetailActivity` 的过程几乎完全相同。请执行以下步骤，将代码迁移到 `WordListFragment`。

1. 将伴生对象从 `DetailActivity` 复制到 `WordListFragment`。确保对 `WordAdapter` 中的 `SEARCH_PREFIX` 的引用已更新为引用 `WordListFragment`。
2. 添加一个 `_binding` 变量，该变量应该可为 null，并且初始值为 `null`。
3. 添加一个名为 binding 的仅供获取变量，等效于 `_binding` 变量。
4. 膨胀 `onCreateView()` 中的布局，同时设置 `_binding` 的值并返回根视图。
5. 在 `onViewCreated()` 中执行其余的所有设置：获取对 recycler 视图的引用，设置其布局管理器和适配器，并添加其项目装饰。您需要从 intent 中获取字母。由于 fragment 没有 `intent` 属性，并且通常不应访问父 activity 的 intent，目前，您需要引用 `activity.intent`（而不是 `DetailActivity` 中的 `intent`）来获取 extra。
6. 在 `onDestroyView` 中，将 `_binding` 重置为 null。
7. 删除 `DetailActivity` 中剩余的代码，只保留 `onCreate()` 方法。



### ⑤将 DetailActivity 转换为 WordListFragment

希望您能享受将 `DetailActivity` 迁移至 `WordListFragment` 的机会。这与将 `MainActivity` 迁移到 `LetterListFragment` 几乎完全相同。如果您在任何时候遇到困难，请参阅下文概述的步骤。

1. 首先，将伴生对象复制到 `WordListFragment`。

   ```
   companion object {   val LETTER = "letter"   val SEARCH_PREFIX = "https://www.google.com/search?q="}
   ```

2. 然后，在 `LetterAdapter` 内用于执行 intent 的 `onClickListener()` 中，您需要更新对 `putExtra()` 的调用，也就是将 `DetailActivity.LETTER` 替换为 `WordListFragment.LETTER`。

   ```
   intent.putExtra(WordListFragment.LETTER, holder.button.text.toString())
   ```

3. 同样，在 `WordAdapter` 中，您需要更新用于导航到相应字词搜索结果的 `onClickListener()`，也就是将 `DetailActivity.SEARCH_PREFIX` 替换为 `WordListFragment.SEARCH_PREFIX`。

   ```
   val queryUrl: Uri = Uri.parse("${WordListFragment.SEARCH_PREFIX}${item}")
   ```

4. 回到 `WordListFragment` 中，添加 `FragmentWordListBinding?` 类型的绑定变量。

   ```
   private var _binding: FragmentWordListBinding? = null
   ```

5. 然后，您可以创建一个仅供获取变量，这样无需使用 `?` 即可引用视图。

   ```
   private val binding get() = _binding!!
   ```

6. 然后膨胀布局，同时分配 `_binding` 变量并返回根视图。请记住，对于 fragment，您需要在 `onCreateView()`（而非 `onCreate()`）中执行此操作。

   ```
   override fun onCreateView(   inflater: LayoutInflater,   container: ViewGroup?,   savedInstanceState: Bundle?): View? {   _binding = FragmentWordListBinding.inflate(inflater, container, false)   return binding.root}
   ```

7. 接下来，您需要实现 `onViewCreated()`。这与在 `DetailActivity` 的 `onCreateView()` 中配置 `recyclerView` 几乎完全相同。不过，由于 fragment 无法直接访问该 intent，因此您需要使用 `activity.intent` 引用它。但是，您必须在 `onCreateView()` 中执行此操作，因为无法保证该 activity 在生命周期的早期就存在。

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {   val recyclerView = binding.recyclerView   recyclerView.layoutManager = LinearLayoutManager(requireContext())   recyclerView.adapter = WordAdapter(activity?.intent?.extras?.getString(LETTER).toString(), requireContext())   recyclerView.addItemDecoration(       DividerItemDecoration(context, DividerItemDecoration.VERTICAL)   )}
   ```

8. 最后，您可以在 `onDestroyView()` 中重置 `_binding` 变量。

   ```
   override fun onDestroyView() {   super.onDestroyView()   _binding = null}
   ```

9. 在所有这些功能移至 WordListFragment 后，您现在可以从 DetailActivity 中删除此代码。剩下的应该就是 onCreate() 方法。

   ```
   override fun onCreate(savedInstanceState: Bundle?) {   super.onCreate(savedInstanceState)   val binding = ActivityDetailBinding.inflate(layoutInflater)   setContentView(binding.root)}
   ```



**移除 DetailActivity**

现在，您已成功将 `DetailActivity` 的功能迁移到 `WordListFragment` 中，无需再使用 `DetailActivity`。您可以直接删除 `DetailActivity.kt` 和 `activity_detail.xml`，还可以对清单稍作更改。

1. 首先，删除 `DetailActivity.kt`

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/dd3b0bcf3ec81c9.png" alt="dd3b0bcf3ec81c9.png" style="zoom: 50%;" />

2. 确保取消选中 **Safe delete**，然后点击 **OK**。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/f2f1ff137b0057a7.png" alt="f2f1ff137b0057a7.png" style="zoom:50%;" />

3. 然后，删除 `activity_detail.xml`。同样，确保取消选中 **Safe delete**。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/6090c1d640433e07.png" alt="6090c1d640433e07.png" style="zoom:50%;" />

4. 最后，由于 `DetailActivity` 不再存在，请从 `AndroidManifest.xml` 中移除以下内容。

   ```
   <activity   android:name=".DetailActivity"   android:parentActivityName=".MainActivity" />
   ```

   

删除 DetailActivity 后，您将得到两个 fragment（LetterListFragment 和  WordListFragment）以及一个 activity (MainActivity)。在下一部分，您将学习 Jetpack  Navigation 组件，还将修改 `activity_main.xml`，使其可以在 fragment 之间显示和导航，而不是托管静态布局。



### ⑥ Jetpack Navigation 组件

Android Jetpack 提供了 Navigation 组件，可帮助您在应用中处理任何简单或复杂的导航实现。Navigation 组件有三个关键部分，可供您在 **Words** 应用中实现导航。

- 导航图：导航图是一种 XML 文件，可以直观地呈现应用内的导航。该文件由若干目的地组成，对应于各个 activity 和 fragment，以及它们之间可通过代码用来从一个目的地导航到另一个目的地的操作。与布局文件一样，Android Studio 提供了一个可视化编辑器，用于向导航图添加目的地和操作。
- `NavHost`：`NavHost` 用于在 activity 内显示导航图中的目的地。当您在 fragment 之间导航时，`NavHost` 中显示的目的地会相应更新。您将在 `MainActivity` 中使用名为 `NavHostFragment` 的内置实现。
- `NavController`：您可以使用 `NavController` 对象控制 `NavHost` 中显示的目的地之间的导航。在使用 intent 时，您必须通过调用 startActivity 导航到新屏幕。借助 Navigation 组件，您可以通过调用 `NavController` 的 `navigate()` 方法来交换显示的 fragment。`NavController` 还可帮您处理常见任务，例如响应系统“向上”按钮可回到之前显示的 fragment。

#### **导航依赖项**

1. 在项目级 `build.gradle` 文件的 **buildscript > ext** 中，在 `material_version` 下，将 `nav_version` 设置为 `2.3.1`。

   ```
   buildscript {    ext {        appcompat_version = "1.2.0"        constraintlayout_version = "2.0.2"        core_ktx_version = "1.3.2"        kotlin_version = "1.3.72"        material_version = "1.2.1"        nav_version = "2.3.1"    }    ...}
   ```

   

2. 在应用级 `build.gradle` 文件中，将以下内容添加到依赖项组中。

   ```
   implementation "androidx.navigation:navigation-fragment-ktx:$nav_version"implementation "androidx.navigation:navigation-ui-ktx:$nav_version"
   ```

   

#### Safe Args 插件

首次在 **Words** 应用中实现导航时，您在两个 activity 之间使用了显式 intent。为了在两个 activity 之间传递数据，您调用了 `putExtra()` 方法，同时传递了所选的字母。

开始在 **Words** 应用中实现 Navigation 组件之前，您还需要添加一个名为 **Safe Args** 的 Gradle 插件；在 fragment 之间传递数据时，该插件可帮助您确保类型安全。

执行以下步骤可将 SafeArgs 集成到您的项目中。

1. 在顶级 `build.gradle` 文件的 **buildscript > dependencies** 中，添加以下类路径。

```
classpath "androidx.navigation:navigation-safe-args-gradle-plugin:$nav_version"
```

1. 在应用级 `build.gradle` 文件中，在顶部的 `plugins` 中添加 `androidx.navigation.safeargs.kotlin`。

```
plugins {    id 'com.android.application'    id 'kotlin-android'    id 'kotlin-kapt'    id 'androidx.navigation.safeargs.kotlin'}
```

1. 在修改 Gradle 文件后，您可能会在顶部看到一个黄色的横幅，要求您同步项目。点击 **Sync Now** 并等待一两分钟的时间，此时 Gradle 会更新项目依赖项，以反映您所做的更改。

![854d44a6f7c4c080.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/854d44a6f7c4c080.png)

同步完成后，您可以继续下一步：添加导航图。



### ⑦使用导航图

现在，您已基本了解 fragment 及其生命周期，接下来可以做些更有趣的事情了。下一步是整合 Navigation 组件。Navigation 组件指的就是用于实现导航的工具集合，尤其是在 fragment 之间。您将使用新的可视化编辑器在 fragment 之间实现导航；这种新的可视化编辑器就是导航图（简称 NavGraph）。

**什么是导航图？**

导航图（简称 NavGraph）是应用导航的虚拟映射。每个屏幕（对您而言，就是每个 fragment）都是可能的导航“目的地”。`NavGraph` 可以用显示各目的地之间关系的 XML 文件来表示。

在后台，它实际上会创建 `NavGraph` 类的新实例。不过，导航图中的目的地由 `FragmentContainerView` 向用户显示。您只需创建一个 XML 文件并指定可能的目的地即可。然后，您可以使用生成的代码在 fragment 之间导航。



#### 在 MainActivity 中使用 FragmentContainerView

由于您的布局现在包含在 `fragment_letter_list.xml` 和 `fragment_word_list.xml` 中，因此您的 `activity_main.xml` 文件不再需要包含应用中第一个屏幕的布局。取而代之的是，您将改变 `MainActivity` 的用途，使其包含一个 `FragmentContainerView`，充当您的 fragment 的 NavHost。从这时开始，应用中的所有导航都将在 `FragmentContainerView` 内进行。

1. 替换 **activity_main.xml** 中 `FrameLayout` 的内容，也就是将 `androidx.recyclerview.widget.RecyclerView` 替换为 `FragmentContainerView`。将 ID 指定为 `nav_host_fragment`，并将其高度和宽度设置为 `match_parent` 以填充整个框架布局。

   将下面的代码：

   ```
       <androidx.recyclerview.widget.RecyclerView        android:id="@+id/recycler_view"        ...        android:padding="16dp" />
   ```

   替换为此代码：

   ```
   <androidx.fragment.app.FragmentContainerView   android:id="@+id/nav_host_fragment"   android:layout_width="match_parent"   android:layout_height="match_parent" />
   ```

2. 在 id 属性下，添加 `name` 属性并将其设置为 `androidx.navigation.fragment.NavHostFragment`。虽然您可以为此属性指定特定的 fragment，但将其设置为 `NavHostFragment` 可让 `FragmentContainerView` 在 fragment 之间导航。

   ```
   android:name="androidx.navigation.fragment.NavHostFragment"
   ```

3. 在 layout_height 和 layout_width 属性下方，添加名为 app:navHost 的属性，并将其设置为 `"true"`。这样一来，fragment 容器就可以与导航层次结构进行交互了。例如，如果您按下系统返回按钮，容器将回到之前显示的 fragment，就像呈现新 activity 时发生的情况一样。

   ```
   app:defaultNavHost="true"
   ```

4. 添加一个名为 `app:navGraph` 的属性，并将其设置为 `"@navigation/nav_graph"`。这将指向用于定义应用的 fragment 如何导航到另一个 fragment 的 XML 文件。目前，Android Studio 会显示未解析的符号错误。您将在下一任务中解决此问题。

   ```
   app:navGraph="@navigation/nav_graph"
   ```

5. 最后，由于您使用应用命名空间添加了两个属性，因此请务必向 `FrameLayout` 添加 xmlns:app 属性。

   ```
   <xmlns:android="http://schemas.android.com/apk/res/android"   xmlns:tools="http://schemas.android.com/tools"   xmlns:app="http://schemas.android.com/apk/res-auto"   android:layout_width="match_parent"   android:layout_height="match_parent"   tools:context=".MainActivity">
   ```

以上就是在 activity_main.xml 中进行的所有更改。接下来，您需要创建 `nav_graph` 文件。



#### 设置导航图

添加导航图文件 (**File > New > Android Resource File**)，然后按照如下所示填写相应字段。

- File name：`nav_graph.xml.`这与您为 `app:navGraph` 属性设置的名称相同。
- Resource type：**Navigation**。然后，**Directory name** 应该会自动更改为“navigation”。系统将会创建一个名为“navigation”的新资源文件夹。

![e26ed91764a5616e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/e26ed91764a5616e.png)

该 XML 文件一旦创建完毕，您就会看到一个新的可视化编辑器。由于您已在 `FragmentContainerView` 的 `navGraph` 属性中引用了 `nav_graph`，因此，如需添加新的目的地，请点击屏幕左上方的新建按钮，为每个 fragment 创建一个目的地（一个用于 `fragment_letter_list`，一个用于 `fragment_word_list`）。

![307d036fce790feb.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/307d036fce790feb.gif)

添加后，这些 fragment 应会出现在屏幕中间的导航图上。您还可以使用左侧的组件树选择特定的目的地。



#### 创建导航操作

如需创建 `letterListFragment` 到 `wordListFragment` 目的地之间的导航操作，请将鼠标悬停在 `letterListFragment` 目的地上，然后从右侧出现的圆圈拖动到 `wordListFragment` 目的地处。

![c9477af5828a83f4.gif](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/c9477af5828a83f4.gif)

现在，您应该看到已经创建了一个箭头来表示两个目的地之间的操作。点击箭头，您可以在“Attributes”窗格中看到此操作的名称为 `action_letterListFragment_to_wordListFragment`，可在代码中引用。



#### 指定 WordListFragment 的参数

使用 intent 在 activity 之间导航时，您指定了“extra”，以便将选定字母传递给 `wordListFragment`。Navigation 还支持在目的地之间传递参数，另外可以用确保类型安全的方式执行此操作。

选择 `wordListFragment` 目的地，然后在“Attributes”窗格的 **Arguments** 下，点击加号按钮以创建一个新参数。

该参数的名称应为 `letter`，类型应为 `String`。这就是您之前添加的 Safe Args 插件的用武之地。将此参数指定为字符串可以确保在代码中执行导航操作时，预计会有一个 `String`。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/b6bc3eaacd14bf50.png" alt="b6bc3eaacd14bf50.png" style="zoom:50%;" />

#### 设置起始目的地

当您的 NavGraph 知道所有需要的目的地时，`FragmentContainerView` 如何知道首先要显示哪个 fragment？在 NavGraph 中，您需要将字母列表设置为起始目的地。

设置起始目的地，方法是选择 `letterListFragment` 并点击 **Assign start destination** 按钮。

![99bb085e39dd7b4a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/99bb085e39dd7b4a.png)

这些就是目前您需要使用 NavGraph 编辑器完成的一切操作。现在，请构建项目。这会根据您的导航图生成一些代码，以便您使用刚创建的导航操作。



#### 执行导航操作

打开 `LetterAdapter`.`kt` 来执行导航操作。这只涉及两个步骤。

1. 删除按钮的 `onClickListener()` 的内容。与之相对，您需要检索刚刚创建的导航操作。将以下内容添加到 `onClickListener()` 中。

```
val action = LetterListFragmentDirections.actionLetterListFragmentToWordListFragment(letter = holder.button.text.toString())
```

您可能无法识别其中一些类和函数的名称，这是因为它们是在您构建项目后自动生成的。这就是您在第一步中添加的 Safe Args 插件的用武之地 - 在 NavGraph 上创建的操作会变为您可以使用的代码。不过，名称应该相当直观。`LetterListFragmentDirections` 表示从 `letterListFragment` 开始的所有可能的导航路径。函数 `actionLetterListFragmentToWordListFragment()`

是导航到 `wordListFragment.` 的特定操作。

对导航操作进行引用后，只需获取对 NavController（一个用于执行导航操作的对象）的引用，并调用 `navigate()`，同时传入相应操作即可。

```
holder.view.findNavController().navigate(action)
```



#### 配置 MainActivity

最后一项设置在 `MainActivity` 中进行。您只需在 `MainActivity` 中完成几项更改，即可让一切正常运行。

1. 创建 `navController` 属性。它将标记为 `lateinit`，因为它会在 `onCreate` 中设置。

   ```
   private lateinit var navController: NavController
   ```

2. 然后，在 `onCreate()` 中调用 `setContentView()` 后，引用 `nav_host_fragment`（这是 `FragmentContainerView` 的 ID），并将其分配给您的 `navController` 属性。

   ```
   val navHostFragment = supportFragmentManager    .findFragmentById(R.id.nav_host_fragment) as NavHostFragmentnavController = navHostFragment.navController
   ```

3. 然后，在 `onCreate()` 中调用 `setupActionBarWithNavController()`，同时传入 `navController`。这样可确保操作栏（应用栏）按钮（例如 `LetterListFragment` 中的菜单选项）可见。

   ```
   setupActionBarWithNavController(navController)
   ```

4. 最后，实现 `onSupportNavigateUp()`。除了在 XML 中将 `defaultNavHost` 设置为 `true`，此方法还支持您处理**向上**按钮。不过，您的 activity 需要提供相应实现。

   ```
   override fun onSupportNavigateUp(): Boolean {   return navController.navigateUp() || super.onSupportNavigateUp()}
   ```

此时，所有组件就已准备就绪，支持用户使用 fragment 进行导航。不过，由于现在使用 fragment 而不是 intent 来执行导航，因此您在 `WordListFragment` 中使用的字母的 intent extra 将不再有效。在下一步中，您将通过更新 `WordListFragment` 来获取 `letter` 参数。

**注意**：由于 `navigateUp()` 函数可能会失败，因此无论其成功与否，都会返回 `Boolean`。不过，仅当 `navigateUp()` 返回 `false` 时，您才需要调用 `super.onSupportNavigateUp()`。这之所以行之有效，是因为 `||` 运算符只要求其中一个条件为 true，因此，如果 `navigateUp()` 返回 `true`，`||` 表达式的右侧永远不会被执行。但是，如果 `navigateUp()` 为 false，系统会调用父类中的实现。这称为[短路求值](https://en.wikipedia.org/wiki/Short-circuit_evaluation)，也是一个不错的编程小技巧。





### ⑧获取 WordListFragment 中的参数

之前，您在 `WordListFragment` 中引用 `activity?.intent` 即可访问 `letter` extra。这种做法虽然行之有效，但并非最佳做法，因为 fragment 可以嵌入其他布局中，而在大型应用中，假定 fragment 属于哪一个 activity 要难得多。此外，使用 `nav_graph` 执行导航且使用安全参数时是没有 intent 的，因此尝试访问 intent extra 根本就行不通。

幸运的是，访问安全参数相当简单，您无需等待 `onViewCreated()` 调用完毕。

1. 在 `WordListFragment` 中，创建一个 `letterId` 属性。您可以将此属性标记为 lateinit，这样您就不必将它设置为可为 null 了。

   ```
   private lateinit var letterId: String
   ```

   

2. 然后替换 `onCreate()`（不是 `onCreateView()` 或 `onViewCreated()`!），并添加以下内容。

   ```
   override fun onCreate(savedInstanceState: Bundle?) {    super.onCreate(savedInstanceState)    arguments?.let {        letterId = it.getString(LETTER).toString()    }}
   ```

   由于 `arguments` 有可能是可选的，请注意您调用了 `let()` 并传入了 lambda。此代码将执行，并假设 `arguments` 不为 null，同时传入 `it` 参数的非 null 参数。不过，如果 `arguments` 为 `null`，该 lambda 不会执行。

   ![96a6a3253cea35b0.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/96a6a3253cea35b0.png)

   虽然这不是实际代码的一部分，但 Android Studio 提供了一条有用的提示，以便您了解 `it` 参数。

   到底什么是 `Bundle`？您可将其看作用于在类之间传递数据的键值对，例如 activity 和 fragment。实际上，当您在此应用的第一个版本中执行 intent 时，调用 `intent?.extras?.getString()` 时使用的就是 bundle。使用 fragment 从参数中获取字符串的方式完全相同。

3. 最后，您可以在设置 recycler 视图的适配器时访问 `letterId`。将 `onViewCreated()` 中的 `activity?.intent?.extras?.getString(LETTER).toString()` 替换为 `letterId`。

   recyclerView.adapter = WordAdapter(letterId, requireContext())

大功告成！花一点时间运行您的应用。现在，您可以在一个 activity 中于两个屏幕之间导航，而不必使用任何 intent。



### ⑨ 更新 fragment 标签

您已成功将两个屏幕转换为使用 fragment。在进行任何更改之前，每个 fragment 的应用栏均具有针对应用栏中每个 activity 的描述性标题。不过，在转换为使用 fragment 之后，详情 activity 中不会再有此标题。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/c385595994ba91b5.png" alt="c385595994ba91b5.png" style="zoom:33%;" />

fragment 具有名为 `"label"` 的属性，您可通过该属性设置父 activity 将在应用栏中使用的标题。

1. 在 `strings.xml` 中的应用名称后面，添加以下常量。

   ```
   <string name="word_list_fragment_label">Words That Start With {letter}</string>
   ```

2. 您可以在导航图中为每个 fragment 设置标签。返回 `nav_graph.xml`，选择组件树中的 `letterListFragment`，然后在“Attributes”窗格中将标签设置为 `app_name` 字符串

   ![4568d78c606999d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/4568d78c606999d.png)

3. 选择 `wordListFragment` 并将标签设置为 `word_list_fragment_label`

![7e7e55ea2dfb65bb.png](https://developer.android.com/codelabs/basic-android-kotlin-training-fragments-navigation-component/img/7e7e55ea2dfb65bb.png)

恭喜您坚持到这里！再次运行应用，您应该能看到所有内容，就像此 Codelab 的开头描述的那样，现在，您的所有导航均托管在单个 activity 中，并且每个屏幕都使用单独的 fragment。



### ⑩小结

- fragment 是可以嵌入到 activity 中且可重复使用的界面片段。
- fragment 的生命周期与 activity 的生命周期不同，前者的视图在 `onViewCreated()`（而非 `onCreateView()`）中设置。
- `FragmentContainerView` 用于在其他 activity 中嵌入 fragment，并可以管理 fragment 之间的导航。

使用 Navigation 组件

- 通过设置 `FragmentContainerView` 的 `navGraph` 属性，您可以在一个 activity 内的多个 fragment 之间导航。
- 您可以使用 `NavGraph` 编辑器添加导航操作，还可以指定不同目的地之间的参数。
- 虽然使用 intent 进行导航需要您传入 extra，但 Navigation 组件使用 SafeArgs 为导航操作自动生成类和方法，从而确保参数实现类型安全。

fragment 的用例。

- 借助 Navigation 组件，许多应用可在单个 activity 中管理其整个布局，且所有导航都在 fragment 之间完成。
- fragment 可实现常见的布局模式，如平板电脑上的主/从布局，或同一 activity 中的多个标签页。



## 5 将数据存储在 ViewModel 中

在之前的 Codelab 中，您已了解了 activity 和 fragment  的生命周期以及与配置更改相关的生命周期问题。想要保存应用数据，有一种选择是保存实例状态，但这种选择有其自身的局限性。在此 Codelab  中，您将了解一种利用 Android Jetpack 库设计应用并在配置更改期间保留应用数据的可靠方式。

[Android Jetpack](https://developer.android.com/jetpack) 库是一系列库的集合，可以让您更轻松地开发出优质的 Android 应用。这些库能帮助您遵循最佳做法、省去编写样板代码的工作并简化复杂任务，以便集中精力编写重要的代码（例如应用逻辑）。

[Android 架构组件](https://developer.android.com/topic/libraries/architecture)是 [Android Jetpack](https://developer.android.com/jetpack) 库的一部分，可帮助您设计具有良好架构的应用。架构组件提供关于应用架构的指南，是推荐采用的最佳做法。

应用架构是一组设计规则。就像房屋的蓝图一样，架构为应用提供了结构。良好的应用架构能让代码在未来几年内始终保持可靠性、灵活性、可伸缩性和可维护性。

在此 Codelab 中，您将学习如何使用 [`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel)（其中一个架构组件）存储应用数据。当框架在配置更改或其他事件期间销毁并重新创建 activity 和 fragment 时，存储的数据不会丢失。

**下载起始代码**

此 Codelab 提供了起始代码，供您使用此 Codelab 中所教的功能对其进行扩展。起始代码可能既包含您在之前的 Codelab 中已熟悉的代码，也包含您不熟悉的代码。这些您尚不熟悉的代码将在后续 Codelab 中进行更详细的介绍。

如果您使用 GitHub 中的起始代码，请注意文件夹名称为 `android-basics-kotlin-unscramble-app-starter`。在 Android Studio 中打开项目时，请选择此文件夹。

**起始代码网址**：https://github.com/google-developer-training/android-basics-kotlin-unscramble-app/tree/starter



**起始代码概览**

1. 在 Android Studio 中打开包含起始代码的项目。
2. 在 Android 设备或模拟器上运行应用。
3. 玩一下游戏，猜几个单词，点按 **Submit** 和 **Skip** 按钮。请注意，点按按钮后会显示下一个单词，并且单词数会增加。
4. 请注意，只有在点按 **Submit** 按钮后，得分才会增加。

**起始代码存在的问题**

您在玩游戏时，可能已经发现了下列错误：

1. 点击 **Submit** 按钮后，应用不会检查玩家的单词。玩家总是会得分。
2. 无法结束游戏。猜完 10 个单词之后，应用也会让您玩下去。
3. 游戏画面显示乱序词、玩家得分和单词数。此时通过旋转设备或模拟器更改屏幕方向，请注意，当前单词、得分和单词数都会丢失，游戏将重新开始。

**应用中的主要问题**

在配置更改期间（例如设备的屏幕方向发生变化时），起始应用不会保存和恢复应用状态和数据。

使用 [`onSaveInstanceState()`](https://developer.android.com/guide/components/activities/activity-lifecycle#save-simple-lightweight-ui-state-using-onsaveinstancestate) 回调可以解决此问题。不过，使用 `onSaveInstanceState()` 方法需要编写额外的代码将状态保存在一个软件包中，并实现相应逻辑来检索该状态。而且，可以存储的数据量极少。

您可以使用本衔接课程中所学的 [Android 架构组件](https://developer.android.com/topic/libraries/architecture)来解决这些问题。



**起始代码演示**

您下载的起始代码已为您预先设计了游戏画面的布局。在本衔接课程中，您只需专心实现游戏逻辑即可。您将使用架构组件来实现推荐的应用架构并解决上述问题。下面简要介绍了一些文件，以帮助您上手。

**game_fragment.xml**

- 在 **Design** 视图中，打开 `res/layout/game_fragment.xml`。
- 此文件包含应用中唯一画面（即游戏画面）的布局。
- 此布局包含一个供玩家输入单词的文本字段，以及用于显示得分和单词数的 `TextViews`。此外，此布局还包含游戏说明和用于玩游戏的按钮（**Submit** 和 **Skip**）。

**main_activity.xml**

此文件定义了只有一个游戏 fragment 的主 activity 布局。

**res/values 文件夹**

此文件夹中是一些您所熟悉的资源文件。

- `colors.xml` 包含应用中使用的主题颜色
- `strings.xml` 包含应用所需的全部字符串
- `themes` 和 `styles` 文件夹包含为应用完成的界面自定义

**MainActivity.kt**

此文件包含默认模板生成的代码，用于将 activity 的内容视图设为 `main_activity.xml.`。

**ListOfWords.kt**

此文件包含游戏中所用单词的列表，以及表示每局游戏最多单词数和玩家每猜对一个单词所得分数的常量。

**警告**：建议不要在代码中对字符串进行硬编码，而应将字符串包含在 `strings.xml` 中，这样更容易进行本地化。不过，在此应用中，为简便起见也为了侧重于使用架构组件，我们对字符串进行了硬编码。

**GameFragment.kt**

这是应用中唯一的 fragment，游戏中的大多数操作都在其中发生：

- 为当前乱序词 (`currentScrambledWord`)、单词数 (`currentWordCount`) 和得分 (`score`) 定义了变量。
- 定义了有权访问 `game_fragment` 视图的名为 `binding` 的绑定对象实例。
- `onCreateView()` 函数使用绑定对象膨胀 `game_fragment` 布局 XML 文件。
- `onViewCreated()` 函数用于设置按钮点击监听器并更新界面。
- `onSubmitWord()` 是 **Submit** 按钮的点击监听器，此函数用于显示下一个乱序词，清空文本字段，并增加得分和单词数（无需确认玩家猜出的单词是否正确）。
- `onSkipWord()` 是 **Skip** 按钮的点击监听器，此函数像 `onSubmitWord()` 一样更新界面，只是不增加得分。
- `getNextScrambledWord()` 是一个辅助函数，用于从单词列表中随机选择一个单词，并打乱单词中的字母。
- `restartGame()` 和 `exitGame()` 函数分别用于重新开始和结束游戏，稍后您会用到这些函数。
- `resetTextField()` 用于清除文本字段内容并重置错误状态。
- `updateNextWordOnScreen()` 函数用于显示新的乱序词。



### ①了解应用架构

架构为您提供了在应用中的类之间分配责任时所应遵循的准则。精心设计的应用架构可以帮助您扩缩应用，并在将来用更多功能对应用进行扩展。此外，它还能简化团队协作。

最普适的[架构原则](https://developer.android.com/jetpack/guide#common-principles)是：分离关注点和通过模型驱动界面。

**分离关注点**

分离关注点设计原则指出，应将应用分为类，每个类有各自的责任。

**通过模型驱动界面**

另一个重要原则是您应该通过模型驱动界面（最好是持久性模型）。模型是负责处理应用数据的组件。它们独立于应用中的 `Views` 和应用组件，因此不受应用的生命周期以及相关的关注点的影响。

Android 架构中主要的类或组件是界面控制器 (activity/fragment)、`ViewModel`、`LiveData` 和 `Room`。这些组件负责处理生命周期的某些复杂情况，并帮助您避免与生命周期相关的问题。后续 Codelab 中将介绍 `LiveData` 和 `Room`。

下图所示为架构的基本组成部分：

### ![53dd5e42f23ffba9.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/53dd5e42f23ffba9.png)

**界面控制器 (activity/fragment)**

activity 和 fragment 是界面控制器。界面控制器通过在屏幕上绘制视图、捕获用户事件以及与用户与之互动的界面相关的所有其他操作来控制界面。应用中的数据或有关该数据的任何决策逻辑都不应放到界面控制器类中。

Android 系统可能会根据某些用户互动情况或因内存不足等系统条件而随时销毁界面控制器。由于这些事件不受您的控制，因此您不应将任何应用数据或状态存储到界面控制器中，而应将有关数据的决策逻辑添加到 `ViewModel` 中。

例如，在 **Unscramble** 应用中，乱序词、得分和单词数显示于 fragment（界面控制器）中，而决策代码（例如确定下一个乱序词）以及得分和单词数的计算则应位于 `ViewModel` 中。

**ViewModel**

[`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 是视图中显示的应用数据的模型。模型是负责处理应用数据的组件，能够让应用遵循架构原则，通过模型驱动界面。

[`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 存储应用相关的数据，这些数据不会在 Android 框架销毁并重新创建 activity 或 fragment 时销毁。在配置更改期间会自动保留 `ViewModel` 对象（不会像销毁 activity 或 fragment 实例一样将其销毁），以便它们存储的数据立即可供下一个 activity 或 fragment 实例使用。

如需在应用中实现 `ViewModel`，请扩展架构组件库中提供的 `ViewModel` 类，并将应用数据存储在该类中。

总结：

| fragment/activity（界面控制器）的责任                        | `ViewModel` 的责任                                           |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| activity 和 fragment 负责将视图和数据绘制到屏幕上并响应用户事件。 | `ViewModel` 负责存储和处理界面需要的所有数据。它绝不应访问视图层次结构（例如视图绑定对象）或存储对 activity 或 fragment 的引用。 |



### ②添加 ViewModel

在此任务中，您将向应用添加 `ViewModel`，用于存储应用数据（乱序词、单词数和得分）。

应用的架构设计如下。`MainActivity` 包含一个 `GameFragment`，该 `GameFragment` 将从 `GameViewModel` 中访问有关游戏的信息。

![2094f3414ddff9b9.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/2094f3414ddff9b9.png)

1. 在 Android Studio 的 **Android** 窗口中，打开 **Gradle Scripts** 文件夹下的文件 `build.gradle(Module:Unscramble.app)`。

2. 为了在应用中使用 `ViewModel`，请验证 `dependencies` 块内是否有 ViewModel 库依赖项。我们已代您完成此步骤。

   ```
   // ViewModelimplementation 'androidx.lifecycle:lifecycle-viewmodel-ktx:2.2.0'
   ```

   请务必使用[最新版本](https://developer.android.com/jetpack/androidx/releases/lifecycle)的库。

3. 新建一个名为 `GameViewModel` 的 Kotlin 类文件。在 **Android** 窗口中，右键点击 **ui.game** 文件夹。依次选择 **New** > **Kotlin File/Class**。

   ![74c85ee631d6524c.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/74c85ee631d6524c.png)

4. 将其命名为 `GameViewModel`，然后从列表中选择 **Class**。

5. 将 `GameViewModel` 更改为由 `ViewModel` 派生的子类。`ViewModel` 是一个抽象类，因此您需要对它进行扩展才能在应用中使用它。请参阅下面的 `GameViewModel` 类定义。

   ```
   class GameViewModel : ViewModel() {}
   ```

#### Ⅰ将 ViewModel 附加到 fragment

为了将 `ViewModel` 与界面控制器（activity/fragment）相关联，请在界面控制器内创建对 `ViewModel` 的引用（对象）。

在此步骤中，您将在相应的界面控制器（即 `GameFragment`）内创建 `GameViewModel` 的对象实例。

1. 在 `GameFragment` 类的顶部，添加一个类型为 `GameViewModel` 的属性。

2. 使用 `by viewModels()` Kotlin 属性委托初始化 `GameViewModel`。在下一个部分，您将对 Kotlin 属性委托作进一步了解。

   ```
   private val viewModel: GameViewModel by viewModels()
   ```

3. 如果 Android Studio 提示，请运行 `import` `androidx.fragment.app.viewModels`。





#### ⅡKotlin 属性委托

在 Kotlin 中，每个可变 (`var`) 属性都具有自动为其生成的默认 getter 和 setter 函数。当您为该属性赋值或读取其值时，系统会调用 setter 和 getter 函数。

只读属性 (`val`) 与可变属性略有不同，默认情况下仅为其生成 getter 函数。当您读取只读属性的值时，系统会调用此 getter 函数。

Kotlin 中的属性委托可以帮助您将 getter-setter 的责任移交给另一个类。

此类（称为“委托类”）提供属性的 getter 和 setter 函数并处理其变更。

delegate 属性使用 `by` 子句和 delegate 类实例进行定义：

```
// Syntax for property delegationvar <property-name> : <property-type> by <delegate-class>()
```

在应用中，如果您如下使用默认的 `GameViewModel` 构造函数初始化视图模型：

```
private val viewModel = GameViewModel()
```

那么，当设备经过配置变更后，应用会丢失 `viewModel` 引用的状态。例如，如果您旋转设备，activity 就会被销毁并重新创建，而您将重新获得初始状态的新视图模型实例。

请改为使用属性委托方法，并将 `viewModel` 对象的责任委托给一个不同的类（名为 `viewModels`）。这意味着当您访问 `viewModel` 对象时，将由 delegate 类 `viewModels` 在内部对其进行处理。delegate 类会在第一次访问时为您创建 `viewModel` 对象并在配置更改时保留其值，然后在收到请求时返回该值。



### ③ 将数据移至 ViewModel

将应用的界面数据与界面控制器（`Activity`/`Fragment` 类）分离可以让您更好地遵循我们前面讨论的单一责任原则。activity 和 fragment 负责将视图和数据绘制到屏幕上，而 `ViewModel` 则负责存储并处理界面所需的所有数据。

在此任务中，您要将数据变量从 `GameFragment` 移至 `GameViewModel` 类。

1. 将数据变量 `score`、`currentWordCount`、`currentScrambledWord` 移至 `GameViewModel` 类。

   ```
   class GameViewModel : ViewModel() {    private var score = 0    private var currentWordCount = 0    private var currentScrambledWord = "test"...
   ```

2. 请注意有关未解析的引用的错误。这是因为这些属性仅对 `ViewModel` 可见，界面控制器无法对其进行访问。接下来，您将修复这些错误。

想要解决此问题，就不能将这些属性的可见性修饰符设为 `public`，不应该让数据可被其他类修改。这种做法存在风险，因为外部类可能会以不符合视图模型中指定的游戏规则的预料外方式对数据做出更改。例如，外部类可能会将 `score` 更改为负值。

在 `ViewModel` 之内，数据应可修改，因此数据应设为 `private` 和 `var`。而在 `ViewModel` 之外，数据应可读取但无法修改，因此数据应作为 `public` 和 `val` 公开。为了实现此行为，Kotlin 提供了称为[后备属性](https://kotlinlang.org/docs/reference/properties.html#backing-properties)的功能。



**后备属性**

使用后备属性，可以从 getter 返回确切对象之外的某些其他内容。

我们已经学过，Kotlin 框架会为每个属性生成 getter 和 setter。

对于 getter 和 setter 方法，您可以替换其中一个方法或同时替换两个方法，并提供您自己的自定义行为。为了实现后备属性，您需要替换 getter 方法以返回只读版本的数据。后备属性示例：

```
// Declare private mutable variable that can only be modified// within the class it is declared.private var _count = 0// Declare another public immutable field and override its getter method.// Return the private property's value in the getter method.// When count is accessed, the get() function is called and// the value of _count is returned.val count: Int   get() = _count
```

举例而言，在您的应用中，您需要应用数据仅对 `ViewModel` 可见：

在 `ViewModel` 类之内：

- `_count` 属性设为 `private` 且可变。因此，只能在 `ViewModel` 类中对其进行访问和修改。惯例是为 `private` 属性添加下划线前缀。

在 `ViewModel` 类之外：

- Kotlin 中的默认可见性修饰符为 `public`，因此 `count` 是公共属性，可从界面控制器等其他类对其进行访问。由于只有 `get()` 方法会被替换，所以此属性不可变且为只读状态。当外部类访问此属性时，它会返回 `_count` 的值且其值无法修改。这可以防止外部类擅自对 `ViewModel` 内的应用数据进行不安全的更改，但允许外部调用方安全地访问该应用数据的值。





**将后备属性添加到 currentScrambledWord**

1. 在 `GameViewModel` 中，更改 `currentScrambledWord` 声明以添加一个后备属性。现在，只能在 `GameViewModel` 中对 `_currentScrambledWord` 进行访问和修改。界面控制器 `GameFragment` 可以使用只读属性 `currentScrambledWord` 读取其值。

   ```
   private var _currentScrambledWord = "test"val currentScrambledWord: String   get() = _currentScrambledWord
   ```

2. 在 `GameFragment` 中，更新 `updateNextWordOnScreen()` 方法以使用只读的 `viewModel` 属性 `currentScrambledWord`。

   ```
   private fun updateNextWordOnScreen() {   binding.textViewUnscrambledWord.text = viewModel.currentScrambledWord}
   ```

3. 在 `GameFragment` 中，删除 `onSubmitWord()` 和 `onSkipWord()` 方法内的代码。稍后您将实现这些方法。现在，您应该能够不出错误地编译代码了。

**警告**：切勿公开 `ViewModel` 中的可变数据字段，请确保无法从其他类修改此数据。`ViewModel` 内的可变数据应始终设为 `private`。



## 6. ViewModel 的生命周期

只要 activity 或 fragment 的范围处于有效状态，框架就会让 [`ViewModel`](https://developer.android.com/reference/androidx/lifecycle/ViewModel.html) 保持有效。即使所有者因配置更改（如屏幕旋转）而被销毁，`ViewModel` 也不会被销毁。所有者的新实例会重新连接到现有 `ViewModel` 实例，如下图所示：

## <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/18e67dc79f89d8a.png" alt="18e67dc79f89d8a.png"  />



### ①了解 ViewModel 生命周期

在 `GameViewModel` 和 `GameFragment` 中添加日志记录，帮助您更好地了解 `ViewModel` 生命周期的情况。

1. 在 `GameViewModel.kt` 中，添加一个带有日志语句的 `init` 块。

   ```
   class GameViewModel : ViewModel() {   init {       Log.d("GameFragment", "GameViewModel created!")   }   ...}
   ```

   Kotlin 提供了初始化式块（也称为 `init` 块），作为对象实例初始化期间所需的初始设置代码的位置。初始化式块带有前缀 `init` 关键字，后跟花括号 `{}`。此代码块将于首次创建和初始化对象实例时运行。

2. 在 `GameViewModel` 类中，替换 [`onCleared()`](https://developer.android.com/reference/androidx/lifecycle/ViewModel#onCleared()) 方法。当关联的 fragment 分离后或 activity 完成后，`ViewModel` 会被销毁。在 `ViewModel` 被销毁前会调用 `onCleared()` 回调。

3. 在 `onCleared()` 内添加日志语句，以跟踪 `GameViewModel` 生命周期。

   ```
   override fun onCleared() {    super.onCleared()    Log.d("GameFragment", "GameViewModel destroyed!")}
   ```

4. 在 `GameFragment` 中的 `onCreateView()` 内，获得对绑定对象的引用后，添加日志语句以记录 fragment 的创建。首次创建 fragment 时以及每次因任何事件（例如配置更改）而重新创建 fragment 时，都会触发 `onCreateView()` 回调。

   ```
   override fun onCreateView(   inflater: LayoutInflater, container: ViewGroup?,   savedInstanceState: Bundle?): View {   binding = GameFragmentBinding.inflate(inflater, container, false)   Log.d("GameFragment", "GameFragment created/re-created!")   return binding.root}
   ```

5. 在 `GameFragment` 中，替换 `onDetach()` 回调方法，相应的 activity 和 fragment 被销毁时会调用该回调方法。

   ```
   override fun onDetach() {    super.onDetach()    Log.d("GameFragment", "GameFragment destroyed!")}
   ```

6. 在 Android Studio 中，运行应用，打开 **Logcat** 窗口并按 `GameFragment` 进行过滤。请注意，创建了 `GameFragment` 和 `GameViewModel`。

   ```
   com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: GameViewModel created!
   ```

7. 在您的设备上或模拟器中启用自动屏幕旋转设置，并更改几次屏幕方向。`GameFragment` 每次都被销毁并重新创建，而 `GameViewModel` 只创建了一次，并不是每次调用都重新创建或销毁。

   ```
   com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: GameViewModel created!com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!
   ```

8. 退出游戏或使用返回箭头退出应用。`GameViewModel` 会被销毁，`onCleared()` 回调会被调用。`GameFragment` 会被销毁。

   ```
   com.example.android.unscramble D/GameFragment: GameViewModel destroyed!com.example.android.unscramble D/GameFragment: GameFragment destroyed!
   ```



## 7. 填充 ViewModel

在此任务中，您将使用辅助方法进一步填充 `GameViewModel` 以获取下一个单词，确认玩家猜出的单词是否正确以增加得分，并检查单词数以结束游戏。

**延迟初始化**

通常，在声明变量时，您会预先为其提供一个初始值。不过，如果您还没准备好赋值，也可以稍后再对其进行初始化。如需在 Kotlin 中对属性进行延迟初始化，请使用关键字 `lateinit`（意思是延迟初始化）。如果您能保证您会在使用前对属性进行初始化，就可以使用 `lateinit` 声明该属性。在对变量进行初始化之前，不会为其分配内存。如果您尝试在初始化变量之前对其进行访问，应用会崩溃。

**获取下一个单词**

在 `GameViewModel` 类中创建具有以下功能的 `getNextWord()` 方法：

- 从 `allWordsList` 中获取一个随机单词并将其赋值给 `currentWord.`。
- 打乱 `currentWord` 中的字母以创建一个乱序词并将其赋值给 `currentScrambledWord`。
- 处理乱序词与理顺词（理清字母顺序的单词）相同的情况。
- 确保不会在游戏期间重复显示同一个单词。

在 `GameViewModel` 类中执行以下步骤：

1. 在 `GameViewModel,` 中，添加一个类型为 `MutableList<String>`、名为 `wordsList` 的新类变量，用于存储游戏中所用单词的列表，以避免重复。

2. 添加名为 `currentWord` 的另一个类变量，用于存储玩家正在尝试理顺的单词。请使用 `lateinit` 关键字，因为您稍后才会初始化此属性。

   ```
   private var wordsList: MutableList<String> = mutableListOf()private lateinit var currentWord: String
   ```

3. 添加一个名为 `getNextWord()` 的新 `private` 方法，该方法不带参数也不返回任何内容。

4. 从 `allWordsList` 中获取一个随机单词并将其赋值给 `currentWord`。

   ```
   private fun getNextWord() {   currentWord = allWordsList.random()}
   ```

5. 在 `getNextWord()` 中，将 `currentWord` 字符串转换为字符数组，并将其赋值给名为 `tempWord` 的新 `val`。为了打乱单词的字母顺序，请使用 Kotlin 方法 [`shuffle()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.collections/shuffle.html) 打乱此数组中的字符。

   ```
   val tempWord = currentWord.toCharArray()tempWord.shuffle()
   ```

6. 有时，打乱的字符顺序与原单词相同。在 shuffle 调用前后添加以下 `while` 循环，以便继续该循环直至乱序词与原单词不同。

   ```
   while (tempWord.toString().equals(currentWord, false)) {    tempWord.shuffle()}
   ```

7. 添加一个 `if-else` 块，用于检查某个单词是否已用过。如果 `wordsList` 包含 `currentWord`，就调用 `getNextWord()`。如果不包含，就使用新打乱字母顺序的单词更新 `_currentScrambledWord` 的值，增加单词数，然后将新单词添加到 `wordsList` 中。

   ```
   if (wordsList.contains(currentWord)) {    getNextWord()} else {    _currentScrambledWord = String(tempWord)    ++currentWordCount    wordsList.add(currentWord)}
   ```

8. 以下是完成后的 `getNextWord()` 方法，供您参考。

   ```
   /** Updates currentWord and currentScrambledWord with the next word.*/private fun getNextWord() {   currentWord = allWordsList.random()   val tempWord = currentWord.toCharArray()   tempWord.shuffle()   while (tempWord.toString().equals(currentWord, false)) {       tempWord.shuffle()   }   if (wordsList.contains(currentWord)) {       getNextWord()   } else {       _currentScrambledWord = String(tempWord)       ++currentWordCount       wordsList.add(currentWord)   }}
   ```



**延迟初始化 currentScrambledWord**

现在，您已创建了 `getNextWord()` 方法，用于获取下一个乱序词。您将在首次初始化 `GameViewModel` 时调用此方法。使用 `init` 块初始化当前单词等类中的 `lateinit` 属性。其结果是，屏幕上显示的第一个单词将是一个乱序词而不是 **test**。

1. 运行应用。请注意，第一个单词始终是“**test**”。

2. 如需在应用启动时显示乱序词，需要调用 `getNextWord()` 方法，该方法会进而更新 `currentScrambledWord`。在 `GameViewModel` 的 `init` 块内，调用 `getNextWord()` 方法。

   ```
   init {    Log.d("GameFragment", "GameViewModel created!")    getNextWord()}
   ```

3. 将 `lateinit` 修饰符添加到 `_currentScrambledWord` 属性上。明确指定数据类型为 `String`，因为此时不会提供初始值。

   ```
   private lateinit var _currentScrambledWord: String
   ```

4. 运行应用。请注意，应用启动时显示的是一个新的乱序词。棒极了！

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/8edd6191a40a57e1.png" alt="8edd6191a40a57e1.png" style="zoom:33%;" />





**添加辅助方法**

接下来，添加一个辅助方法，用于在 `ViewModel` 内处理和修改数据。您在后续任务中将用到此方法。

1. 在 `GameViewModel` 类中，添加名为 `nextWord().` 的另一个方法。从列表中获取下一个单词，如果单词数少于 `MAX_NO_OF_WORDS`，就返回 `true`。

```
/** Returns true if the current word count is less than MAX_NO_OF_WORDS.* Updates the next word.*/fun nextWord(): Boolean {    return if (currentWordCount < MAX_NO_OF_WORDS) {        getNextWord()        true    } else false}
```



## 8. 对话框

在起始代码中，游戏永远不会结束，即使猜完 10 个单词后仍会继续。修改应用，使游戏在用户猜完 10 个单词后结束，并显示包含最终得分的对话框。此外，您还要为用户提供一个用于选择再玩一次还是退出游戏的选项。

![c418686382513213.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/c418686382513213.png)

这是您首次向应用中添加对话框。对话框是提示用户做出决定或输入更多信息的小窗口（画面）。通常，对话框不会填满整个屏幕，而且需要用户执行操作后才能继续。Android 提供不同类型的对话框。在此 Codelab 中，您将学习提醒对话框。



**提醒对话框详解**

![a5ecc09450ae44dc.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/a5ecc09450ae44dc.png)

1. 提醒对话框
2. 标题（可选）
3. 消息
4. 文本按钮



### **①实现最终得分对话框**

使用 Material Design 组件库中的 [`MaterialAlertDialog`](https://material.io/develop/android/components/dialogs)，向应用中添加遵循 Material 准则的对话框。由于对话框与界面相关，因此将由 `GameFragment` 负责创建和显示最终得分对话框。

1. 首先，向 `score` 变量添加一个后备属性。在 `GameViewModel` 中，对 `score` 变量声明做以下更改。

   ```
   private var _score = 0val score: Int   get() = _score
   ```

2. 在 `GameFragment` 中，添加一个名为 `showFinalScoreDialog()` 的私有函数。若要创建 `MaterialAlertDialog`，请使用 `MaterialAlertDialogBuilder` 类逐步构建对话框的各个部分。使用 fragment 的 [`requireContext()`](https://developer.android.com/reference/androidx/fragment/app/Fragment#requireContext()) 方法调用传入内容的 [`MaterialAlertDialogBuilder`](https://developer.android.com/reference/com/google/android/material/dialog/MaterialAlertDialogBuilder) 构造函数。`requireContext()` 方法会返回一个非 null `Context`。

   ```
   /** Creates and shows an AlertDialog with the final score.*/private fun showFinalScoreDialog() {   MaterialAlertDialogBuilder(requireContext())}
   ```

   顾名思义，[`Context`](https://developer.android.com/reference/android/content/Context.html) 表示应用、activity 或 fragment 的上下文或当前状态。它包含有关 activity、fragment 或应用的信息。通常，它用于获取对资源、数据库和其他系统服务的访问权限。在此步骤中，您将传递 fragment 上下文以创建提醒对话框。

   如果 Android Studio 提示，请运行 `import` `com.google.android.material.dialog.MaterialAlertDialogBuilder`。

3. 添加代码以对提醒对话框设置标题，使用 `strings.xml` 中的字符串资源。

   ```
   MaterialAlertDialogBuilder(requireContext())   .setTitle(getString(R.string.congratulations))
   ```

4. 设置消息以显示最终得分，使用您先前添加的只读版本得分变量 (`viewModel.score`)。

   ```
      .setMessage(getString(R.string.you_scored, viewModel.score))
   ```

5. 使用 [`setCancelable()`](https://developer.android.com/reference/android/app/Dialog#setCancelable(boolean)) 方法并传递 `false`，使提醒对话框在用户按下返回键时无法取消。

   ```
       .setCancelable(false)
   ```

6. 使用 `setNegativeButton()` 和 `setPositiveButton()` 方法，添加两个文本按钮 **EXIT** 和 **PLAY AGAIN**。从 lambda 分别调用 `exitGame()` 和 `restartGame()`。

   ```
      .setNegativeButton(getString(R.string.exit)) { _, _ ->        exitGame()    }    .setPositiveButton(getString(R.string.play_again)) { _, _ ->        restartGame()    }
   ```

   您可能不熟悉此语法，但这是 `setNegativeButton(getString(R.string.exit), { _, _ -> exitGame()})` 的简写形式，其中 `setNegativeButton()` 方法接受两个参数：一个 `String` 和一个函数 `DialogInterface.OnClickListener()`，后者可以用一个 lambda 来表示。当传入的最后一个参数是函数时，您可以将 lambda 表达式放在圆括号外。这称为[尾随 lambda 语法](https://kotlinlang.org/docs/reference/lambdas.html#passing-a-lambda-to-the-last-parameter)。这两种代码编写方式（将 lambda 放在圆括号内和圆括号外）均可接受。这一点同样适用于 `setPositiveButton` 函数。

7. 最后，添加 [`show()`](https://developer.android.com/reference/android/app/Dialog#show())，用于创建然后显示提醒对话框。

   ```
     .show()
   ```

   

8. 以下是完整的 `showFinalScoreDialog()` 方法，供您参考。

   ```
   /** Creates and shows an AlertDialog with the final score.*/private fun showFinalScoreDialog() {   MaterialAlertDialogBuilder(requireContext())       .setTitle(getString(R.string.congratulations))       .setMessage(getString(R.string.you_scored, viewModel.score))       .setCancelable(false)       .setNegativeButton(getString(R.string.exit)) { _, _ ->           exitGame()       }       .setPositiveButton(getString(R.string.play_again)) { _, _ ->           restartGame()       }       .show()}
   ```



## 9. 为 Submit 按钮实现 OnClickListener

在此任务中，您将使用 `ViewModel` 和您添加的提醒对话框，实现 **Submit** 按钮点击监听器的游戏逻辑。

**显示乱序词**

1. 在 `GameFragment` 中，删除点按 **Submit** 按钮时调用的 `onSubmitWord()` 内的代码（如果尚未删除）。

2. 添加对 `viewModel.nextWord()` 方法返回值的检查。如为 `true`，表示还有其他单词可用，所以使用 `updateNextWordOnScreen()` 更新屏幕上的乱序词。否则，表示游戏已结束，所以显示包含最终得分的提醒对话框。

   ```
   private fun onSubmitWord() {    if (viewModel.nextWord()) {        updateNextWordOnScreen()    } else {        showFinalScoreDialog()    }}
   ```

3. 运行应用！玩一下游戏，猜几个单词。请注意，您尚未实现 **Skip** 按钮，因此无法跳过单词。

4. 请注意，文本字段不会更新，因此玩家必须手动删除上一个单词。提醒对话框中的最终得分始终为零。您将在后续步骤中修复这些错误。

   | ![a4c660e212ce2c31.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/a4c660e212ce2c31.png) | ![12a42987a0edd2c4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/12a42987a0edd2c4.png) |
   | ------------------------------------------------------------ | ------------------------------------------------------------ |





**添加辅助方法以确认玩家猜出的单词是否正确**

1. 在 `GameViewModel` 中添加一个名为 `increaseScore()` 的新私有方法，该方法不带参数也不返回任何值。将 `score` 变量增加 `SCORE_INCREASE`。

   ```
   private fun increaseScore() {   _score += SCORE_INCREASE}
   ```

2. 在 `GameViewModel` 中，添加一个名为 `isUserWordCorrect()` 的辅助方法，该方法返回 `Boolean` 并接受 `String`（玩家猜出的单词）作为参数。

3. 在 `isUserWordCorrect()` 中，确认玩家猜出的单词是否正确，如果正确就增加得分。这将更新提醒对话框中的最终得分。

   ```
   fun isUserWordCorrect(playerWord: String): Boolean {   if (playerWord.equals(currentWord, true)) {       increaseScore()       return true   }   return false}
   ```



**在文本字段中显示错误**

对于 Material 文本字段，[`TextInputLayout`](https://developer.android.com/reference/com/google/android/material/textfield/TextInputLayout) 具有一项显示错误消息的内置功能。例如，在以下文本字段中，标签的颜色发生了变化，显示了错误图标并显示了错误消息，等等。

![18069f0e6b2fddbc.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/18069f0e6b2fddbc.png)

如需在文本字段中显示错误，可在代码中动态设置错误消息，也可在布局文件中静态设置错误消息。下面显示的是在代码中设置和重置错误的示例：

```
// Set error textpasswordLayout.error = getString(R.string.error)// Clear error textpasswordLayout.error = null
```

您会发现，起始代码中已定义了辅助方法 `setErrorTextField(error: Boolean)` 来帮助您设置和重置文本字段中显示的错误。根据您是否要在文本字段中显示错误，以 `true` 或 `false` 作为输入参数调用此方法。

起始代码中的代码段

```
private fun setErrorTextField(error: Boolean) {   if (error) {       binding.textField.isErrorEnabled = true       binding.textField.error = getString(R.string.try_again)   } else {       binding.textField.isErrorEnabled = false       binding.textInputEditText.text = null   }}
```

在此任务中，您将实现 `onSubmitWord()` 方法。单词提交后，对照原单词进行检查，确认用户猜出的单词是否正确。如果单词正确，就转到下一个单词（如果游戏结束，就显示对话框）。如果单词不正确，就在文本字段中显示错误，同时继续显示当前单词。

1. 在 `GameFragment,` 中的 `onSubmitWord()` 开头，创建一个名为 `playerWord` 的 `val`。通过在 `binding` 变量中从文本字段提取玩家猜出的单词，将此单词存储在该值中。

   ```
   private fun onSubmitWord() {    val playerWord = binding.textInputEditText.text.toString()    ...}
   ```

   

2. 在 `onSubmitWord()` 中的 `playerWord` 声明的下方，确认玩家猜出的单词是否正确。添加 `if` 语句，使用 `isUserWordCorrect()` 方法并传入 `playerWord` 检查玩家猜出的单词。

3. 在 `if` 块内，重置文本字段，调用 `setErrorTextField` 并传入 `false`。

4. 将现有代码移至 `if` 块内。

   ```
   private fun onSubmitWord() {    val playerWord = binding.textInputEditText.text.toString()    if (viewModel.isUserWordCorrect(playerWord)) {        setErrorTextField(false)        if (viewModel.nextWord()) {            updateNextWordOnScreen()        } else {            showFinalScoreDialog()        }    }}
   ```

5. 如果用户猜出的单词不正确，就在文本字段中显示错误消息。将 `else` 块添加到上面的 `if` 块，然后调用 `setErrorTextField()` 并传入 `true`。完成后的 `onSubmitWord()` 方法应如下所示：

   ```
   private fun onSubmitWord() {    val playerWord = binding.textInputEditText.text.toString()    if (viewModel.isUserWordCorrect(playerWord)) {        setErrorTextField(false)        if (viewModel.nextWord()) {            updateNextWordOnScreen()        } else {            showFinalScoreDialog()        }    } else {        setErrorTextField(true)    }}
   ```

6. 运行应用。玩一下游戏，猜几个单词。如果玩家猜出的单词正确，那么点击 **Submit** 按钮时单词会被清除，否则会显示“Try again!”消息。请注意，**Skip** 按钮仍然不起作用。您将在下一个任务中添加此实现。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/a10c7d77aa26b9db.png" alt="a10c7d77aa26b9db.png" style="zoom:33%;" />





## 10. 实现 Skip 按钮

在此任务中，您将添加 `onSkipWord()` 的实现，用于处理点击 **Skip** 按钮的情况。

1. 与 `onSubmitWord()` 类似，在 `nextWord()` 方法中添加一个条件。如为 `true`，就在屏幕上显示单词并重置文本字段。如为 `false`，并且本局游戏中再没有剩下的单词，就显示包含最终得分的提醒对话框。

   ```
   /** Skips the current word without changing the score.*/private fun onSkipWord() {    if (viewModel.nextWord()) {        setErrorTextField(false)        updateNextWordOnScreen()    } else {        showFinalScoreDialog()    }}
   ```

2. 运行应用。玩游戏。请注意，**Skip** 和 **Submit** 按钮运行正常。非常好！



## 11. 验证 ViewModel 能否保留数据

在此任务中，请在 `GameFragment` 中添加日志记录，以便监测配置更改期间应用数据是否在 `ViewModel` 中得以保留。为了访问 `GameFragment` 中的 `currentWordCount`，您需要使用后备属性公开只读版本。

1. 在 `GameViewModel` 中，右键点击变量 `currentWordCount`，然后依次选择 **Refactor** > **Rename...**。为新名称添加下划线前缀 (`_currentWordCount`)。
2. 添加后备字段。

```
private var _currentWordCount = 0val currentWordCount: Int   get() = _currentWordCount
```

1. 在 `GameFragment` 中的 `onCreateView()` 内，在 return 语句上方添加另一个日志，用于输出应用数据，即单词、得分和单词数。

```
Log.d("GameFragment", "Word: ${viewModel.currentScrambledWord} " +       "Score: ${viewModel.score} WordCount: ${viewModel.currentWordCount}")
```

1. 在 Android Studio 中，打开 **Logcat**，按 `GameFragment` 进行过滤。运行应用并玩一下游戏，猜几个单词。更改设备的屏幕方向。fragment（界面控制器）会被销毁并重新创建。查看日志。现在，您可以看到得分和单词数增加！

```
com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: GameViewModel created!com.example.android.unscramble D/GameFragment: Word: oimfnru Score: 0 WordCount: 1com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: Word: ofx Score: 80 WordCount: 5com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: Word: ofx Score: 80 WordCount: 5com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: Word: nvoiil Score: 160 WordCount: 9com.example.android.unscramble D/GameFragment: GameFragment destroyed!com.example.android.unscramble D/GameFragment: GameFragment created/re-created!com.example.android.unscramble D/GameFragment: Word: nvoiil Score: 160 WordCount: 9
```

请注意，屏幕方向更改期间，应用数据在 `ViewModel` 中得以保留。在后续 Codelab 中，您将使用 `LiveData` 和数据绑定更新界面中的得分值和单词数。



## 12. 更新游戏重新开始逻辑

1. 再次运行应用并玩游戏，这次猜完所有单词。在 **Congratulations!** 提醒对话框中，点击 **PLAY AGAIN**。应用不会让您再玩一次，因为单词数现在已达到 `MAX_NO_OF_WORDS` 的值。您需要将单词数重置为 0，才能从头再玩一次游戏。

2. 为了重置应用数据，请在 `GameViewModel` 中添加一个名为 `reinitializeData()` 的方法。将得分和单词数设为 `0`。清空单词列表并调用 `getNextWord()` 方法。

   ```
   /** Re-initializes the game data to restart the game.*/fun reinitializeData() {   _score = 0   _currentWordCount = 0   wordsList.clear()   getNextWord()}
   ```

3. 在 `GameFragment` 中的 `restartGame()` 方法顶部，调用新创建的 `reinitializeData()` 方法。

   ```
   private fun restartGame() {   viewModel.reinitializeData()   setErrorTextField(false)   updateNextWordOnScreen()}
   ```

4. 再次运行应用。玩游戏。到达恭喜对话框时，点击 **Play Again**。现在，您应该能够成功地再玩一次游戏！

最终应用应表现出如下行为：游戏随机显示十个乱序词供玩家理顺。您可以点按 **Skip** 跳过单词，也可以猜出单词后点按 **Submit**。如果您猜对了，得分就会增加。如果猜错了，文本字段中就会显示一个错误状态。每猜一个新单词，单词数也会相应增加。

请注意，屏幕上显示的得分和单词数尚不会更新。不过，相应信息仍会存储在视图模型中，并在设备旋转等配置更改期间得以保留。在后续 Codelab 中，您将更新屏幕上的得分和单词数。

| ![f332979d6f63d0e5.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/f332979d6f63d0e5.png) | ![2803d4855f5d401f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/2803d4855f5d401f.png) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |



猜完 10 个单词后，游戏结束，系统会弹出一个提醒对话框，其中会显示您的最终得分以及用于选择退出游戏还是再玩一次的选项。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel/img/d8e0111f5f160ead.png" alt="d8e0111f5f160ead.png" style="zoom: 33%;" />

祝贺您！您已创建了您的第一个 `ViewModel` 并保存了数据！



## 13. 小结

- Android 应用架构准则建议将具有不同责任的类分离并通过模型驱动界面。
- 界面控制器是基于界面的类，例如 `Activity` 或 `Fragment`。界面控制器应仅包含处理界面和操作系统交互的逻辑；它们不应该是界面中要显示的数据的来源。请将那些数据以及任何相关逻辑都放入 `ViewModel` 中。
- `ViewModel` 类负责存储和管理与界面相关的数据。`ViewModel` 类让数据可在发生屏幕旋转等配置更改后继续留存。
- `ViewModel` 是推荐使用的 Android 架构组件之一。



## 14.将 LiveData 与 ViewModel 配合使用

`LiveData` 类也是 [Android 架构组件](https://developer.android.com/topic/libraries/architecture)的一部分，是一种可观察的数据存储器类。

**下载此 Codelab 的起始代码**

此 Codelab 使用您在上一个 Codelab（[将数据存储在 ViewModel 中](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel)）中构建的 Unscramble 应用作为起始代码。

**起始代码网址**：https://github.com/google-developer-training/android-basics-kotlin-unscramble-app/tree/starter

将上一个 Codelab（[将数据存储在 ViewModel 中](https://developer.android.com/codelabs/basic-android-kotlin-training-viewmodel)）中的解决方案代码添加到上面的起始代码分支中，并将其作为此 Codelab 的起始代码。



### ①什么是 LiveData

[`LiveData`](https://developer.android.com/topic/libraries/architecture/livedata) 是一种具有生命周期感知能力、可观察的数据存储器类。

`LiveData` 的部分特性如下：

- `LiveData` 可存储数据；`LiveData` 是一种可存储任何类型的数据的封装容器。
- `LiveData` 是可观察的，这意味着当 `LiveData` 对象存储的数据发生更改时，观察器会收到通知。
- `LiveData` 具有生命周期感知能力。当您将观察器附加到 `LiveData` 后，观察器就会与 [`LifecycleOwner`](https://developer.android.com/topic/libraries/architecture/lifecycle#lco)（通常是 activity 或 fragment）相关联。`LiveData` 仅更新处于活跃生命周期状态（例如 [`STARTED`](https://developer.android.com/reference/android/arch/lifecycle/Lifecycle.State.html#STARTED) 或 [`RESUMED`](https://developer.android.com/reference/android/arch/lifecycle/Lifecycle.State.html#RESUMED)）的观察器。您可以在[此处](https://developer.android.com/topic/libraries/architecture/livedata.html#work_livedata)详细了解 `LiveData` 和观察。

**起始代码中的界面更新**

在起始代码中，每次需要在界面中显示新的乱序词时，都会显式调用 `updateNextWordOnScreen()` 方法。在游戏初始化期间以及玩家按下 **Submit** 或 **Skip** 按钮时，也会调用此方法。此方法还会从 `onViewCreated()`、`restartGame()`、`onSkipWord()` 和 `onSubmitWord()` 方法中调用。不过，有了 `Livedata` 后，您就不必从多个位置调用此方法来更新界面了。您只需在观察器中调用一次即可。



### ② 向当前乱序词添加 LiveData

在此任务中，您要将 `GameViewModel` 中的当前单词转换为 [`LiveData`](https://developer.android.com/reference/android/arch/lifecycle/LiveData.html)，以此来了解如何使用 `LiveData,` 封装任何数据。在后续任务中，您将向这些 `LiveData` 对象添加观察器并了解如何观察 `LiveData`。

#### MutableLiveData

`MutableLiveData` 是 `LiveData` 的可变版本，也就是说，其中存储的数据的值是可以更改的。

1. 在 `GameViewModel` 中，将变量 `_currentScrambledWord` 的类型更改为 [`MutableLiveData`](https://developer.android.com/reference/androidx/lifecycle/MutableLiveData)`<String>`。`LiveData` 和 `MutableLiveData` 是泛型类，因此需要指定其存储的数据的类型。

2. 将 `_currentScrambledWord` 的变量类型更改为 `val`，因为 `LiveData`/`MutableLiveData` 对象的值将保持不变，且只有该对象中存储的数据会发生更改。

   ```
   private val _currentScrambledWord = MutableLiveData<String>()
   ```

   

3. 将后备字段 `currentScrambledWord` 的类型更改为 `LiveData<String>`，因为它不可变。Android Studio 会显示一些错误，您将在后续步骤中修复这些错误。

   ```
   val currentScrambledWord:LiveDate<String>   get() = _currentScrambledWord
   ```

4. 要访问 `LiveData` 对象中的数据，请使用 `value` 属性。在 `GameViewModel` 中，在 `getNextWord()` 方法内的 `else` 块中，将 **`_currentScrambledWord`** 的引用更改为 **`_currentScrambledWord.value`**。

   ```
   private fun getNextWord() { ...   } else {       _currentScrambledWord.value = String(tempWord)       ...   }}
   ```





### ③将观察器附加到 LiveData 对象

在此任务中，您将在应用组件 `GameFragment` 中设置观察器。您添加的观察器用于观察对应用数据 `currentScrambledWord` 做出的更改。`LiveData` 具有生命周期感知能力，也就是说它仅更新处于活跃生命周期状态的观察器。因此，仅当 `GameFragment` 处于 `STARTED` 或 `RESUMED` 状态时，`GameFragment` 中的观察器才会收到通知。

1. 在 `GameFragment` 中，删除 `updateNextWordOnScreen()` 方法以及对它的所有调用。您不需要此方法，因为您要将一个观察器附加到 `LiveData` 上。

2. 在 `onSubmitWord()` 中，修改以下空 `if-else` 块。完整的方法应如下所示。

   ```
   private fun onSubmitWord() {    val playerWord = binding.textInputEditText.text.toString()    if (viewModel.isUserWordCorrect(playerWord)) {        setErrorTextField(false)        if (!viewModel.nextWord()) {            showFinalScoreDialog()        }    } else {        setErrorTextField(true)    }}
   ```

3. 为 `currentScrambledWord` `LiveData` 附加一个观察器。在 `GameFragment` 中的 `onViewCreated()` 回调末尾，对 `currentScrambledWord` 调用 [`observe()`](https://developer.android.com/reference/androidx/lifecycle/LiveData#observe(androidx.lifecycle.LifecycleOwner, androidx.lifecycle.Observer)) 方法。

   ```
   // Observe the currentScrambledWord LiveData.viewModel.currentScrambledWord.observe()
   ```

   Android Studio 将显示一个关于缺少参数的错误。您将在下一步中修复该错误。

4. 将 `viewLifecycleOwner` 作为第一个参数传递给 `observe()` 方法。`viewLifecycleOwner` 表示 [fragment 的视图](https://developer.android.com/reference/kotlin/androidx/fragment/app/Fragment.html#getView())生命周期。此参数可以帮助 `LiveData` 了解 `GameFragment` 的生命周期，并仅在 `GameFragment` 处于活跃状态（`STARTED` 或 `RESUMED`）时通知观察器。

5. 添加 lambda 作为第二个参数，并以 `newWord` 作为函数参数。`newWord` 将包含新乱序词的值。

   ```
   // Observe the scrambledCharArray LiveData, passing in the LifecycleOwner and the observer.viewModel.currentScrambledWord.observe(viewLifecycleOwner,   { newWord ->   })
   ```

6. 在 lambda 表达式的函数主体中，将 `newWord` 赋值给乱序词文本视图。

   ```
   // Observe the scrambledCharArray LiveData, passing in the LifecycleOwner and the observer.viewModel.currentScrambledWord.observe(viewLifecycleOwner,   { newWord ->       binding.textViewUnscrambledWord.text = newWord   })
   ```

7. 编译并运行应用。游戏应用的运行应该和之前完全一样，但现在乱序词的文本视图会在 `LiveData` 观察器中自动更新，而不是在 `updateNextWordOnScreen()` 方法中更新。



### ④将观察器附加到得分和单词数

与上一个任务一样，在此任务中，您将向应用中的其他数据（得分和单词数）添加 `LiveData`，这样界面便会在游戏期间更新正确的得分和单词数。

#### 第 1 步：使用 LiveData 封装得分和单词数

1. 在 `GameViewModel` 中，将 `_score` 和 `_currentWordCount` 类变量的类型更改为 `val`。

2. 将变量 `_score` 和 `_currentWordCount` 的数据类型更改为 `MutableLiveData`，并将其初始化为 `0`。

3. 将后备字段类型更改为 `LiveData<Int>.`。

   ```
   private val _score = MutableLiveData(0)val score: LiveData<Int>   get() = _scoreprivate val _currentWordCount = MutableLiveData(0)val currentWordCount: LiveData<Int>   get() = _currentWordCount
   ```

4. 在 `GameViewModel` 中的 `reinitializeData()` 方法的开头，将 `_score` 和 `_currentWordCount` 的引用分别更改为 `_score.``value` 和 `_currentWordCount.``value`。

   ```
   fun reinitializeData() {    _score.value = 0    _currentWordCount.value = 0    wordsList.clear()    getNextWord()}
   ```

5. 在 `GameViewModel` 中的 `nextWord()` 方法内，将 `_currentWordCount` 的引用更改为 `_currentWordCount.``value!!`。

   ```
   fun nextWord(): Boolean {    return if (_currentWordCount.value!! < MAX_NO_OF_WORDS) {           getNextWord()           true       } else false   }
   ```

6. 在 `GameViewModel` 中的 `increaseScore()` 和 `getNextWord()` 方法内，将 `_score` 和 `_currentWordCount` 的引用分别更改为 `_score.``value` 和 `_currentWordCount.``value`。Android Studio 会显示错误，因为 `_score` 不再是整数而是 `LiveData`，您将在后续步骤中修复该错误。

7. 使用 [`plus()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/plus.html) Kotlin 函数来增加 `_score` 的值，该函数会以确保 null 安全的形式执行加法。

   ```
   private fun increaseScore() {    _score.value = (_score.value)?.plus(SCORE_INCREASE)}
   ```

8. 同样，使用 [`inc()`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-int/inc.html) Kotlin 函数，以确保 Null 安全的形式将值加一。

9. 在 `GameFragment` 中，使用 `value` 属性访问 `score` 的值。在 `showFinalScoreDialog()` 方法内，将 `viewModel.score` 更改为 `viewModel.score.``value`。





#### 第 2 步：将观察器附加到得分和单词数上

该应用中的得分和单词数目前还不会更新。在此任务中，您将使用 `LiveData` 观察器对它们进行更新。

1. 在 `GameFragment` 中的 `onViewCreated()` 方法内，删除用于更新得分和单词数文本视图的代码。

   移除：

   ```
   binding.score.text = getString(R.string.score, 0)binding.wordCount.text = getString(R.string.word_count, 0, MAX_NO_OF_WORDS)
   ```

2. 在 `GameFragment` 中的 `onViewCreated()` 方法的末尾，为 `score` 附加观察器。将 `viewLifecycleOwner` 作为第一个参数传入观察器，并传入 lambda 表达式作为第二个参数。在 lambda 表达式内，将新得分作为参数传递，并在函数主体内将新得分设为文本视图。

   ```
   viewModel.score.observe(viewLifecycleOwner,   { newScore ->       binding.score.text = getString(R.string.score, newScore)   })
   ```

3. 在 `onViewCreated()` 方法的末尾，附加 `currentWordCount` `LiveData` 的观察器。将 `viewLifecycleOwner` 作为第一个参数传入观察器，并传入 lambda 表达式作为第二个参数。在 lambda 表达式内，将新单词数作为参数传递，并在函数主体中将新单词数连同 `MAX_NO_OF_WORDS` 一起设为文本视图。

   ```
   viewModel.currentWordCount.observe(viewLifecycleOwner,{        newWordCount ->    binding.wordCount.text = getString(R.string.word_count, newWordCount, MAX_NO_OF_WORDS)})
   ```

   在生命周期所有者（即 `GameFragment`）的整个生命周期内，当 `ViewModel` 内的得分和单词数值更改时，就会触发新观察器。

4. 运行应用，亲眼见识一下这种神奇的功能。玩一下游戏，猜几个单词。屏幕上的得分和单词数现在也正确更新了。请注意，这些文本视图并非根据代码中的某些条件而更新。`score` 和 `currentWordCount` 是 `LiveData`，当底层的值发生更改时，会自动调用相应的观察器。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-livedata/img/80e118245bdde6df.png" alt="80e118245bdde6df.png" style="zoom:33%;" />



### ⑤将 LiveData 与数据绑定搭配使用

在前面的任务中，应用会在代码中监听数据更改。同样，应用也可以从布局监听数据更改。借助数据绑定，当可观察的 `LiveData` 值发生更改时，与其绑定的布局中的界面元素也会收到通知，并可在布局中更新界面。

**概念：数据绑定**

在之前的 Codelab 中，您已了解过[视图绑定](https://developer.android.com/topic/libraries/view-binding)，它是一种单向绑定。您可以将视图绑定到代码，但反之则不然。

#### **视图绑定复习：**

视图绑定是一项能让您更轻松地在代码中访问视图的功能。它会为每个 XML 布局文件生成绑定类。绑定类的实例包含对在相应布局中具有 ID 的所有视图的直接引用。例如，Unscramble 应用目前使用了视图绑定，因此可在代码中使用生成的绑定类引用视图。

示例：

```
binding.textViewUnscrambledWord.text = newWordbinding.score.text = getString(R.string.score, newScore)binding.wordCount.text =                  getString(R.string.word_count, newWordCount, MAX_NO_OF_WORDS)
```

使用视图绑定时，您无法在视图（布局文件）中引用应用数据。这一点可以通过[数据绑定](https://developer.android.com/topic/libraries/data-binding)来实现。

#### 数据绑定

数据绑定库也是 [Android Jetpack 库](https://developer.android.com/jetpack)的一部分。数据绑定使用声明性格式将布局中的界面组件绑定到应用中的数据源，此 Codelab 中稍后将对此进行介绍。

简而言之，数据绑定就是将数据（从代码）绑定到视图 + 视图绑定（将视图绑定到代码）

在界面控制器中使用视图绑定的示例

```
binding.textViewUnscrambledWord.text = viewModel.currentScrambledWord
```

在布局文件中使用数据绑定的示例

```
android:text="@{gameViewModel.currentScrambledWord}"
```

上面的示例显示了如何使用数据绑定库直接在布局文件中将应用数据赋值给视图/微件。请注意赋值表达式中 `@{}` 语法的使用。

使用数据绑定的主要优势在于，您可以移除 activity 中的许多界面框架调用，使其维护起来更简单、方便。还可以提高应用性能，并且有助于防止内存泄漏以及避免发生 null 指针异常。

#### 第 1 步：将视图绑定更改为数据绑定

1. 在 `build.gradle(Module)` 文件中的 `buildFeatures` 部分下，启用 `dataBinding` 属性。

   将

   ```
   buildFeatures {   viewBinding = true}
   ```

   替换为

   ```
   buildFeatures {   dataBinding = true}
   ```

   当 Android Studio 提示时，执行 Gradle 同步。

2. 若要在任何 Kotlin 项目中使用数据绑定，应当应用 `kotlin-kapt` 插件。我们已在 `build.gradle(Module)` 文件中代您完成此步骤。

   ```
   plugins {   id 'com.android.application'   id 'kotlin-android'   id 'kotlin-kapt'}
   ```

   上述步骤会为应用中的每个布局 XML 文件自动生成绑定类。如果布局文件名是 `activity_main.xml`，那么自动生成的类将被命名为 `ActivityMainBinding`。

   

#### 第 2 步：将布局文件转换为数据绑定布局

数据绑定布局文件略有不同，以根标记 `<layout>` 开头，后跟可选 `<data>` 元素和 `view` 根元素。此 view 元素就是非绑定布局文件中的根。

1. 打开 `game_fragment.xml`，选择 **code** 标签页。

2. 为了将布局转换为数据绑定布局，请将根元素封装在 `<layout>` 标记中。您还必须将命名空间定义（以 `xmlns:` 开头的属性）移至新的根元素。在根元素上方的 `<layout>` 标记内，添加 `<data></data>` 标记。Android Studio 提供了一种便捷方式来自动执行此操作：右键点击根元素 (`ScrollView`)，然后依次选择 **Show Context Actions** > **Convert to data binding layout**

   ![f356fc45e8fe91b1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-livedata/img/f356fc45e8fe91b1.png)

3. 您的布局应如下所示：

   ```
   <layout xmlns:android="http://schemas.android.com/apk/res/android"   xmlns:app="http://schemas.android.com/apk/res-auto"   xmlns:tools="http://schemas.android.com/tools">   <data>   </data>   <ScrollView       android:layout_width="match_parent"       android:layout_height="match_parent">       <androidx.constraintlayout.widget.ConstraintLayout         ...       </androidx.constraintlayout.widget.ConstraintLayout>   </ScrollView></layout>
   ```

4. 在 `GameFragment` 中的 `onCreateView()` 方法开头，将 `binding` 变量的实例化更改为使用数据绑定。

   将

   ```
   binding = GameFragmentBinding.inflate(inflater, container, false)
   ```

   替换为

   ```
   binding = DataBindingUtil.inflate(inflater, R.layout.game_fragment, container, false)
   ```

5. 编译代码；您应该能够不出任何错误地顺利编译。应用现在使用的是数据绑定，布局中的视图可以访问应用数据。



### ⑥添加数据绑定变量

在此任务中，您将在布局文件中添加属性，以访问 `viewModel` 中的应用数据。您将在代码中初始化布局变量。

1. 在 `game_fragment.xml` 中的 `<data>` 标记内添加名为 `<variable>` 的子标记内，声明一个名为 `gameViewModel`、类型为 `GameViewModel` 的属性。您将使用此属性将 `ViewModel` 中的数据绑定到布局。

   ```
   <data>   <variable       name="gameViewModel"       type="com.example.android.unscramble.ui.game.GameViewModel" /></data>
   ```

   请注意，类型 `gameViewModel` 包含软件包名称。请确保此软件包名称与应用中的软件包名称匹配。

2. 在 `gameViewModel` 声明下的 `<data>` 标记内，添加类型为 `Integer` 的另一个变量，并将其命名为 `maxNoOfWords`。您将使用此变量绑定到 ViewModel 中的变量，以存储每局游戏的单词数。

   ```
   <data>   ...   <variable       name="maxNoOfWords"       type="int" /></data>
   ```

3. 在 `GameFragment` 中的 `onViewCreated()` 方法开头，初始化布局变量 `gameViewModel` 和 `maxNoOfWords`。

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {   super.onViewCreated(view, savedInstanceState)   binding.gameViewModel = viewModel   binding.maxNoOfWords = MAX_NO_OF_WORDS...}
   ```

4. `LiveData` 是生命周期感知型可观察对象，因此您必须将生命周期所有者传递给布局。在 `GameFragment` 中的 `onViewCreated()` 方法内，在绑定变量的初始化下方添加以下代码。

   ```
      // Specify the fragment view as the lifecycle owner of the binding.   // This is used so that the binding can observe LiveData updates   binding.lifecycleOwner = viewLifecycleOwner
   ```

   回想一下，您在实现 `LiveData` 观察器时实现过类似功能。您当时将 `viewLifecycleOwner` 作为一个参数传递给 `LiveData` 观察器。





### ⑦使用绑定表达式

绑定表达式在布局中引用布局属性的特性属性（例如 `android:text`）中编写。布局属性在数据绑定布局文件的顶部通过 `<variable>` 标记进行声明。当任何因变量发生更改时，“数据绑定库”将运行绑定表达式（并因此更新视图）。这项更改检测功能是一项了不起的优化，如果您使用数据绑定库，就可以免费获得这项功能。

#### 绑定表达式的语法

绑定表达式以 `@` 符号开头并用花括号 `{}` 括起来。在以下示例中，`TextView` 文本被设为 `user` 变量的 `firstName` 属性：

示例：

```
<TextView android:layout_width="wrap_content"          android:layout_height="wrap_content"          android:text="@{user.firstName}" />
```

#### 第 1 步：向当前单词添加绑定表达式

在此步骤中，您要将当前单词文本视图绑定到 `ViewModel` 中的 `LiveData` 对象。

1. 在 `game_fragment.xml` 中，将 `text` 属性添加到 `textView_unscrambled_word` 文本视图。使用新的布局变量 `gameViewModel`，并将 `@{gameViewModel.currentScrambledWord}` 赋值给 `text` 属性。

   ```
   <TextView   android:id="@+id/textView_unscrambled_word"   ...   android:text="@{gameViewModel.currentScrambledWord}"   .../>
   ```

2. 在 `GameFragment` 中，移除 `currentScrambledWord` 的 `LiveData` 观察器代码：fragment 中不再需要此观察器代码。布局会直接收到对 `LiveData` 所做更改的更新。

   移除

   ```
   viewModel.currentScrambledWord.observe(viewLifecycleOwner,   { newWord ->       binding.textViewUnscrambledWord.text = newWord   })
   ```

3. 运行应用，此时应用应该像以前一样工作。不过，现在乱序词文本视图使用绑定表达式来更新界面，而非使用 `LiveData` 观察器。



#### 第 2 步：向得分和单词数添加绑定表达式

**数据绑定表达式中的资源**

数据绑定表达式可以使用以下语法引用应用资源。

示例：

```
android:padding="@{@dimen/largePadding}"
```

在上面的示例中，`padding` 属性被赋予 `dimen.xml`资源文件中的值 `largePadding`。

您还可以将布局属性作为资源参数传递。

示例：

```
android:text="@{@string/example_resource(user.lastName)}"strings.xml<string name="example_resource">Last Name: %s</string>
```

在上面的示例中，`example_resource` 是带有 `%s` 占位符的字符串资源。您将 `user.lastName` 作为资源参数传入绑定表达式，其中 `user` 是布局变量。

在此步骤中，您将向得分和单词数文本视图添加绑定表达式，传入资源参数。此步骤与上面针对 `textView_unscrambled_word` 执行的操作类似。

1. 在 `game_fragment.xml` 中，使用以下绑定表达式更新 `word_count` 文本视图的 `text` 属性。使用 `word_count` 字符串资源并传入 `gameViewModel.currentWordCount` 和 `maxNoOfWords` 作为资源参数。

   ```
   <TextView   android:id="@+id/word_count"   ...   android:text="@{@string/word_count(gameViewModel.currentWordCount, maxNoOfWords)}"   .../>
   ```

2. 使用以下绑定表达式更新 `score` 文本视图的 `text` 属性。使用 `score` 字符串资源并传入 `gameViewModel.score` 作为资源参数。

   ```
   <TextView   android:id="@+id/score"   ...   android:text="@{@string/score(gameViewModel.score)}"   ... />
   ```

3. 从 `GameFragment` 中移除 `LiveData` 观察器。您不再需要这些观察器，绑定表达式会在相应的 `LiveData` 更改时更新界面。

   移除：

   ```
   viewModel.score.observe(viewLifecycleOwner,   { newScore ->       binding.score.text = getString(R.string.score, newScore)   })viewModel.currentWordCount.observe(viewLifecycleOwner,   { newWordCount ->       binding.wordCount.text =           getString(R.string.word_count, newWordCount, MAX_NO_OF_WORDS)   })
   ```

4. 运行应用并玩一下游戏，猜几个单词。现在，您的代码使用 `LiveData` 和绑定表达式来更新界面。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-livedata/img/7880e60dc0a6f95c.png" alt="7880e60dc0a6f95c.png" style="zoom: 50%;" />           <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-livedata/img/9ef2fdf21ffa5c99.png" alt="9ef2fdf21ffa5c99.png" style="zoom: 50%;" />

恭喜！您已经学习了如何将 `LiveData` 与 `LiveData` 观察器搭配使用以及如何将 `LiveData` 与绑定表达式搭配使用。



### ⑧在启用 Talkback 的情况下测试 Unscramble 应用

正如您在本课程中所了解的，您需要构建可供尽可能多的用户访问的应用。有些用户可能会使用 [TalkBack](https://support.google.com/accessibility/android/answer/6283677) 访问您的应用并在其中导航。TalkBack 是 Android 设备随附的 Google 屏幕阅读器。TalkBack 会为您提供语音反馈，这样即使您不看屏幕也能轻松使用设备。

在启用 Talkback 的情况下，确保玩家可以玩游戏。

1. 按照这些[说明](https://support.google.com/accessibility/android/answer/6007100)在您的设备上启用 TalkBack。
2. 返回 Unscramble 应用。
3. 按照这些[说明](https://developer.android.com/guide/topics/ui/accessibility/testing#explore_your_app_with_talkback)，通过 TalkBack 探索您的应用。向右滑动可按顺序浏览屏幕元素，向左滑动即可按相反顺序浏览。点按任意位置两次即可选择。确认您可以通过滑动手势访问应用的所有元素。
4. 确保 TalkBack 用户能够导航到屏幕上的每一项。
5. 请注意，Talkback 会尝试将乱序词作为一个单词读出来。这可能会让玩家感到困惑，因为乱序词并不是真正的单词。
6. 让 Talkback 读出乱序词的一个个字符会带来更好的用户体验。在 `GameViewModel` 中，将乱序词 `String` 转换为 `Spannable` 字符串。Spannable 字符串是附加了一些额外信息的字符串。在本例中，我们需要将该字符串与类型为 [`TYPE_VERBATIM`](https://developer.android.com/reference/android/text/style/TtsSpan#TYPE_VERBATIM)`,` 的 [`TtsSpan`](https://developer.android.com/reference/android/text/style/TtsSpan) 相关联，让文字转语音引擎逐个字符地读出乱序词。
7. 在 `GameViewModel,` 中，使用以下代码修改 `currentScrambledWord` 变量的声明方式：

```
val currentScrambledWord: LiveData<Spannable> = Transformations.map(_currentScrambledWord) {    if (it == null) {        SpannableString("")    } else {        val scrambledWord = it.toString()        val spannable: Spannable = SpannableString(scrambledWord)        spannable.setSpan(            TtsSpan.VerbatimBuilder(scrambledWord).build(),            0,            scrambledWord.length,            Spannable.SPAN_INCLUSIVE_INCLUSIVE        )        spannable    }}
```

此变量现在是一个 `LiveData<Spannable>` 而不是 `LiveData<String>`。您不必费心了解其工作原理的所有细节，只需要知道，该实现使用 `LiveData` 转换将当前乱序词 `String` 转换为可由无障碍服务进行相应处理的 Spannable 字符串。在下一个 Codelab 中，您将详细了解 `LiveData` 转换，这种转换能让您根据相应 `LiveData` 的值返回不同的 `LiveData` 实例。

1. 运行 Unscramble 应用，使用 Talkback 探索该应用。TalkBack 现在应该会读出乱序词的一个个字符。

如需详细了解如何让您的应用使用起来更没有障碍，请参阅这些[准则](https://developer.android.com/guide/topics/ui/accessibility/principles)。

**注意**：您的设备上随附的无障碍服务可能因设备制造商而有所不同，因此您可能会遇到不同的行为。如果没有读出乱序词的一个个字符，请尝试在 Android Studio 中的模拟器上运行应用。您需要在模拟器上安装 [Android 无障碍套件应用](https://play.google.com/store/apps/details?id=com.google.android.marvin.talkback)才能启用 Talkback。



### ⑨ 删除未使用的代码

最好删除解决方案代码中无用、未使用或不需要的代码。这样做既方便维护代码，又能让新的团队成员更轻松地进一步理解代码。

1. 在 `GameFragment` 中，删除 `getNextScrambledWord()` 和 `onDetach()` 方法。
2. 在 `GameViewModel` 中，删除 `onCleared()` 方法。
3. 删除源文件顶部的任何未使用的导入。这些导入显示为灰色。

您不再需要日志语句，如果愿意，您可将其从代码中删除。

1. [可选] 删除您在上一个 Codelab 中为了了解 `ViewModel` 生命周期而在源文件（`GameFragment.kt` 和 `GameViewModel.kt`）中添加的 `Log` 语句。



### ⑩小结

- `LiveData` 可存储数据；`LiveData` 是一种可用于任何数据的封装容器。
- `LiveData` 是可观察的，这意味着当 `LiveData` 对象存储的数据发生更改时，观察器会收到通知。
- `LiveData` 具有生命周期感知能力。当您将观察器附加到 `LiveData` 后，观察器就会与 [`LifecycleOwner`](https://developer.android.com/topic/libraries/architecture/lifecycle#lco)（通常是 activity 或 fragment）相关联。LiveData 仅更新处于活跃生命周期状态（例如 [`STARTED`](https://developer.android.com/reference/android/arch/lifecycle/Lifecycle.State.html#STARTED) 或 [`RESUMED`](https://developer.android.com/reference/android/arch/lifecycle/Lifecycle.State.html#RESUMED)）的观察器。您可以在[此处](https://developer.android.com/topic/libraries/architecture/livedata.html#work_livedata)详细了解 `LiveData` 和观察。
- 应用可以使用数据绑定和绑定表达式，从布局监听 LiveData 更改。
- 绑定表达式在布局中引用布局属性的特性属性（例如 `android:text`）中编写。



##  15.Fragment 之间的共享 ViewModel

**起始代码网址**：https://github.com/google-developer-training/android-basics-kotlin-cupcake-app/tree/starter

下面是项目中重要文件的演示。

**MainActivity：**

`MainActivity` 的代码与默认生成的代码类似，可将 activity 的内容视图设为 `activity_main.xml`。此代码使用参数化构造函数 `AppCompatActivity(@LayoutRes int contentLayoutId)`，它接受一个布局，该布局将作为 `super.onCreate(savedInstanceState)` 的一部分膨胀。

`MainActivity` 类中的代码

```
class MainActivity : AppCompatActivity(R.layout.activity_main)
```

与使用默认 `AppCompatActivity` 构造函数的以下代码相同：

```
class MainActivity : AppCompatActivity() {

   override fun onCreate(savedInstanceState: Bundle?) {
       super.onCreate(savedInstanceState)
       setContentView(R.layout.main_activity)
   }
}
```

**布局（res/layout 文件夹）：**

`layout` 资源文件夹包含 activity 和 fragment 布局文件。这些是简单的布局文件，并且您在之前的 Codelab 中已熟悉 XML。

- `fragment_start.xml` 是应用中显示的第一个屏幕。它包含一张纸杯蛋糕图片和三个按钮，这三个按钮用于选择要订购的纸杯蛋糕数量：一个纸杯蛋糕、六个纸杯蛋糕和十二个纸杯蛋糕。
- `fragment_flavor.xml` 将纸杯蛋糕口味的列表显示为单选按钮选项，还显示了一个 **Next** 按钮。
- `fragment_pickup.xml` 提供了一个用于选择取货日期的选项，还有一个用于转到摘要屏幕的 **Next** 按钮。
- `fragment_summary.xml` 显示了订单详情的摘要（如数量和口味），还有一个用于将订单发送到另一个应用的按钮。

**Fragment 类：**

- `StartFragment.kt` 是应用中显示的第一个屏幕。这个类包含视图绑定代码和三个按钮的点击处理程序。
- `FlavorFragment.kt`、`PickupFragment.kt` 和 `SummaryFragment.kt` 类主要包含样板代码以及 **Next** 或 **Send Order to Another App** 按钮的点击处理程序，点击这些按钮会显示消息框消息。

**资源（res 文件夹）：**

- `drawable` 文件夹包含第一个屏幕的纸杯蛋糕资源，以及启动器图标文件。
- `navigation/nav_graph.xml` 包含四个 fragment 目的地（`startFragment`、`flavorFragment`、`pickupFragment` 和 `summaryFragment`），但不包含操作，您稍后将在此 Codelab 中定义操作。
- `values` 文件夹包含用于自定义应用主题的颜色、尺寸、字符串、样式和主题。您应该在之前的 Codelab 中已熟悉这些资源类型。



### ①完成导航图

#### 连接导航图中的目的地

1. 在 Android Studio 的 **Project** 窗口中，依次打开 **res > navigation > nav_graph.xml** 文件。切换到 **Design** 标签页（如果尚未选择该标签页）。

   ![28c2c94eb97e2f0.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/28c2c94eb97e2f0.png)

2. 此时将打开 **Navigation Editor**，以直观呈现应用中的导航图。您应该会看到应用中已存在的四个 fragment。

   ![fdce89b318218ea6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/fdce89b318218ea6.png)

   **注意**：如果目的地 fragment 在 Android Studio 中的布局不同，请点击并拖动目的地，以类似于上面屏幕截图的方式重新排列。这样更方便您稍后在此 Codelab 中配置导航操作。

3. 连接导航图中的 fragment 目的地。创建从 `startFragment` 到 `flavorFragment` 的操作，从 `flavorFragment` 到 `pickupFragment` 的连接，以及从 `pickupFragment` 到 `summaryFragment` 的连接。如果您需要更详细的说明，请按照接下来的几个步骤操作。

4. 将光标悬停在 **startFragment** 上，直到您看到该 fragment 周围的灰色边框，以及出现在该 fragment 右侧边缘中心的灰色圆圈。点击该圆圈并将其拖动到 **flavorFragment**，然后松开鼠标。

   ![d014c1b710c1088d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/d014c1b710c1088d.png)

5. 这两个 fragment 之间的箭头指示连接成功，这表示您将能够从 **startFragment** 导航到 **flavorFragment**。这称为导航操作，您在之前的 Codelab 中已经学过。

6. 同样，添加从 **flavorFragment** 到 **pickupFragment** 以及从 **pickupFragment** 到 **summaryFragment** 的导航操作。当您创建完导航操作后，完成的导航图应如下所示。

7. 您创建的三项新操作也应该反映在 **Component Tree** 窗格中。

   ![e4ee54469f5ff1a4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/e4ee54469f5ff1a4.png)

8. 定义导航图时，您还需要指定起始目的地。目前，您可以看到 startFragment 旁边有一个小房子图标。

   这指示 **startFragment** 将是要在 `NavHost` 中显示的第一个 fragment。保留此设置作为应用的预期行为。为了方便您日后参考，您可以随时更改起始目的地，方法是右键点击一个 fragment，然后选择菜单选项 **Set as Start Destination**。

   

#### 从起始 fragment 导航到口味 fragment

接下来，您将添加相应的代码，以通过点按第一个 fragment 中的按钮从 **startFragment** 导航到 **flavorFragment**，而不是显示 `Toast` 消息。下面是起始 fragment 布局的参考。您将在后续任务中将纸杯蛋糕的数量传递给口味 fragment。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/867d8e4c72078f76.png" alt="867d8e4c72078f76.png" style="zoom:33%;" />

1. 在 **Project** 窗口中，依次打开 **app > java > com.example.cupcake > StartFragment** Kotlin 文件。

2. 在 `onViewCreated()` 方法中，请注意，在三个按钮上设置了点击监听器。点按每个按钮时，系统会调用 `orderCupcake()` 方法，并将纸杯蛋糕的数量（1 个、6 个或 12 个纸杯蛋糕）作为其参数。

   **参考代码**：

   ```
   orderOneCupcake.setOnClickListener { orderCupcake(1) }
   orderSixCupcakes.setOnClickListener { orderCupcake(6) }
   orderTwelveCupcakes.setOnClickListener { orderCupcake(12) }
   ```

3. 在 `orderCupcake()` 方法中，将用于显示消息框消息的代码替换为用于导航到口味 fragment 的代码。使用 `findNavController()` 方法获取 `NavController` 并对其调用 `navigate()`，且传入操作 ID `R.id.action_startFragment_to_flavorFragment`。确保此操作 ID 与 `nav_graph.xml.` 中声明的操作匹配。

   将以下代码

   ```
   fun orderCupcake(quantity: Int) {
       Toast.makeText(activity, "Ordered $quantity cupcake(s)", Toast.LENGTH_SHORT).show()
   }
   ```

   替换为下面的代码：

   ```
   fun orderCupcake(quantity: Int) {
      findNavController().navigate(R.id.action_startFragment_to_flavorFragment)
   }
   ```

4. 添加导入代码 `import` `androidx.navigation.fragment.findNavController`，或者您也可以从 Android Studio 提供的选项中进行选择。

   ![2a087f53a77765a6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/2a087f53a77765a6.png)

#### 向口味 fragment 和取货 fragment 添加导航

与前面的任务类似，在此任务中，您将向其他 fragment（即口味 fragment 和取货 fragment）添加导航。

![3b351067bf4926b7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/3b351067bf4926b7.png)

1. 依次打开 **app > java > com.example.cupcake > FlavorFragment.kt**。请注意，在 **Next** 按钮点击监听器中调用的方法是 `goToNextScreen()` 方法。

2. 在 `FlavorFragment.kt` 中的 `goToNextScreen()` 方法内，替换用于显示消息框的代码以导航到取货 fragment。使用操作 ID `R.id.action_flavorFragment_to_pickupFragmen`，并确保此 ID 与 `nav_graph.xml.` 中声明的操作匹配。

   ```
   fun goToNextScreen() {
       findNavController().navigate(R.id.action_flavorFragment_to_pickupFragment)
   }
   ```

   记得添加 `import androidx.navigation.fragment.findNavController` 代码以导入相应的类。

3. 同样，在 `PickupFragment.kt` 中的 `goToNextScreen()` 方法内，替换现有代码以导航到摘要 fragment。

4. 运行应用。确保使用按钮能够在屏幕之间导航。每个 fragment 中显示的信息可能不完整，但不必担心，您将在接下来的步骤中以正确的数据填充这些 fragment。



#### 更新应用栏中的标题

当您在应用中导航时，请注意应用栏中的标题。它始终显示为 **Cupcake**。

如果能够根据当前 fragment 的功能来提供更相关的标题，那么就会带来更好的用户体验。

使用 `NavController` 为每个 fragment 更改应用栏（又称为操作栏）中的标题，并显示 **Up** (←) 按钮。

![b7657cdc50cfeab0.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/b7657cdc50cfeab0.png)

1. 在 `MainActivity.kt` 中，替换 `onCreate()` 方法以设置导航控制器。从 `NavHostFragment` 获取 `NavController` 的实例。

2. 对 `setupActionBarWithNavController(navController)` 进行调用，并传入 `NavController` 的实例。这会有以下作用：根据目的地的标签，在应用栏中显示标题；只要您不在顶级目的地，就会显示 **Up** 按钮。

   ```
   class MainActivity : AppCompatActivity(R.layout.activity_main) {
   
       override fun onCreate(savedInstanceState: Bundle?) {
           super.onCreate(savedInstanceState)
   
           val navHostFragment = supportFragmentManager
                   .findFragmentById(R.id.nav_host_fragment) as NavHostFragment
           val navController = navHostFragment.navController
   
           setupActionBarWithNavController(navController)
       }
   }
   ```

3. 当 Android Studio 提示时，添加必要的导入代码。

   ```
   import android.os.Bundle
   import androidx.navigation.fragment.NavHostFragment
   import androidx.navigation.ui.setupActionBarWithNavController
   ```

4. 为每个 fragment 设置应用栏标题。打开 `navigataion/nav_graph.xml` 并切换到 **Code** 标签页。

5. 在 `nav_graph.xml` 中，修改每个 fragment 目的地的 `android:label` 属性。使用起始应用中已声明的以下字符串资源。

   对于起始 fragment，使用 `@string/app_name`，值为 `Cupcake`。

   对于口味 fragment，使用 `@string/choose_flavor`，值为 `Choose Flavor`。

   对于取货 fragment，使用 `@string/choose_pickup_date`，值为 `Choose Pickup Date`。

   对于摘要 fragment，使用 `@string/order_summary`，值为 `Order Summary`。

   ```
   <navigation ...>
       <fragment
           android:id="@+id/startFragment"
           ...
           android:label="@string/app_name" ... >
           <action ... />
       </fragment>
       <fragment
           android:id="@+id/flavorFragment"
           ...
           android:label="@string/choose_flavor" ... >
           <action ... />
       </fragment>
       <fragment
           android:id="@+id/pickupFragment"
           ...
           android:label="@string/choose_pickup_date" ... >
           <action ... />
       </fragment>
       <fragment
           android:id="@+id/summaryFragment"
           ...
           android:label="@string/order_summary" ... />
   </navigation>
   ```

6. 运行应用。请注意，当您导航到每个 fragment 目的地时，应用栏中的标题会发生变化。另请注意，应用栏中现在显示了 **Up** 按钮（箭头 ←）。如果您点按该按钮，它不起任何作用。您将在下一个 Codelab 中实现 **Up** 按钮行为。

   ![dbd4108d6fdc637a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/dbd4108d6fdc637a.png)

### ②创建共享 ViewModel

让我们继续在每个 fragment 中填充正确的数据。您将使用共享 `ViewModel` 将应用的数据保存在单个 `ViewModel` 中。应用中的多个 fragment 将根据其 activity 作用域访问共享 `ViewModel`。

在大多数正式版应用中，在 fragment 之间共享数据是常见的用例。例如，在此 Codelab 中的最终版 **Cupcake** 应用中（请注意下面的屏幕截图），用户在第一个屏幕中选择纸杯蛋糕的数量，在第二个屏幕中，系统根据纸杯蛋糕的数量计算并显示价格。同样，口味和取货日期等其他应用数据也用在摘要屏幕中。

![3b6a68cab0b9ee2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/3b6a68cab0b9ee2.png)

通过查看应用功能，您可以推断，将此订单信息存储在单个 `ViewModel` 中会很有用，该视图模型可以在此 activity 的 fragment 之间共享。回想一下，[`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 是 [Android 架构组件](https://developer.android.com/topic/libraries/architecture)的一部分。保存在 `ViewModel` 中的应用数据在配置更改期间会保留。如需将 `ViewModel` 添加到应用，您可以创建一个从 [`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 类扩展的新类。

#### **创建 OrderViewModel**

在此任务中，您将为 **Cupcake** 应用创建一个名为 `OrderViewModel` 的共享 `ViewModel`。您还会将应用数据添加为 `ViewModel` 内的属性，并添加用于更新和修改数据的方法。下面是该类的属性：

- 订购数量 (`Integer`)
- 纸杯蛋糕口味 (`String`)
- 取货日期 (`String`)
- 价格 (`Double`)

**遵循 [`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 最佳做法**

在 `ViewModel` 中，建议的做法是不将视图模型数据公开为 `public` 变量。否则，应用数据可能会被外部类以意想不到的方式修改，并造成应用没有预料到要处理的极端情况。应将这些可变属性设为 `private`，实现后备属性，并在需要时公开每个属性的 `public` 不可变版本。惯例是在 `private` 可变属性的名称前面加上下划线 (`_`) 作为前缀。

下面是用于更新上述属性的方法，具体取决于用户的选择：

- `setQuantity(numberCupcakes: Int)`
- `setFlavor(desiredFlavor: String)`
- `setDate(pickupDate: String)`

您不需要使用 setter 方法来设置价格，因为您将使用其他属性在 `OrderViewModel` 中计算价格。下面的步骤为您演示了如何实现共享 `ViewModel`。

您将在项目中创建一个名为 `model` 的新软件包，并添加 `OrderViewModel` 类。这样会将视图模型代码与界面代码的其余部分（fragment 和 activity）分离开来。根据功能将代码分离到软件包中是一种编码最佳做法。

1. 在 Android Studio 的 **Project** 窗口中，右键点击 **com.example.cupcake**，然后依次选择“New”>“Package”。

2. 此时将打开 **New Package** 对话框，请将软件包命名为 `com.example.cupcake.model`。

   ![d958ee5f3d2aef5a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/d958ee5f3d2aef5a.png)

3. 在 `model` 软件包下创建 `OrderViewModel` Kotlin 类。在 **Project** 窗口中，右键点击 `model` 软件包，然后依次选择 **New > Kotlin File/Class**。在新对话框中，提供文件名 `OrderViewModel`。

   ![fc68c1d3861f1cca.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/fc68c1d3861f1cca.png)

4. 在 `OrderViewModel.kt` 中，更改类签名以从 `ViewModel` 扩展。

   ```
   import androidx.lifecycle.ViewModel
   
   class OrderViewModel : ViewModel() {
   
   }
   ```

5. 在 `OrderViewModel` 类内，将上述属性添加为 `private` `val`。

6. 将属性类型更改为 `LiveData` 并向属性添加后备字段，这样这些属性就可观察，当视图模型中的源数据发生变化时，界面就会更新。

   ```
   private val _quantity = MutableLiveData<Int>(0)
   val quantity: LiveData<Int> = _quantity
   
   private val _flavor = MutableLiveData<String>("")
   val flavor: LiveData<String> = _flavor
   
   private val _date = MutableLiveData<String>("")
   val date: LiveData<String> = _date
   
   private val _price = MutableLiveData<Double>(0.0)
   val price: LiveData<Double> = _price
   ```

   您需要导入以下类：

   ```
   import androidx.lifecycle.LiveData
   import androidx.lifecycle.MutableLiveData
   ```

7. 在 `OrderViewModel` 类中，添加上述方法。在方法内，分配传入可变属性的参数。

8. 由于这些 setter 方法需要从视图模型外部进行调用，因此请将其保留为 `public` 方法（这意味着，在 `fun` 关键字之前不需要 `private` 或其他可见性修饰符）。Kotlin 中的默认可见性修饰符为 `public`。

   ```
   fun setQuantity(numberCupcakes: Int) {    _quantity.value = numberCupcakes}fun setFlavor(desiredFlavor: String) {    _flavor.value = desiredFlavor}fun setDate(pickupDate: String) {    _date.value = pickupDate}
   ```

9. 构建并运行您的应用，以确保没有编译错误。界面中应该还没有明显的变化。

   非常棒！现在，您已经有了视图模型的起始代码。随着您在应用中构建出更多功能并意识到类中需要更多属性和方法，您会逐渐向此类添加更多代码。

   如果您看到类名称、属性名称或方法名称在 Android Studio 中显示为灰色字体，这并不奇怪。这意味着，类、属性或方法目前没有被使用，但它们将会被使用！这是接下来要讲的内容。



### ③使用 ViewModel 来更新界面

在此任务中，您将使用创建的共享视图模型更新应用的界面。实现共享视图模型的主要区别在于我们从界面控制器访问它的方式。您将使用 activity 实例而不是 fragment 实例，您将在接下来几部分中看到如何执行此操作。

这意味着，视图模型可以在 fragment 之间共享。每个 fragment 都可以访问视图模型，以检查订单的某些详情或更新视图模型中的某些数据。

#### 更新 StartFragment 以使用视图模型

为了在 `StartFragment` 中使用共享视图模型，您将使用 `activityViewModels()` 而不是 `viewModels()` 委托类来初始化 `OrderViewModel`。

- `viewModels()` 可为您提供作用域限定为当前 fragment 的 `ViewModel` 实例。这会因 fragment 不同而异。
- `activityViewModels()` 可为您提供作用域限定为当前 activity 的 `ViewModel` 实例。因此，实例将在同一 activity 的多个 fragment 之间保持不变。

**使用 Kotlin 属性委托**

在 Kotlin 中，每个可变 (`var`) 属性都具有自动为其生成的默认 getter 和 setter 函数。当您为该属性赋值或读取其值时，系统会调用 setter 和 getter 函数。（对于只读属性 [`val`]，默认情况下仅为其生成 getter 函数。当您读取只读属性的值时，系统会调用此 getter 函数。）

Kotlin 中的属性委托可以帮助您将 getter-setter 的责任移交给另一个类。

此类（称为“委托类”）提供属性的 getter 和 setter 函数并处理其变更。

委托属性使用 `by` 子句和委托类实例进行定义：

```
// Syntax for property delegationvar <property-name> : <property-type> by <delegate-class>()
```

1. 在 `StartFragment` 类中，以类变量的形式获取对共享视图模型的引用。使用 `fragment-ktx` 库中的 `by activityViewModels()` Kotlin 属性委托。

   ```
   private val sharedViewModel: OrderViewModel by activityViewModels()
   ```

   您可能需要导入下面这些新类：

   ```
   import androidx.fragment.app.activityViewModelsimport com.example.cupcake.model.OrderViewModel
   ```

2. 针对 `FlavorFragment`、`PickupFragment` 和 `SummaryFragment` 类重复执行上面的步骤，您将在此 Codelab 的后面几部分中使用此 `sharedViewModel` 实例。

3. 返回 `StartFragment` 类，您现在可以使用视图模型了。在 `orderCupcake()` 方法的开头，调用共享视图模型中的 `setQuantity()` 方法以更新数量，然后再导航到口味 fragment。

   ```
   fun orderCupcake(quantity: Int) {    sharedViewModel.setQuantity(quantity)    findNavController().navigate(R.id.action_startFragment_to_flavorFragment)}
   ```

4. 在 `OrderViewModel` 类中，添加以下方法来检查是否已设置订购的纸杯蛋糕口味。在后面的步骤中，您将在 `StartFragment` 类中使用此方法。

   ```
   fun hasNoFlavorSet(): Boolean {    return _flavor.value.isNullOrEmpty()}
   ```

5. 在 `StartFragment` 类中的 `orderCupcake()` 方法内，设置数量后，将默认口味设置为“Vanilla”（如果未设置口味），然后再导航到口味 fragment。完整的方法将如下所示：

   ```
   fun orderCupcake(quantity: Int) {    sharedViewModel.setQuantity(quantity)    if (sharedViewModel.hasNoFlavorSet()) {        sharedViewModel.setFlavor(getString(R.string.vanilla))    }    findNavController().navigate(R.id.action_startFragment_to_flavorFragment)}
   ```

6. 构建应用以确保没有编译错误。不过，界面中应该没有明显的变化。

   

### ④将 ViewModel 与数据绑定搭配使用

接下来，您将使用数据绑定将视图模型数据绑定到界面。您还将根据用户在界面中做出的选择来更新共享视图模型。

**复习数据绑定**

回想一下，[数据绑定库](https://developer.android.com/topic/libraries/data-binding)是 [Android Jetpack](https://developer.android.com/jetpack) 的一部分。数据绑定使用声明性格式将布局中的界面组件绑定到应用中的数据源。简而言之，数据绑定就是将数据（从代码）绑定到视图 + 视图绑定（将视图绑定到代码）。通过设置这些绑定并让更新自动执行，可帮助您降低在忘记从代码中手动更新界面时出现错误的几率。

#### 根据用户选择更新口味

1. 在 `layout/fragment_flavor.xml` 中，在根 `<layout>` 标记内添加一个 `<data>` 标记。添加一个名为 `viewModel` 且类型为 `com.example.cupcake.model.OrderViewModel` 的布局变量。请确保类型属性中的软件包名称与应用中的共享视图模型类 `OrderViewModel` 的软件包名称相符。

   ```
   <layout ...>    <data>        <variable            name="viewModel"            type="com.example.cupcake.model.OrderViewModel" />    </data>    <ScrollView ...>    ...
   ```

2. 同样，针对 `fragment_pickup.xml` 和 `fragment_summary.xml` 重复执行上面的步骤以添加 `viewModel` 布局变量。您将在后面几部分中使用此变量。您不需要在 `fragment_start.xml` 中添加此代码，因为此布局不使用共享视图模型。

3. 在 `FlavorFragment` 类中的 `onViewCreated()` 内，将视图模型实例与布局中的共享视图模型实例绑定。在 `binding?.``apply` 代码块内添加以下代码。

   ```
   binding?.apply {    viewModel = sharedViewModel    ...}
   ```

   **apply 作用域函数**

   这可能是您首次看到 Kotlin 中的 `apply` 函数。`apply` 是 Kotlin 标准库中的[作用域函数](https://kotlinlang.org/docs/reference/scope-functions.html)。它在对象的上下文中执行代码块。它会形成一个临时作用域，在该作用域中，您可以访问对象而不需要其名称。`apply` 的常见用例是配置对象。此类调用可以解读为“对对象应用以下赋值”。

   **示例**：

   ```
   clark.apply {    firstName = "Clark"    lastName = "James"    age = 18}// The equivalent code without apply scope function would look like the following.clark.firstName = "Clark"clark.lastName = "James"clark.age = 18
   ```

4. 针对 `PickupFragment` 和 `SummaryFragment` 类中的 `onViewCreated()` 方法重复执行相同的步骤。

   ```
   binding?.apply {    viewModel = sharedViewModel    ...}
   ```

5. 在 `fragment_flavor.xml` 中，根据视图模型中的 `flavor` 值，使用新布局变量 `viewModel` 来设置单选按钮的 `checked` 属性。如果由单选按钮表示的口味与视图模型中保存的口味相同，则将单选按钮显示为选中状态 (`checked` = true)。**Vanilla** `RadioButton` 的选中状态的绑定表达式将如下所示：

   ```
   @{viewModel.flavor.equals(@string/vanilla)}
   ```

   从本质上讲，您是使用 [`equals`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-any/equals.html) 函数将 `viewModel.flavor` 属性与相应的字符串资源进行比较，以确定选中状态应该是 true 还是 false。

   **注意**：切记，绑定表达式以 `@` 符号开头并用花括号 `{}` 括起来。

   ```
   <RadioGroup   ...>   <RadioButton       android:id="@+id/vanilla"       ...       android:checked="@{viewModel.flavor.equals(@string/vanilla)}"       .../>   <RadioButton       android:id="@+id/chocolate"       ...       android:checked="@{viewModel.flavor.equals(@string/chocolate)}"       .../>   <RadioButton       android:id="@+id/red_velvet"       ...       android:checked="@{viewModel.flavor.equals(@string/red_velvet)}"       .../>   <RadioButton       android:id="@+id/salted_caramel"       ...       android:checked="@{viewModel.flavor.equals(@string/salted_caramel)}"       .../>   <RadioButton       android:id="@+id/coffee"       ...       android:checked="@{viewModel.flavor.equals(@string/coffee)}"       .../></RadioGroup>
   ```



#### **监听器绑定**

监听器绑定是在事件（如 `onClick` 事件）发生时运行的 lambda 表达式。它们类似于方法引用（如 `textview.setOnClickListener(clickListener)`），但监听器绑定可让您运行任意数据绑定表达式。

1. 在 `fragment_flavor.xml` 中，使用监听器绑定向单选按钮添加事件监听器。使用不带参数的 lambda 表达式，并通过传入相应的口味字符串资源对 `viewModel`.`setFlavor()` 方法进行调用。

```
<RadioGroup   ...>   <RadioButton       android:id="@+id/vanilla"       ...       android:onClick="@{() -> viewModel.setFlavor(@string/vanilla)}"       .../>   <RadioButton       android:id="@+id/chocolate"       ...       android:onClick="@{() -> viewModel.setFlavor(@string/chocolate)}"       .../>   <RadioButton       android:id="@+id/red_velvet"       ...       android:onClick="@{() -> viewModel.setFlavor(@string/red_velvet)}"       .../>   <RadioButton       android:id="@+id/salted_caramel"       ...       android:onClick="@{() -> viewModel.setFlavor(@string/salted_caramel)}"       .../>   <RadioButton       android:id="@+id/coffee"       ...       android:onClick="@{() -> viewModel.setFlavor(@string/coffee)}"       .../></RadioGroup>
```

运行应用，请注意 **Vanilla** 选项在口味 fragment 中默认处于选中状态。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/3095e824b4817b98.png" alt="3095e824b4817b98.png" style="zoom:33%;" />

太好了！现在，您可以继续构建后面的 fragment 了。



### ⑤更新取货 fragment 和汇总 fragment 以使用视图模型

在应用中导航，请注意，在取货 fragment 中，单选按钮选项标签是空白的。在此任务中，您将计算 4  个可用的取货日期，并将其显示在取货 fragment 中。您可以采用不同的方式来显示设置了格式的日期，下面是 Android  为此提供的一些有用的实用程序。

#### **创建取货选项列表**

##### **日期格式设置工具（[`SimpleDateFormat`](https://developer.android.com/reference/java/text/SimpleDateFormat) ）**

Android 框架提供了一个名为 [`SimpleDateFormat`](https://developer.android.com/reference/java/text/SimpleDateFormat) 的类，这个类用于以语言区域敏感的方式对日期进行格式设置和解析。使用该类可以对日期进行格式设置（日期 → 文本）和解析（文本 → 日期）。

您可以通过传入模式字符串和语言区域来创建 `SimpleDateFormat` 的实例：

```
SimpleDateFormat("E MMM d", Locale.getDefault())
```

像 `"E MMM d"` 这样的模式字符串表示日期和时间格式。字母 `'A'` 到 `'Z'` 以及 `'a'` 到 `'z'` 解释为模式字母，它们表示日期或时间字符串的组成部分。例如，`d` 表示几号，`y` 表示年份，`M` 表示月份。如果日期是 2018 年 1 月 4 日，模式字符串 `"EEE, MMM d"` 将解析为 `"Wed, Jul 4"`。如需查看模式字母的完整列表，请参阅相应的[文档](https://developer.android.com/reference/java/text/SimpleDateFormat#date-and-time-patterns)。

[`Locale`](https://developer.android.com/reference/java/util/Locale) 对象表示特定的地理、政治或文化区域。它表示语言/国家/地区/变体的组合。语言区域用于改变数字或日期等信息的表示方式，使其符合相应区域的惯例。日期和时间对语言区域敏感，因为它们在世界上不同地方的书写方式不同。您将使用 `Locale.getDefault()` 方法检索在用户设备上设置的语言区域信息，并将其传入 `SimpleDateFormat` 构造函数。

Android 中的语言区域是语言和国家/地区代码的组合。语言代码是两个字母的小写 ISO 语言代码，如“en”表示英语。国家/地区代码是两个字母的大写 ISO 国家/地区代码，如“US”表示美国。

现在，使用 `SimpleDateFormat` 和 `Locale` 确定 **Cupcake** 应用的可用取货日期。

1. 在 `OrderViewModel` 类中，添加以下名为 `getPickupOptions()` 的函数，以创建并返回取货日期列表。在该方法中，创建一个名为 `options` 的 `val` 变量，并将其初始化为 `mutableListOf``<String>()`。

   ```
   private fun getPickupOptions(): List<String> {   val options = mutableListOf<String>()}
   ```

2. 使用 `SimpleDateFormat` 创建格式设置工具字符串，并传递模式字符串 `"E MMM d"` 和语言区域。在模式字符串中，`E` 代表星期几，它解析为“**Tue Dec 10**”。

   ```
   val formatter = SimpleDateFormat("E MMM d", Locale.getDefault())
   ```

   当 Android Studio 提示时，导入 `java.text.SimpleDateFormat` 和 `java.util.Locale`。

3. 获取 `Calendar` 实例并将其分配给一个新变量。将此变量设为 `val`。此变量将包含当前日期和时间。此外，还应导入 `java.util.Calendar`。

   ```
   val calendar = Calendar.getInstance()
   ```

4. 构建一个日期列表，从当前日期开始，还有接下来的三个日期。由于您需要 4 个日期选项，因此请重复此代码块 4 次。此 [`repeat`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/repeat.html) 代码块会设置日期的格式，将其添加到日期选项列表，然后让日历按 1 天递增。

   ```
   repeat(4){	options.add(formatter.format(calendar.time))	calendar.add(Calendar.DATE, 1)}
   ```

   

5. 在方法的末尾返回更新后的 `options`。下面是您完成的方法：

   ```
   private fun getPickupOptions(): List<String> {   val options = mutableListOf<String>()   val formatter = SimpleDateFormat("E MMM d", Locale.getDefault())   val calendar = Calendar.getInstance()   // Create a list of dates starting with the current date and the following 3 dates   repeat(4) {       options.add(formatter.format(calendar.time))       calendar.add(Calendar.DATE, 1)   }   return options}
   ```

6. 在 `OrderViewModel` 类中，添加一个名为 `dateOptions` 的类属性，它是一个 `val`。使用您刚刚创建的 `getPickupOptions()` 方法对其进行初始化。

   ```
   val dateOptions = getPickupOptions()
   ```



#### 更新布局以显示取货选项

现在，视图模型中已经有了四个可用的取货日期，下面更新 `PickupFragment` 以显示这些日期。您还将使用数据绑定显示每个单选按钮的选中状态，并在选中了其他单选按钮时更新视图模型中的日期。此实现类似于口味 fragment 中的数据绑定。

在 `fragment_pickup.xml` 中：

单选按钮 `option0` 表示 `viewModel` 中的 `dateOptions[0]`（今天）

单选按钮 `option1` 表示 `viewModel` 中的 `dateOptions[1]`（明天）

单选按钮 `option2` 表示 `viewModel` 中的 `dateOptions[2]`（后天）

单选按钮 `option3` 表示 `viewModel` 中的 `dateOptions[3]`（大后天）

1. 在 `fragment_pickup.xml` 中，对于 `option0` 单选按钮，根据视图模型中的 `date` 值，使用新布局变量 `viewModel` 来设置 `checked` 属性。将 `viewModel.date` 属性与 `dateOptions` 列表中的第一个字符串（即当前日期）进行比较。使用 [`equals`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-any/equals.html) 函数进行比较，最终的绑定表达式如下所示：

   ```
   @{viewModel.date.equals(viewModel.dateOptions[0])}
   ```

2. 对于同一单选按钮，使用监听器绑定向 `onClick` 属性添加事件监听器。点击此单选按钮选项时，在 `viewModel` 上对 `setDate()` 进行调用，并传入 `dateOptions[0]`。

3. 对于同一单选按钮，将 `text` 属性值设置为 `dateOptions` 列表中的第一个字符串。

   ```
   <RadioButton   android:id="@+id/option0"   ...   android:checked="@{viewModel.date.equals(viewModel.dateOptions[0])}"   android:onClick="@{() -> viewModel.setDate(viewModel.dateOptions[0])}"   android:text="@{viewModel.dateOptions[0]}"   ...   />
   ```

4. 针对其他单选按钮重复执行上面的步骤，相应地更改 `dateOptions` 的索引。

   ```
   <RadioButton   android:id="@+id/option1"   ...   android:checked="@{viewModel.date.equals(viewModel.dateOptions[1])}"   android:onClick="@{() -> viewModel.setDate(viewModel.dateOptions[1])}"   android:text="@{viewModel.dateOptions[1]}"   ... /><RadioButton   android:id="@+id/option2"   ...   android:checked="@{viewModel.date.equals(viewModel.dateOptions[2])}"   android:onClick="@{() -> viewModel.setDate(viewModel.dateOptions[2])}"   android:text="@{viewModel.dateOptions[2]}"   ... /><RadioButton   android:id="@+id/option3"   ...   android:checked="@{viewModel.date.equals(viewModel.dateOptions[3])}"   android:onClick="@{() -> viewModel.setDate(viewModel.dateOptions[3])}"   android:text="@{viewModel.dateOptions[3]}"   ... />
   ```

5. 运行应用，您应该会看到接下来几天作为可用的取货选项。您的屏幕截图会因您的当前日期而异。请注意，默认情况下未选中任何选项。您将在下一步中实现此行为。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/b55b3a36e2aa7be6.png" alt="b55b3a36e2aa7be6.png" style="zoom:33%;" />

6. 在 `OrderViewModel` 类中，创建一个名为 `resetOrder()` 的函数，以重置视图模型中的 `MutableLiveData` 属性。将 `dateOptions` 列表中的当前日期值赋给 `_date.``value.`。

7. 向类中添加一个 `init` 代码块，并从其调用新方法 `resetOrder()`。

   ```
   init{	resetOrder()}
   ```

   

8. 从类的属性声明中移除初始值。现在，创建 `OrderViewModel` 的实例时，您使用 `init` 代码块来初始化属性。

   ```
   private val _quantity = MutableLiveData<Int>()val quantity: LiveData<Int> = _quantityprivate val _flavor = MutableLiveData<String>()val flavor: LiveData<String> = _flavorprivate val _date = MutableLiveData<String>()val date: LiveData<String> = _dateprivate val _price = MutableLiveData<Double>()val price: LiveData<Double> = _price
   ```

9. 再次运行应用，请注意，默认情况下选中了今天的日期。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/bfe4f1b82977b4bc.png" alt="bfe4f1b82977b4bc.png" style="zoom:33%;" />

#### 更新摘要 fragment 以使用视图模型

现在，让我们继续构建最后一个 fragment。订单摘要 fragment 旨在显示订单详情的摘要。在此任务中，您将利用共享视图模型中的所有订单信息，并使用数据绑定更新屏幕上的订单详情。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/78f510e10d848dd2.png" alt="78f510e10d848dd2.png" style="zoom:33%;" />

1. 在 `fragment_summary.xml` 中，确保您已声明视图模型数据变量 `viewModel`。

   ```
   <layout ...>    <data>        <variable            name="viewModel"            type="com.example.cupcake.model.OrderViewModel" />    </data>    <ScrollView ...>    ...
   ```

2. 在 `SummaryFragment` 的 `onViewCreated()` 中，确保已初始化 `binding.viewModel`。

3. 在 `fragment_summary.xml` 中，读取视图模型中的数据，以使用订单摘要详情更新屏幕。通过添加以下文本属性，更新数量、口味和日期 `TextViews`。数量的类型为 `Int`，因此您需要将其转换为字符串。

   ```
   <TextView   android:id="@+id/quantity"   ...   android:text="@{viewModel.quantity.toString()}"   ... /><TextView   android:id="@+id/flavor"   ...   android:text="@{viewModel.flavor}"   ... /><TextView   android:id="@+id/date"   ...   android:text="@{viewModel.date}"   ... />
   ```

4. 运行并测试应用以验证您选择的订单选项是否显示在订单摘要中。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/7091453fa817b55.png" alt="7091453fa817b55.png" style="zoom:33%;" />

### ⑥根据订单详情计算价格

看一下此 Codelab 的最终应用屏幕截图，您会注意到，价格确实显示在每个 fragment 中（`StartFragment` 除外），这样用户在创建订单时就会知道价格。

![3b6a68cab0b9ee2.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/3b6a68cab0b9ee2.png)

下面是纸杯蛋糕店关于如何计算价格的规则。

- 每个纸杯蛋糕 $2.00
- 如果当天取货，订单价格另加 $3.00

因此，如果订购了 6 个纸杯蛋糕，那么价格将为 6 个纸杯蛋糕 x $2/个 = $12。如果用户想要当天取货，那么需要额外支付 $3，这样一来，订单总价就为 $15。

#### 更新视图模型中的价格

如需在应用中添加对此功能的支持，请先处理每个纸杯蛋糕的价格，暂时忽略当天取货费用。

1. 打开 `OrderViewModel.kt`，将每个纸杯蛋糕的价格存储在一个变量中。在文件的顶部将其声明为一个顶级专用常量，该声明在类定义之外（但在 import 语句之后）。使用 `const` 修饰符，如需将其设为只读，请使用 `val`。

   ```
   package ...import ...private const val PRICE_PER_CUPCAKE = 2.00class OrderViewModel : ViewModel() {    ...
   ```

   回想一下，常量值（在 Kotlin 中使用 `const` 关键字标记）不会更改，并且该值在编译时已知。如需详细了解常量，请参阅相应的[文档](https://kotlinlang.org/docs/reference/properties.html#compile-time-constants)。

2. 现在，您已经定义了每个纸杯蛋糕的价格，接下来创建一个辅助方法来计算价格。此方法可以为 `private`，因为它只在此类中使用。您将在下一项任务中更改价格逻辑以包含当天取货费用。

   ```
   private fun updatePrice() {    _price.value = (quantity.value ?: 0) * PRICE_PER_CUPCAKE}
   ```

   这行代码用每个纸杯蛋糕的价格乘以订购的纸杯蛋糕数量。对于圆括号中的代码，由于 `quantity.value` 的值可以为 null，因此使用 elvis 运算符 (`?:`)。elvis 运算符 (`?:`) 表示如果左侧的表达式不为 null，则使用该表达式。否则，如果左侧的表达式为 null，则使用 elvis 运算符右侧的表达式（在本例中为 `0`）。

   **趣味小知识**：elvis 运算符 (`?:`) 是以摇滚明星 Elvis Presley 的名字命名的，因为当您从侧面看时，它就像是留着[飞机头](https://en.wikipedia.org/wiki/Quiff)的 [Elvis Presley](https://en.wikipedia.org/wiki/Elvis_Presley) 的表情符。

3. 在同一 `OrderViewModel` 类中，设置数量后更新价格变量。在 `setQuantity()` 函数中对新函数进行调用。

   ```
   fun setQuantity(numberCupcakes: Int) {    _quantity.value = numberCupcakes    updatePrice()}
   ```

#### **将价格属性绑定到界面**

1. 在 `fragment_flavor.xml`、`fragment_pickup.xml` 和 `fragment_summary.xml` 的布局中，确保定义了类型为 `com.example.cupcake.model.OrderViewModel` 的数据变量 `viewModel`。

   ```
   <layout ...>    <data>        <variable            name="viewModel"            type="com.example.cupcake.model.OrderViewModel" />    </data>    <ScrollView ...>    ...
   ```

2. 在每个 fragment 类的 `onViewCreated()` 方法中，确保将 fragment 中的视图模型对象实例绑定到布局中的视图模型数据变量。

   ```
   binding?.apply {    viewModel = sharedViewModel    ...}
   ```

3. 在每个 fragment 布局中，如果价格显示在布局中，则使用 `viewModel` 变量设置价格。首先修改 `fragment_flavor.xml` 文件。对于 `subtotal` 文本视图，将 `android:text` 属性的值设置为 `"@{@string/subtotal_price(viewModel.price)}".`。此数据绑定布局表达式使用字符串资源 `@string/subtotal_price`，并传入一个参数，它是来自视图模型的价格，因此输出将显示正确的字符串，例如 **Subtotal 12.0**。

   ```
   ...<TextView    android:id="@+id/subtotal"    android:text="@{@string/subtotal_price(viewModel.price)}"    ... />...
   ```

   您使用的是 `strings.xml` 文件中已声明的以下字符串资源：

   ```
   <string name="subtotal_price">Subtotal %s</string>
   ```

4. 运行应用。如果您在起始 fragment 中选择 **One cupcake**，口味 fragment 将显示 **Subtotal 2.0**。如果您选择 **Six cupcakes**，口味 fragment 将显示 **Subtotal 12.0**，依此类推。您稍后会将价格的格式设置为适当的货币格式，因此目前此行为符合预期。

   | ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/13e316e13779d3c2.png) | ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/adb9342d3a0da64e.png) |
   | ------------------------------------------------------------ | ------------------------------------------------------------ |

5. 现在，对取货 fragment 和摘要 fragment 进行类似的更改。在 `fragment_pickup.xml` 和 `fragment_summary.xml` 布局中，修改文本视图，使其也使用 `viewModel` `price` 属性。

   ```
   fragment_pickup.xml...<TextView    android:id="@+id/subtotal"    ...    android:text="@{@string/subtotal_price(viewModel.price)}"    ... />...fragment_summary.xml
   ```

   ...

   ```
   <TextView   android:id="@+id/total"   ...   android:text="@{@string/total_price(viewModel.price)}"   ... />
   ```

6. 运行应用。确保订购数量为 1 个、6 个和 12 个纸杯蛋糕时订单摘要中显示的价格计算正确。前面已经提到，预计目前价格的格式设置不正确（$2 将显示为 2.0，$12 将显示为 12.0）。

   | ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/f53d06e5a3c12e96.png) | ![img](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/f6eda1308338db23.png) |
   | ------------------------------------------------------------ | ------------------------------------------------------------ |



#### 当天取货收取额外费用

在此任务中，您将实现第二个规则，即如果当天取货，订单价格另加 $3.00。

1. 在 `OrderViewModel` 类中，针对当天取货费用定义一个新的顶级专用常量。

   ```
   private const val PRICE_FOR_SAME_DAY_PICKUP = 3.00
   ```

   

2. 在 `updatePrice()` 中，检查用户是否选择了当天取货。检查视图模型中的日期 (`_date.``value`) 是否与 `dateOptions` 列表中的第一项（始终为当天）相同。

   ```
   private fun updatePrice() {    _price.value = (quantity.value ?: 0) * PRICE_PER_CUPCAKE    if (dateOptions[0] == _date.value) {    }}
   ```

3. 为使这些计算更简单，引入一个临时变量 `calculatedPrice`。计算更新后的价格，并将其赋值回 `_price.``value`。

   ```
   private fun updatePrice() {    var calculatedPrice = (quantity.value ?: 0) * PRICE_PER_CUPCAKE    // If the user selected the first option (today) for pickup, add the surcharge    if (dateOptions[0] == _date.value) {        calculatedPrice += PRICE_FOR_SAME_DAY_PICKUP    }    _price.value = calculatedPrice}
   ```

4. 从 `setDate()` 方法调用 `updatePrice()` 辅助方法以添加当天取货费用。

   ```
   fun setDate(pickupDate: String) {    _date.value = pickupDate    updatePrice()}
   ```

5. 运行应用，并在应用中导航。您会注意到，如果更改取货日期，不会从总价中去掉当天取货费用。这是因为，价格在视图模型中发生了变化，但没有通知绑定布局。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/2ea8e000fb4e6ec8.png" alt="2ea8e000fb4e6ec8.png" style="zoom:33%;" />



#### 设置生命周期所有者以观察 LiveData

[`LifecycleOwner`](https://developer.android.com/reference/androidx/lifecycle/LifecycleOwner) 是一个具有 Android 生命周期的类，如 activity 或 fragment。仅当生命周期所有者处于活动状态时（`STARTED` 或 `RESUMED`），`LiveData` 观察器才会观察应用数据的更改。

在应用中，`LiveData` 对象或可观察的数据是视图模型中的 `price` 属性。生命周期所有者是口味 fragment、取货 fragment 和摘要 fragment。`LiveData` 观察器是包含价格之类的可观察数据的布局文件中的绑定表达式。借助数据绑定，当可观察的值发生变化时，它绑定到的界面元素会自动更新。

绑定表达式的示例：`android:text="@{@string/subtotal_price(viewModel.price)}"`

为使界面元素自动更新，您必须在应用中将 `binding.lifecycleOwner` 与生命周期所有者关联。接下来您将实现此行为。

1. 在 `FlavorFragment`、`PickupFragment` 和 `SummaryFragment` 类中的 `onViewCreated()` 方法内，在 `binding?.apply` 代码块中添加以下代码。这样会在绑定对象上设置生命周期所有者。通过设置生命周期所有者，应用将能够观察 `LiveData` 对象。

   ```
   binding?.apply {    lifecycleOwner = viewLifecycleOwner    ...}
   ```

2. 再次运行应用。在取货屏幕中，更改取货日期，并注意价格自动更改方式的差异。当天取货费用会正确地反映在摘要屏幕中。

3. 请注意，如果您选择当天取货，订单的价格会增加 $3.00。如果选择在将来的任何日期取货，价格应该仍然是纸杯蛋糕的数量 x $2.00。

4. 使用不同的纸杯蛋糕数量、口味和取货日期来测试不同的用例。现在，您应该会看到每个 fragment 上视图模型中的价格更新。最好的一点是，您不必编写额外的 Kotlin 代码，即可让界面每次都随价格更新。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/f4c0a3c5ea916d03.png" alt="f4c0a3c5ea916d03.png" style="zoom:33%;" />

   

5. 为了完成价格功能的实现，您需要将价格的格式设置为本地货币。





#### 通过 LiveData 转换设置价格的格式

`LiveData` 转换方法提供了一种方式来对源 `LiveData` 执行数据操作，并返回生成的 `LiveData` 对象。简单来说，就是它将 `LiveData` 的值转换为其他值。除非某个观察器正在观察 `LiveData` 对象，否则不会计算这些转换。

[`Transformations.map()`](https://developer.android.com/reference/androidx/lifecycle/Transformations.html#map(androidx.lifecycle.LiveData, androidx.arch.core.util.Function)) 是一个转换函数，此方法将源 `LiveData` 和一个函数作为参数。该函数可操控源 `LiveData`，并返回更新后的值（该值也可观察）。

您可以使用 LiveData 转换的一些实时示例如下：

- 设置要显示的日期和时间字符串的格式
- 对项列表进行排序
- 对项进行过滤或分组
- 从列表中计算结果（如所有项的总和与项数）、返回最后一项，等等。

在此任务中，您将使用 [`Transformations.map()`](https://developer.android.com/reference/androidx/lifecycle/Transformations.html#map(androidx.lifecycle.LiveData, androidx.arch.core.util.Function)) 方法设置价格的格式以使用本地货币。您会将十进制值 (`LiveData<Double>`) 形式的原始价格转换为字符串值 (`LiveData<String>`)。

1. 在 `OrderViewModel` 类中，将后备属性类型更改为 `LiveData<String>`，而不是 `LiveData<Double>.`。设置了格式的价格将是一个带有货币符号（如“$”）的字符串。您将在下一步中修复初始化错误。

2. 使用 [`Transformations.map()`](https://developer.android.com/reference/androidx/lifecycle/Transformations.html#map(androidx.lifecycle.LiveData, androidx.arch.core.util.Function)) 初始化新的变量，并传入 `_price` 和一个 lambda 函数。使用 [`NumberFormat`](https://developer.android.com/reference/kotlin/android/icu/text/NumberFormat) 类中的 `getCurrencyInstance()` 方法将价格转换为本地货币格式。转换代码将如下所示。

   ```
   val price:LiveData<String> = Transformations.map(_price){	NumberFormat.getCurrencyInstance().format(it)}
   ```

3. 您需要导入 `androidx.lifecycle.Transformations` 和 `java.text.NumberFormat`

4. 运行应用。现在，您应该会看到小计和合计的设置了格式的价格字符串。这样用户理解起来就容易多了！

   ![1853bd13a07f1bc7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/1853bd13a07f1bc7.png)

5. 测试应用是否按预期运行。测试一些用例，如订购一个纸杯蛋糕、订购六个纸杯蛋糕或订购十二个纸杯蛋糕。确保价格在每个屏幕上都能正确更新。对于口味 fragment 和取货 fragment，应显示 **Subtotal $2.00**；对于订单摘要，应显示 **Total $2.00**。此外，还应确保订单摘要显示正确的订单详情。





### ⑦使用监听器绑定来设置点击监听器

在此任务中，您将使用监听器绑定将 fragment 类中的按钮点击监听器绑定到布局。

1. 在布局文件 `fragment_start.xml` 中，添加一个名为 `startFragment` 且类型为 `com.example.cupcake.StartFragment` 的数据变量。确保 fragment 的软件包名称与应用的软件包名称相符。

   ```
   <layout ...>    <data>        <variable            name="startFragment"            type="com.example.cupcake.StartFragment" />    </data>    ...    <ScrollView ...>
   ```

2. 在 `StartFragment.kt` 的 `onViewCreated()` 方法中，将新的数据变量绑定到 fragment 实例。您可以使用 `this` 关键字来访问 fragment 内的 fragment 实例。移除 `binding?.apply` 代码块以及其中的代码。完成后的方法应如下所示

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {    super.onViewCreated(view, savedInstanceState)    binding?.startFragment = this}
   ```

3. 在 `fragment_start.xml` 中，使用监听器绑定向按钮的 `onClick` 属性添加事件监听器，在 `startFragment` 上对 `orderCupcake()` 进行调用，并传入纸杯蛋糕的数量。

   ```
   <Button    android:id="@+id/order_one_cupcake"    android:onClick="@{() -> startFragment.orderCupcake(1)}"    ... /><Button    android:id="@+id/order_six_cupcakes"    android:onClick="@{() -> startFragment.orderCupcake(6)}"    ... /><Button    android:id="@+id/order_twelve_cupcakes"    android:onClick="@{() -> startFragment.orderCupcake(12)}"    ... />
   ```

4. 运行应用。请注意，起始 fragment 中的按钮点击处理程序按预期运行。

5. 同样，也在其他布局中添加上面的数据变量，以绑定 fragment 实例 `fragment_flavor.xml`、`fragment_pickup.xml` 和 `fragment_summary.xml`。

   在 `fragment_flavor.xml` 中：

   ```
   <layout ...>    <data>        <variable            ... />        <variable            name="flavorFragment"            type="com.example.cupcake.FlavorFragment" />    </data>    <ScrollView ...>
   ```

   在 `fragment_pickup.xml` 中：

   ```
   <layout ...>    <data>        <variable            ... />        <variable            name="pickupFragment"            type="com.example.cupcake.PickupFragment" />    </data>    <ScrollView ...>
   ```

   在 `fragment_summary.xml` 中：

   ```
   <layout ...>    <data>        <variable            ... />        <variable            name="summaryFragment"            type="com.example.cupcake.SummaryFragment" />    </data>    <ScrollView ...>
   ```

6. 在其余 fragment 类的 `onViewCreated()` 方法中，删除用于手动设置按钮上的点击监听器的代码。

7. 在 `onViewCreated()` 方法中，将 fragment 数据变量与 fragment 实例绑定。您将在此处以不同的方式使用 `this` 关键字，因为在 `binding?.apply` 代码块内，`this` 关键字是指绑定实例，而不是 fragment 实例。使用 `@` 并明确指定 fragment 类名称，例如 `this@FlavorFragment`。完成后的 `onViewCreated()` 方法应如下所示：

   `FlavorFragment` 类中的 `onViewCreated()` 方法应如下所示：

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {    super.onViewCreated(view, savedInstanceState)    binding?.apply {        lifecycleOwner = viewLifecycleOwner        viewModel = sharedViewModel        flavorFragment = this@FlavorFragment    }}
   ```

   `PickupFragment` 类中的 `onViewCreated()` 方法应如下所示：

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {   super.onViewCreated(view, savedInstanceState)   binding?.apply {       lifecycleOwner = viewLifecycleOwner       viewModel = sharedViewModel       pickupFragment = this@PickupFragment   }}
   ```

   `SummaryFragment` 类中生成的 `onViewCreated()` 方法应如下所示：

   ```
   override fun onViewCreated(view: View, savedInstanceState: Bundle?) {   super.onViewCreated(view, savedInstanceState)   binding?.apply {       lifecycleOwner = viewLifecycleOwner       viewModel = sharedViewModel       summaryFragment = this@SummaryFragment   }}
   ```

8. 同样，在其他布局文件中，向按钮的 `onClick` 属性添加监听器绑定表达式。

   在 `fragment_flavor.xml` 中：

   ```
   <Button    android:id="@+id/next_button"    android:onClick="@{() -> flavorFragment.goToNextScreen()}"    ... />
   ```

   在 `fragment_pickup.xml` 中：

   ```
   <Button
       android:id="@+id/next_button"
       android:onClick="@{() -> pickupFragment.goToNextScreen()}"
       ... />
   ```

   在 `fragment_summary.xml` 中：

   ```
   <Button
       android:id="@+id/send_button"
       android:onClick="@{() -> summaryFragment.sendOrder()}"
       ...>
   ```

9. 运行应用以验证按钮是否仍按预期工作。行为上应该没有明显的变化，但现在您已使用监听器绑定设置了点击监听器！

恭喜您完成了此 Codelab 的学习并构建了 **Cupcake** 应用！不过，该应用还没有彻底完成。在下一个 Codelab 中，您将添加一个 **Cancel** 按钮并修改返回堆栈。您还会学习什么是返回堆栈以及其他新概念。到时候见！

### ⑧小结

- [`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 是 [Android 架构组件](https://developer.android.com/topic/libraries/architecture)的一部分，保存在 `ViewModel` 中的应用数据在配置更改期间会保留。如需将 `ViewModel` 添加到应用，您可以创建一个新类，并从 [`ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel) 类扩展该类。
- [共享 `ViewModel`](https://developer.android.com/topic/libraries/architecture/viewmodel.html#sharing) 用于将来自多个 fragment 的应用数据保存在单个 `ViewModel` 中。应用中的多个 fragment 将根据其 activity 作用域访问共享 `ViewModel`。
- [`LifecycleOwner`](https://developer.android.com/reference/androidx/lifecycle/LifecycleOwner) 是一个具有 Android 生命周期的类，如 activity 或 fragment。
- 仅当生命周期所有者处于活动状态时（`STARTED` 或 `RESUMED`），`LiveData` 观察器才会观察应用数据的更改。
- 监听器绑定是在事件（如 `onClick` 事件）发生时运行的 lambda 表达式。它们类似于方法引用（如 `textview.setOnClickListener(clickListener)`），但监听器绑定可让您运行任意数据绑定表达式。
- `LiveData` 转换方法提供了一种方式来对源 `LiveData` 执行数据操作，并返回生成的 `LiveData` 对象。
- Android 框架提供了一个名为 [`SimpleDateFormat`](https://developer.android.com/reference/java/text/SimpleDateFormat) 的类，它是一个用于以语言区域敏感的方式对日期进行格式设置和解析的类。使用该类可以对日期进行格式设置（日期 → 文本）和解析（文本 → 日期）。





## 16.导航和返回堆栈

此 Codelab 使用上一个 Codelab 中的 **Cupcake** 应用。您可以使用完成前一个 Codelab 获得的代码，也可以从 GitHub 下载起始代码。

**下载此 Codelab 的起始代码**

如果您从 GitHub 下载起始代码，请注意该项目的文件夹名称为 `android-basics-kotlin-cupcake-app-viewmodel`。在 Android Studio 中打开项目时，请选择此文件夹。

**起始代码网址**：

https://github.com/google-developer-training/android-basics-kotlin-cupcake-app/tree/viewmodel

### ①实现向上按钮行为

在 **Cupcake** 应用中，应用栏会显示一个箭头，点按该箭头可返回上一屏幕。该按钮称为 **Up** 按钮，您在之前的 Codelab 中已对此有所了解。鉴于 **Up** 按钮当前无法执行任何操作，因此请先修复应用中这一导航错误。

![fbdc1793f9fea6da.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/fbdc1793f9fea6da.png)

1. 在 `MainActivity` 中，您应该已经获得相应代码，以便使用导航控制器设置应用栏（也称为操作栏）。将 `navController` 设为类变量，从而可以在另一种方法中使用。

   ```
   class MainActivity : AppCompatActivity(R.layout.activity_main) {
   
       private lateinit var navController: NavController
   
       override fun onCreate(savedInstanceState: Bundle?) {
           super.onCreate(savedInstanceState)
   
           val navHostFragment = supportFragmentManager
                   .findFragmentById(R.id.nav_host_fragment) as NavHostFragment
           navController = navHostFragment.navController
   
           setupActionBarWithNavController(navController)
       }
   }
   ```

2. 在同一类中，添加代码以替换 `onSupportNavigateUp()` 函数。此代码将要求 `navController` 处理应用中的向上导航。否则，回退到处理 **Up** 按钮的超类实现（在 `AppCompatActivity` 中）。

   ```
   override fun onSupportNavigateUp(): Boolean {
      return navController.navigateUp() || super.onSupportNavigateUp()
   }
   ```

3. 运行应用。现在，**Up** 按钮在 `FlavorFragment`、`PickupFragment` 和 `SummaryFragment` 中应能正常工作。在导航到订单流程中的前几步时，fragment 应显示视图模型提供的正确口味和自提日期。



### ②了解任务和返回堆栈

现在，您将在应用的订单流程中引入 **Cancel** 按钮。用户在订单流程中的任何时刻取消订单都会使用户返回 `StartFragment`。为处理此行为，您需了解 Android 中的任务和返回堆栈。

#### **任务**

Android 中的 activity 存在于任务中。当您从启动器图标首次打开应用时，Android 会使用主 activity 创建一个新任务。任务是用户在执行某项作业（例如，查看电子邮件、创建纸杯蛋糕订单、拍照）时与之互动的一系列 activity。

activity 排列在一个堆栈中，称为“返回堆栈”，其中，用户访问的每个新的 activity 都会推送到任务的返回堆栈中。您可以将它看作是一摞煎饼，每一张新的煎饼都会加到这摞煎饼的最上方。堆栈顶部的 activity 是用户当前正在与之互动的 activity。堆栈中位于下方的 activity 已置于后台，并且已停止。

![517054e483795b46.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/517054e483795b46.png)

当用户需要向后导航时，返回堆栈十分有用。Android 可以从堆栈顶部移除当前 activity，将其销毁，然后重新启动其下方的  activity。此过程是将一个 activity 从堆栈中弹出，并将前一个 activity  置于前台，以便用户与之互动。如果用户想要返回多次，Android 将一直从堆栈顶部弹出 activity，直到接近堆栈的底部。当返回堆栈中不再有 activity 时，用户会被带回设备的启动器屏幕（或启动该应用的应用）。

我们来看看您使用以下 2 个 activity 实现的 **Words** 应用的版本：`MainActivity` 和 `DetailActivity`。

当您首次启动应用时，系统会打开 `MainActivity` 并将其添加到任务的返回堆栈中。

![4bc8f5aff4d5ee7f.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/4bc8f5aff4d5ee7f.png)

当您点击某个字母时，系统会启动 `DetailActivity`，并将其推送到返回堆栈。这意味着，`DetailActivity` 已创建、启动和恢复，因此用户可以与之互动。`MainActivity` 会置于后台，并且在图表中显示为灰色的背景色。

![80f7c594ae844b84.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/80f7c594ae844b84.png)

如果您点按 **Back** 按钮，系统会从返回堆栈中弹出 `DetailActivity`，并销毁和完成 `DetailActivity` 实例。

![80f532af817191a4.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/80f532af817191a4.png)

然后，返回堆栈顶部的下一个项目 (`MainActivity`) 会进入前台。

![85004712d2fbcdc1.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/85004712d2fbcdc1.png)

**注意**：打开应用后，如果点按设备上的**主屏幕**，应用的整个任务都会置于后台。如果您再次点按应用的启动器图标，Android 将查看您的应用是否存在现有任务，如存在，Android 会将该任务置于前台（返回堆栈保持不变）。如果不存在现有任务，Android  将为您创建新任务，并启动主 activity，将其推送到返回堆栈。

返回堆栈可以跟踪用户已打开的 activity，与此相同，返回堆栈还可以借助 Jetpack Navigation 组件跟踪用户访问过的 fragment 目的地。

![fe417ac5cbca4ce7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/fe417ac5cbca4ce7.png)

借助 Navigation 库，您可以在用户按 **Back** 按钮时从返回堆栈弹出 fragment 目的地。此默认行为将自动实现，您无需实施任何操作。如果您需要自定义返回堆栈行为，您只需编写代码即可，您将为 **Cupcake** 应用执行此操作。



#### **Cupcake 应用的默认行为**

让我们一起看看在 **Cupcake** 应用中返回堆栈如何工作。该应用中只有一个 activity，但是用户导航有多个 fragment 目的地。因此，最好在每次点按 **Back** 按钮时，它能返回到上一个 fragment 目的地。

首次打开应用时，将显示 `StartFragment` 目的地。该目的地会推送到堆栈的顶部。

![cf0e80b4907d80dd.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/cf0e80b4907d80dd.png)

选择要订购的纸杯蛋糕数量后，您将导航到 `FlavorFragment`（此时会被推送到返回堆栈）。

![39081dcc3e537e1e.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/39081dcc3e537e1e.png)

选择一种口味并点按 **Next** 即可导航到 `PickupFragment`，此时，PickupFragment 将被推送到返回堆栈。

![37dca487200f8f73.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/37dca487200f8f73.png)

最后，选择自提日期并点按 **Next** 后，您将导航到 `SummaryFragment`，此时，SummaryFragment 将被添加到返回堆栈的顶部。

![d67689affdfae0dd.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/d67689affdfae0dd.png)

如果您从 `SummaryFragment` 点按 **Back** 或 **Up** 按钮，`SummaryFragment` 将从堆栈中弹出并被销毁。

![215b93fd65754017.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/215b93fd65754017.png)

`PickupFragment` 现在位于返回堆栈的顶部，并向用户显示。

![37dca487200f8f73.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/37dca487200f8f73.png)

再次点按 **Back** 或 **Up** 按钮。系统从堆栈中弹出 `PickupFragment`，然后显示 `FlavorFragment`。

再次点按 **Back** 或 **Up** 按钮。系统从堆栈中弹出 `FlavorFragment`，然后显示 `StartFragment`。

当您导航回订单流程中之前的步骤时，一次只能弹出一个目的地。但在下一个任务中，您将向应用添加取消订单功能。这可能需要您一次在返回堆栈中弹出多个目的地，才能将用户返回 `StartFragment` 以开启新订单。

![e3dae0f492450207.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/e3dae0f492450207.png)

## 

#### 修改 Cupcake 应用中的返回堆栈

修改 `FlavorFragment`、`PickupFragment` 和 `SummaryFragment` 类和布局文件，以便为用户提供 Cancel 订单按钮。

##### 添加导航操作

首先，将导航操作添加到应用的导航图中，以便用户从后续目的地导航回 `StartFragment`。

1. 转到 **res > navigation > nav_graph.xml** 文件并选择 **Design** 视图，以打开 **Navigation Editor**。

2. 目前，有一个从 `startFragment` 到 `flavorFragment` 的操作，从 `flavorFragment` 到 `pickupFragment` 的操作，以及从 `pickupFragment` 到 `summaryFragment` 的操作。

3. 点击并拖动即可创建从 `summaryFragment` 到 `startFragment` 的新导航操作。如需回顾如何关联导航图中的目的地，您可以查看[这些说明](https://developer.android.com/guide/navigation/navigation-getting-started#connect)。

4. 从 `pickupFragment` 中，点击并拖动以创建到 `startFragment` 的新操作。

5. 从 `flavorFragment` 中，点击并拖动以创建到 `startFragment` 的新操作。

6. 完成后，导航图应如下所示。

   ![dcbd27a08d24cfa0.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/dcbd27a08d24cfa0.png)

7. 通过这些更改，用户可以从订单流程中的某个后续 fragment 遍历订单流程的开头。现在，您需要使用能够实际使用这些操作进行导航的代码。合适位置为点按 **Cancel** 按钮时。

##### 向布局添加“Cancel”按钮

首先，为除 `StartFragment` 以外的所有 fragment 的布局文件添加 **Cancel** 按钮。如果您已经在订单流程的第一个屏幕上，则无需取消订单。

1. 打开 `fragment_flavor.xml` 布局文件。

2. 使用 **Split** 视图直接修改 XML 并并排查看预览。

3. 在小计文本视图和 **Next** 按钮之间添加 **Cancel** 按钮。为 Cancel 按钮分配资源 ID `@+id/cancel_button` 和文本，显示为 `@string/cancel`。

   该按钮应水平放置于 **Next** 按钮旁边，使之与 Next 按钮显示在一排。对于垂直约束条件，请将 **Cancel** 按钮的顶部约束为 **Next** 按钮的顶部。对于水平约束条件，请将 **Cancel** 按钮的起始位置约束到父容器，并将其结束位置约束为 **Next** 按钮的起始位置。

   此外，请将 **Cancel** 按钮的高度和宽度分别指定为 `wrap_content` 和 `0dp`，以便其可以与另外一个按钮均分屏幕宽度。请注意，在下一步之前，该按钮不会出现在 **Preview** 窗格中。

   ```
   ...
   
   <TextView
       android:id="@+id/subtotal" ... />
   
   <Button
       android:id="@+id/cancel_button"
       android:layout_width="0dp"
       android:layout_height="wrap_content"
       android:text="@string/cancel"
       app:layout_constraintEnd_toStartOf="@id/next_button"
       app:layout_constraintStart_toStartOf="parent"
       app:layout_constraintTop_toTopOf="@id/next_button" />
   
   <Button
       android:id="@+id/next_button" ... />
   
   ...
   ```

4. 在 `fragment_flavor.xml` 中，您还需要将 **Next** 按钮的起始约束条件从 `app:layout_constraintStart_toStartOf="parent`" 更改为 `app:layout_constraintStart_toEndOf="@id/cancel_button"`。此外，还要在 **Cancel** 按钮上添加一个末端外边距，以便在两个按钮之间留出一些空白。现在，Android Studio 的 **Preview** 窗格中会显示 **Cancel** 按钮。

   ```
   ...
   
   <Button
       android:id="@+id/cancel_button"
       android:layout_marginEnd="@dimen/side_margin" ... />
   
   <Button
       android:id="@+id/next_button"
       app:layout_constraintStart_toEndOf="@id/cancel_button"... />
   
   ...
   ```

5. 就外观样式而言，使用 [Material Outlined Button](https://material.io/components/buttons/android#outlined-button) 样式（具有属性 `style="?attr/materialButtonOutlinedStyle"`），这样，**Cancel** 按钮就不会像 **Next** 按钮一样突出显示，后者是您希望用户关注的主要操作。

   ```
   <Button
       android:id="@+id/cancel_button"
       style="?attr/materialButtonOutlinedStyle" ... />
   ```

   现在，按钮及其位置看起来都很合适！

   ![1fb41763cc255c05.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/1fb41763cc255c05.png)

6. 以同样的方式，向 `fragment_pickup.xml` 布局文件添加一个 **Cancel** 按钮。同时更新 **Next** 按钮的起始约束条件。然后，预览中将显示 **Cancel** 按钮。

   ```
   ...
   
   <TextView
       android:id="@+id/subtotal" ... />
   
   <Button
       android:id="@+id/cancel_button"
       style="?attr/materialButtonOutlinedStyle"
       android:layout_width="0dp"
       android:layout_height="wrap_content"
       android:layout_marginEnd="@dimen/side_margin"
       android:text="@string/cancel"
       app:layout_constraintEnd_toStartOf="@id/next_button"
       app:layout_constraintStart_toStartOf="parent"
       app:layout_constraintTop_toTopOf="@id/next_button" />
   
   <Button
       android:id="@+id/next_button"
       app:layout_constraintStart_toEndOf="@id/cancel_button" ... />
   
   ...
   ```

7. 对 `fragment_summary.xml` 文件应用类似的更改，但此 fragment 的布局略有不同。您将在父类别 `LinearLayout` 的 **Send** 按钮下添加 **Cancel** 按钮，并在两按钮之间添加一定的外边距。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/741c0f034397795c.png" alt="741c0f034397795c.png" style="zoom:33%;" />

   ```
   ...
   
       <Button
           android:id="@+id/send_button" ... />
   
       <Button
           android:id="@+id/cancel_button"
           style="?attr/materialButtonOutlinedStyle"
           android:layout_width="match_parent"
           android:layout_height="wrap_content"
           android:layout_marginTop="@dimen/margin_between_elements"
           android:text="@string/cancel" />
   
   </LinearLayout>
   ```

8. 运行并测试应用。现在，您应该会在 `FlavorFragment`、`PickupFragment` 和 `SummaryFragment` 的布局中看到 **Cancel** 按钮。不过，点按该按钮不会执行任何操作。在下一步中为这些按钮设置点击监听器。



##### 添加“Cancel”按钮点击监听器

在每个 fragment 类（`StartFragment` 除外）中，添加一个支持在用户点击 **Cancel** 按钮时处理的辅助方法。

1. 将此 `cancelOrder()` 方法添加到 `FlavorFragment`。显示口味选项时，如果用户决定取消订单，请通过调用 `sharedViewModel.resetOrder().` 来清除视图模型。然后使用 ID 为 `R.id.action_flavorFragment_to_startFragment.` 的导航操作导航回 `StartFragment`。

   ```
   fun cancelOrder() {    sharedViewModel.resetOrder()    findNavController().navigate(R.id.action_flavorFragment_to_startFragment)}
   ```

   如果您发现与操作资源 ID 相关的错误，则可能需要返回 `nav_graph.xml` 文件来验证您的导航操作是否也被命名为同一名称 (`action_flavorFragment_to_startFragment`)。

2. 使用监听器绑定在 `fragment_flavor.xml` 布局中的 **Cancel** 按钮上设置点击监听器。点击此按钮将会调用您刚刚在 `FragmentFlavor` 类中创建的 `cancelOrder()` 方法。

   ```
   <Button    android:id="@+id/cancel_button"    android:onClick="@{() -> flavorFragment.cancelOrder()}" ... />
   ```

3. 对 `PickupFragment` 重复上述过程。向 fragment 类添加 `cancelOrder()` 方法，此举会重置订单，并从 `PickupFragment` 导航到 `StartFragment`。并在 `fragment_pickup.xml` 中，对 **Cancel** 按钮设置点击监听器，以便在点击该按钮后调用 `cancelOrder()` 方法。

   ```
   fun cancelOrder() {
       sharedViewModel.resetOrder()
       findNavController().navigate(R.id.action_pickupFragment_to_startFragment)
   }
   ```

   ```
   <Button
       android:id="@+id/cancel_button"
       android:onClick="@{() -> pickupFragment.cancelOrder()}" ... />
   ```

4. 为 `SummaryFragment` 中的 **Cancel** 按钮添加类似的代码，以便用户返回 `StartFragment`。如果系统未自动为您导入 `androidx.navigation.fragment.findNavController`，则您需要手动导入。并在 `fragment_summary.xml` 中，点击 **Cancel** 按钮时，调用 `SummaryFragment` 的 `cancelOrder()` 方法。

   ```
   fun cancelOrder() {
       sharedViewModel.resetOrder()
       findNavController().navigate(R.id.action_summaryFragment_to_startFragment)
   }
   ```

   ```
   <Button
       android:id="@+id/cancel_button"
       android:onClick="@{() -> summaryFragment.cancelOrder()}" ... />
   ```

5. 运行并测试应用以验证您刚刚添加到每个 fragment 的逻辑。创建纸杯蛋糕订单后，点按 `FlavorFragment`、`PickupFragment` 或 `SummaryFragment` 中的 **Cancel** 按钮即可返回 `StartFragment`。在创建新订单时，您会注意到之前订单中的信息已清除。

   这看起来运行正常，但返回到 `StartFragment` 后，实际上存在一个向后导航错误。执行下面几个步骤重现错误。

6. 浏览创建新纸杯蛋糕订单的订单流程，直到到达摘要屏幕。例如，您可以订购 12 个巧克力口味的纸杯蛋糕，然后选择未来的提货日期。

7. 然后点按 **Cancel**。您将回到 `StartFragment`。

8. 这看起来没问题，但如果您点按了系统自带的 **Back** 按钮，您最终将返回到订单摘要屏幕，其中将显示订单摘要：订购了 0 个纸杯蛋糕，未选择任何口味。此摘要是不正确的，不应向用户显示。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/1a9024cd58a0e643.png" alt="1a9024cd58a0e643.png" style="zoom:33%;" />

   用户可能不希望重复执行订单流程。此外，视图模型中的所有订单数据都已清除，因此此信息没有用。在这种情况下，点按 `StartFragment` 中的 **Back** 按钮将离开 **Cupcake** 应用。

   让我们一起看一下返回堆栈目前的外观，并了解一下如何修复该错误。当您通过订单摘要屏幕创建订单时，每个目的地均会推送到返回堆栈。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/fc88100cdf1bdd1.png" alt="fc88100cdf1bdd1.png" style="zoom: 50%;" />

   您从 `SummaryFragment` 中取消了此订单。当您通过操作从 `SummaryFragment` 导航到 `StartFragment` 时，Android 在返回堆栈中添加了另一个 `StartFragment` 实例作为新的目的地。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/5616cb0028b63602.png" alt="5616cb0028b63602.png" style="zoom:33%;" />

   因此，如果您点按 `StartFragment` 中的 **Back** 按钮，应用最终将重新显示 `SummaryFragment`（包含空白订单信息）。

   如需解决此导航错误，请了解如何使用 Navigation 组件在使用操作进行导航时从返回堆栈中弹出其他目的地。



#### 从返回堆栈中弹出其他目的地

##### 导航操作：popUpTo 属性

在导航图的导航操作中添加 `app:popUpTo` 属性后，多个目的地可以从返回堆栈中弹出，直至达到指定的目的地为止。如果您指定 `app:popUpTo="@id/startFragment"`，那么在到达 `StartFragment` 之前，返回堆栈中的目的地将被弹出，而 StartFragment 将继续保留在堆栈中。

将此更改添加到您的代码中并运行应用后，您会发现，当取消订单时，您将回到 `StartFragment`。但这时，当您从 `StartFragment` 中点按 **Back** 按钮时，会再次看到 `StartFragment`（而不是退出应用）。这也不是期望出现的行为。如前所述，由于您正在导航到 `StartFragment`，Android 实际上会在返回堆栈中添加 `StartFragment` 作为新目的地，因此现在您可以在返回堆栈上有 2 个 StartFragment 实例。因此，您需要点按两次 **Back** 按钮才能退出应用。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/dd0fedc6e231e595.png" alt="dd0fedc6e231e595.png" style="zoom: 33%;" />

##### 导航操作：popUpToInclusive 属性

如需修复这一新错误，须请求将所有目的地都从返回堆栈中弹出，包含 `StartFragment`。您可以通过在合适的导航操作上指定 `app:popUpTo="@id/startFragment"` 和

`app:popUpToInclusive="true"` 来修复该错误。这样，在返回堆栈中您就只会有一个新的 `StartFragment` 实例。然后从 `StartFragment` 点按 **Back** 按钮一次即可退出该应用。让我们现在就执行这一更改吧。

<img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/cf0e80b4907d80dd.png" alt="cf0e80b4907d80dd.png" style="zoom:50%;" />

##### 修改导航操作

1. 打开 **res > navigation > nav_graph.xml** 文件，转到 **Navigation Editor**。

2. 选择从 `summaryFragment` 到 `startFragment` 的操作，以便以蓝色突出显示。

3. 展开右侧的 **Attributes**（如果尚未打开）。在您可以修改的属性列表中查找 **Pop Behavior**。

   ![d762df0f167efd3a.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/d762df0f167efd3a.png)

4. 在下拉列表选项中，将 **popUpTo** 设置为 `startFragment`。这意味着，返回堆栈中的所有目的地都将弹出（从堆栈顶部开始，然后向下），一直到 `startFragment`。

5. 然后点击 **popUpToInclusive** 复选框，直到屏幕上显示对勾标记并标记为 **true**。这表示您要弹出最多的目的地，并包含返回堆栈中已存在的 `startFragment` 实例。这样，返回堆栈中就不会有两个 `startFragment` 实例。

   ![4a403838a62ff487.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/4a403838a62ff487.png)

6. 对将 `pickupFragment` 和 `flavorFragment` 连接到 `startFragment` 的操作重复执行这些更改。

7. 完成后，查看导航图文件的 **Code** 视图，确认您对应用进行了正确的更改。

   ```
   <navigation
       android:id="@+id/nav_graph" ...>
       <fragment
           android:id="@+id/startFragment" ...>
           ...
       </fragment>
       <fragment
           android:id="@+id/flavorFragment" ...>
           ...
           <action
               android:id="@+id/action_flavorFragment_to_startFragment"
               app:destination="@id/startFragment"
               app:popUpTo="@id/startFragment"
               app:popUpToInclusive="true" />
       </fragment>
       <fragment
           android:id="@+id/pickupFragment" ...>
           ...
           <action
               android:id="@+id/action_pickupFragment_to_startFragment"
               app:destination="@id/startFragment"
               app:popUpTo="@id/startFragment"
               app:popUpToInclusive="true" />
       </fragment>
       <fragment
           android:id="@+id/summaryFragment" ...>
           <action
               android:id="@+id/action_summaryFragment_to_startFragment"
               app:destination="@id/startFragment"
               app:popUpTo="@id/startFragment"
               app:popUpToInclusive="true" />
       </fragment>
   </navigation>
   ```

   请注意，这 3 项操作（`action_flavorFragment_to_startFragment`、`action_pickupFragment_to_startFragment` 和 `action_summaryFragment_to_startFragment`）应该都新增了属性 `app:popUpTo="@id/startFragment"` 和 `app:popUpToInclusive="true"`。

8. 现在运行该应用。浏览订单流程，然后点按 **Cancel**。当您返回到 `StartFragment` 时，点按 **Back** 按钮（仅按一次！），您将退出应用。

   下面将简要概述发生了什么，当您取消订单并返回到应用的第一个屏幕时，返回堆栈中的所有 fragment 目的地都将弹出堆栈，包括 `StartFragment` 的第一个实例。完成导航操作后，在返回堆栈中会添加 `StartFragment` 作为新目的地。点按 **Back** 会将 `StartFragment` 弹出堆栈，而不会在返回堆栈中留下任何 fragment。因此，Android 会完成 activity，用户也将离开应用。

   该应用的外观应如下所示：

   ![5bf939ab1255fb0d.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/5bf939ab1255fb0d.png)



### ③发送订单

目前，该应用看起来很棒！只缺少一个部分。当您点按 `SummaryFragment` 上的“Send Order”按钮时，系统仍然会弹出 `Toast` 消息。

![90ed727c7b812fd6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/90ed727c7b812fd6.png)

如果可以从应用中发送订单，该体验将十分实用。充分利用您在之前的 Codelab 中学到的知识，了解如何利用隐式 intent  将应用中的信息分享到其他应用。这样，用户就可以使用设备上的电子邮件应用分享纸杯蛋糕订单信息，从而将订单通过电子邮件发送到纸杯蛋糕店。

![170d76b64ce78f56.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/170d76b64ce78f56.png)

如需实现此功能，请查看上方屏幕截图中电子邮件主题和电子邮件正文的结构。

您将使用 `strings.xml` 文件中已有的字符串。

```
<string name="new_cupcake_order">New Cupcake Order</string>
<string name="order_details">Quantity: %1$s cupcakes \n Flavor: %2$s \nPickup date: %3$s \n Total: %4$s \n\n Thank you!</string>
```

`order_details` 是包含 4 种不同格式参数的字符串资源，这些参数是纸杯蛋糕实际数量、期望的口味、期望提货日期和总价的占位符。参数的编号为 1 到 4，语法为 `%1` 到 `%4`。系统也指定了参数类型（`$s` 表示此处需要字符串）。

在 Kotlin 代码中，您将能够对 `R.string.order_details` 调用 `getString()`，后接 4 个参数（顺序很重要！）。例如，调用 `getString(R.string.order_details, "12", "Chocolate", "Sat Dec 12", "$24.00")` 可创建以下字符串，该字符串是您需要的电子邮件正文。

```
Quantity: 12 cupcakes
Flavor: Chocolate
Pickup date: Sat Dec 12
Total: $24.00

Thank you!
```

**注意**：您可能还记得，您已了解包含格式参数的字符串资源。例如，您在应用中使用的小计和总价字符串将声明为

```
<string name="subtotal_price">Subtotal %s</string>
<string name="total_price">Total %s</string>
```

其中 `%s` 是格式化的价格字符串的占位符。

1. 在 `SummaryFragment.kt` 中，修改 `sendOrder()` 方法。移除现有的 `Toast` 消息。

2. 在 `sendOrder()` 方法中，构建订单摘要文本。获取共享视图模型中的订单数量、口味、日期和价格，然后创建格式化的 `order_details` 字符串。

   ```
   val orderSummary = getString(
       R.string.order_details,
       sharedViewModel.quantity.value.toString(),
       sharedViewModel.flavor.value.toString(),
       sharedViewModel.date.value.toString(),
       sharedViewModel.price.value.toString()
   )
   ```

3. 在 `sendOrder()` 方法中，创建一个隐式 intent，以将订单分享给其他应用。如需了解如何创建电子邮件 intent，请参阅[文档](https://developer.android.com/guide/components/intents-common#Email)。为 intent 操作指定 `Intent.ACTION_SEND`，将类型设置为 `"text/plain"`，并包含电子邮件主题 (`Intent.EXTRA_SUBJECT`) 和电子邮件正文 (`Intent.EXTRA_TEXT`) 的 intent extra。如果需要，导入 `android.content.Intent`。

   ```
   val intent = Intent(Intent.ACTION_SEND)
       .setType("text/plain")
       .putExtra(Intent.EXTRA_SUBJECT, getString(R.string.new_cupcake_order))
       .putExtra(Intent.EXTRA_TEXT, orderSummary)
   ```

   额外提示：如果您自行调整此应用以适应您自己的用例，则可以预先填充电子邮件的收件人，作为纸杯蛋糕店的电子邮件地址。在 intent 中，您需要使用 intent extra [`Intent.EXTRA_EMAIL`](https://developer.android.com/reference/android/content/Intent#EXTRA_EMAIL) 指定电子邮件收件人。

4. 由于这是隐式 intent，因此您无需提前了解具体由哪个组件或应用处理此 intent。用户将决定要使用哪个应用来处理  intent。不过，在使用该 intent 启动 activity 之前，请检查是否有应用能够处理该 intent。如果没有可用的应用来处理  intent，执行该项检查可防止 **Cupcake** 应用崩溃，从而提升代码的安全性。

   ```
   if (activity?.packageManager?.resolveActivity(intent, 0) != null) {
       startActivity(intent)
   }
   ```

   通过访问 [`PackageManager`](https://developer.android.com/reference/android/content/pm/PackageManager) 来执行该项检查，PackageManager 中说明了设备上安装了哪些应用软件包。`PackageManager` 可通过 fragment 的 `activity` 访问，前提是 `activity` 和 `packageManager` 均不为 null。使用您创建的 intent 调用 `PackageManager` 的 `resolveActivity()` 方法。如果结果不为 null，就可以放心使用您的 intent 来调用 `startActivity()`。

   

5. 运行您的应用以测试代码。创建纸杯蛋糕订单，然后点按 **Send Order to Another App**。当共享对话框弹出时，您可以选择 Gmail 应用，但如果您愿意，也可以选择其他应用。如果您选择 Gmail  应用，则可能需要在设备上设置一个帐号（如果您尚未设置帐号），例如，在您使用模拟器的情况下。如果电子邮件正文中未显示您的最新纸杯蛋糕订单，则可能需要先舍弃当前的电子邮件草稿。

   ![170d76b64ce78f56.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/170d76b64ce78f56.png)

   在测试不同场景时，如果您只订购 1 个纸杯蛋糕，可能会出现错误。订单摘要显示 **1 cupcakes**，但在英语中，这种说法存在语法错误。

   ![ef046a100381bb07.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/ef046a100381bb07.png)

   正确说法应为 **1 cupcake**（不使用复数）。如果您想根据数量值选择是使用“cupcake”还是“cupcakes”，则可以使用 Android 中的[数量字符串](https://developer.android.com/guide/topics/resources/string-resource#Plurals)。通过声明 `plurals` 资源，您可以根据具体数量指定要使用的不同字符串资源，例如采用单数或复数形式。

6. 在 `strings.xml` 文件中添加一个 `cupcakes` 复数资源。

   ```
   <plurals name="cupcakes">
       <item quantity="one">%d cupcake</item>
       <item quantity="other">%d cupcakes</item>
   </plurals>
   ```

   在单数情况 (`quantity="one"`) 下，将使用单数形式的字符串。在所有其他情况 (`quantity="other"`) 下，将使用复数形式的字符串。请注意，与需要字符串参数的 `%s` 不同，`%d` 需要的是整数参数，您将在格式化字符串时传入该整数参数。

   在您的 Kotlin 代码中，调用

   ```
   getQuantityString(R.string.cupcakes, 1, 1)` 将返回字符串 `1 cupcake
   getQuantityString(R.string.cupcakes, 6, 6)` 将返回字符串 `6 cupcakes
   getQuantityString(R.string.cupcakes, 0, 0)` 将返回字符串 `0 cupcakes
   ```

   **注意**：调用 `getQuantityString()` 时，您需要传入两次数量，因为第一个数量参数将用于选择正确的复数形式字符串。第二个数量参数用于实际字符串资源的 `%d` 占位符。

7. 在转到您的 Kotlin 代码之前，请更新 `strings.xml` 中的 `order_details` 字符串资源，这样复数形式的 **cupcakes** 就不会再硬编码到代码中。

   ```
   <string name="order_details">Quantity: %1$s \n Flavor: %2$s \nPickup date: %3$s \n
           Total: %4$s \n\n Thank you!</string>
   ```

8. 在 `SummaryFragment` 类中，更新 `sendOrder()` 方法以使用新的数量字符串。最简单的方法是首先从视图模型中计算出数量，然后将其存储在变量中。由于视图模型中的 `quantity` 的类型为 `LiveData<Int>`，因此 `sharedViewModel.quantity.value` 可能为 null。如果该值为 null，使用 `0` 作为 `numberOfCupcakes` 的默认值。

   ```
   val numberOfCupcakes = sharedViewModel.quantity.value ?: 0
   ```

   [Elvis 运算符](https://kotlinlang.org/docs/reference/null-safety.html#elvis-operator) (?:) 表示如果左侧的表达式不为 null，则使用该表达式。但如果左侧的表达式为 null，请使用 Elvis 运算符右侧的表达式（在本例中为 `0`）

9. 然后，像之前一样格式化 `order_details` 字符串。使用 `resources.getQuantityString(R.plurals.cupcakes, numberOfCupcakes, numberOfCupcakes)` 创建格式化的纸杯蛋糕字符串，而不是直接传入 `numberOfCupcakes` 作为数量参数。

   完整的 `sendOrder()` 方法应如下所示：

   ```
   fun sendOrder() {
       val numberOfCupcakes = sharedViewModel.quantity.value ?: 0
       val orderSummary = getString(
           R.string.order_details,
           resources.getQuantityString(R.plurals.cupcakes, numberOfCupcakes, numberOfCupcakes),
           sharedViewModel.flavor.value.toString(),
           sharedViewModel.date.value.toString(),
           sharedViewModel.price.value.toString()
       )
   
       val intent = Intent(Intent.ACTION_SEND)
           .setType("text/plain")
           .putExtra(Intent.EXTRA_SUBJECT, getString(R.string.new_cupcake_order))
           .putExtra(Intent.EXTRA_TEXT, orderSummary)
   
       if (activity?.packageManager?.resolveActivity(intent, 0) != null) {
           startActivity(intent)
       }
   }
   ```

10. 运行并测试您的代码。检查电子邮件正文中的订单摘要显示 1 cupcake、6 cupcakes 或 12 cupcakes。

    至此，您已经完成了 Cupcake 应用的全部功能！恭喜！构建该应用无疑是一个极具挑战性的任务，但这也使您在成为 Android 开发者的道路上取得了巨大的进步！现在，您将能够成功将到目前为止学到的所有概念相结合，并在此过程中学到一些新的问题解决技巧。



### ④剩下的步骤

现在请花些时间清理代码，这是练习您从之前的 Codelab 中学到的良好编码做法的好机会。

- 优化导入
- 重新格式化文件
- 移除不使用或被注释掉的代码
- 根据需要在代码中添加注释

如需提升您的应用的无障碍使用性，请在启用 [Talkback](https://developer.android.com/guide/topics/ui/accessibility/testing#explore_your_app_with_talkback) 的情况下测试您的应用，以确保用户体验顺畅。在适当情况下，语音反馈有助于传达屏幕上各种元素的用途。此外，还要确保应用的所有元素都可使用滑动手势进行导航。

请仔细检查您实现的用例，确保它们在您的最终应用中发挥预期的作用。示例：

- 将在设备旋转时保留数据（得益于视图模型）。
- 如果您点按 **Up** 或 **Back** 按钮，订单信息应该仍然可以在 `FlavorFragment` 和 `PickupFragment` 上正确显示。
- 将订单发送到另一个应用将分享正确的订单详情。
- 取消订单将清除订单中的所有信息。

如果您发现任何错误，请立即修复。

复核工作做得不错！

