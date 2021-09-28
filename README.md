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


[三](https://github.com/liuzeminweb/Kotlin_learn/blob/main/README-1.md)
