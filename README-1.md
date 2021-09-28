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
class MainActivity : AppCompatActivity() {   override fun onCreate(savedInstanceState: Bundle?) {       super.onCreate(savedInstanceState)       setContentView(R.layout.main_activity)   }}
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
   orderOneCupcake.setOnClickListener { orderCupcake(1) }orderSixCupcakes.setOnClickListener { orderCupcake(6) }orderTwelveCupcakes.setOnClickListener { orderCupcake(12) }
   ```

3. 在 `orderCupcake()` 方法中，将用于显示消息框消息的代码替换为用于导航到口味 fragment 的代码。使用 `findNavController()` 方法获取 `NavController` 并对其调用 `navigate()`，且传入操作 ID `R.id.action_startFragment_to_flavorFragment`。确保此操作 ID 与 `nav_graph.xml.` 中声明的操作匹配。

   将以下代码

   ```
   fun orderCupcake(quantity: Int) {    Toast.makeText(activity, "Ordered $quantity cupcake(s)", Toast.LENGTH_SHORT).show()}
   ```

   替换为下面的代码：

   ```
   fun orderCupcake(quantity: Int) {   findNavController().navigate(R.id.action_startFragment_to_flavorFragment)}
   ```

4. 添加导入代码 `import` `androidx.navigation.fragment.findNavController`，或者您也可以从 Android Studio 提供的选项中进行选择。

   ![2a087f53a77765a6.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/2a087f53a77765a6.png)

#### 向口味 fragment 和取货 fragment 添加导航

与前面的任务类似，在此任务中，您将向其他 fragment（即口味 fragment 和取货 fragment）添加导航。

![3b351067bf4926b7.png](https://developer.android.com/codelabs/basic-android-kotlin-training-shared-viewmodel/img/3b351067bf4926b7.png)

1. 依次打开 **app > java > com.example.cupcake > FlavorFragment.kt**。请注意，在 **Next** 按钮点击监听器中调用的方法是 `goToNextScreen()` 方法。

2. 在 `FlavorFragment.kt` 中的 `goToNextScreen()` 方法内，替换用于显示消息框的代码以导航到取货 fragment。使用操作 ID `R.id.action_flavorFragment_to_pickupFragmen`，并确保此 ID 与 `nav_graph.xml.` 中声明的操作匹配。

   ```
   fun goToNextScreen() {    findNavController().navigate(R.id.action_flavorFragment_to_pickupFragment)}
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
   class MainActivity : AppCompatActivity(R.layout.activity_main) {    override fun onCreate(savedInstanceState: Bundle?) {        super.onCreate(savedInstanceState)        val navHostFragment = supportFragmentManager                .findFragmentById(R.id.nav_host_fragment) as NavHostFragment        val navController = navHostFragment.navController        setupActionBarWithNavController(navController)    }}
   ```

3. 当 Android Studio 提示时，添加必要的导入代码。

   ```
   import android.os.Bundleimport androidx.navigation.fragment.NavHostFragmentimport androidx.navigation.ui.setupActionBarWithNavController
   ```

4. 为每个 fragment 设置应用栏标题。打开 `navigataion/nav_graph.xml` 并切换到 **Code** 标签页。

5. 在 `nav_graph.xml` 中，修改每个 fragment 目的地的 `android:label` 属性。使用起始应用中已声明的以下字符串资源。

   对于起始 fragment，使用 `@string/app_name`，值为 `Cupcake`。

   对于口味 fragment，使用 `@string/choose_flavor`，值为 `Choose Flavor`。

   对于取货 fragment，使用 `@string/choose_pickup_date`，值为 `Choose Pickup Date`。

   对于摘要 fragment，使用 `@string/order_summary`，值为 `Order Summary`。

   ```
   <navigation ...>    <fragment        android:id="@+id/startFragment"        ...        android:label="@string/app_name" ... >        <action ... />    </fragment>    <fragment        android:id="@+id/flavorFragment"        ...        android:label="@string/choose_flavor" ... >        <action ... />    </fragment>    <fragment        android:id="@+id/pickupFragment"        ...        android:label="@string/choose_pickup_date" ... >        <action ... />    </fragment>    <fragment        android:id="@+id/summaryFragment"        ...        android:label="@string/order_summary" ... /></navigation>
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
   import androidx.lifecycle.ViewModelclass OrderViewModel : ViewModel() {}
   ```

5. 在 `OrderViewModel` 类内，将上述属性添加为 `private` `val`。

6. 将属性类型更改为 `LiveData` 并向属性添加后备字段，这样这些属性就可观察，当视图模型中的源数据发生变化时，界面就会更新。

   ```
   private val _quantity = MutableLiveData<Int>(0)val quantity: LiveData<Int> = _quantityprivate val _flavor = MutableLiveData<String>("")val flavor: LiveData<String> = _flavorprivate val _date = MutableLiveData<String>("")val date: LiveData<String> = _dateprivate val _price = MutableLiveData<Double>(0.0)val price: LiveData<Double> = _price
   ```

   您需要导入以下类：

   ```
   import androidx.lifecycle.LiveDataimport androidx.lifecycle.MutableLiveData
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
   <Button    android:id="@+id/next_button"    android:onClick="@{() -> pickupFragment.goToNextScreen()}"    ... />
   ```

   在 `fragment_summary.xml` 中：

   ```
   <Button    android:id="@+id/send_button"    android:onClick="@{() -> summaryFragment.sendOrder()}"    ...>
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
   class MainActivity : AppCompatActivity(R.layout.activity_main) {    private lateinit var navController: NavController    override fun onCreate(savedInstanceState: Bundle?) {        super.onCreate(savedInstanceState)        val navHostFragment = supportFragmentManager                .findFragmentById(R.id.nav_host_fragment) as NavHostFragment        navController = navHostFragment.navController        setupActionBarWithNavController(navController)    }}
   ```

2. 在同一类中，添加代码以替换 `onSupportNavigateUp()` 函数。此代码将要求 `navController` 处理应用中的向上导航。否则，回退到处理 **Up** 按钮的超类实现（在 `AppCompatActivity` 中）。

   ```
   override fun onSupportNavigateUp(): Boolean {   return navController.navigateUp() || super.onSupportNavigateUp()}
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
   ...<TextView    android:id="@+id/subtotal" ... /><Button    android:id="@+id/cancel_button"    android:layout_width="0dp"    android:layout_height="wrap_content"    android:text="@string/cancel"    app:layout_constraintEnd_toStartOf="@id/next_button"    app:layout_constraintStart_toStartOf="parent"    app:layout_constraintTop_toTopOf="@id/next_button" /><Button    android:id="@+id/next_button" ... />...
   ```

4. 在 `fragment_flavor.xml` 中，您还需要将 **Next** 按钮的起始约束条件从 `app:layout_constraintStart_toStartOf="parent`" 更改为 `app:layout_constraintStart_toEndOf="@id/cancel_button"`。此外，还要在 **Cancel** 按钮上添加一个末端外边距，以便在两个按钮之间留出一些空白。现在，Android Studio 的 **Preview** 窗格中会显示 **Cancel** 按钮。

   ```
   ...<Button    android:id="@+id/cancel_button"    android:layout_marginEnd="@dimen/side_margin" ... /><Button    android:id="@+id/next_button"    app:layout_constraintStart_toEndOf="@id/cancel_button"... />...
   ```

5. 就外观样式而言，使用 [Material Outlined Button](https://material.io/components/buttons/android#outlined-button) 样式（具有属性 `style="?attr/materialButtonOutlinedStyle"`），这样，**Cancel** 按钮就不会像 **Next** 按钮一样突出显示，后者是您希望用户关注的主要操作。

   ```
   <Button    android:id="@+id/cancel_button"    style="?attr/materialButtonOutlinedStyle" ... />
   ```

   现在，按钮及其位置看起来都很合适！

   ![1fb41763cc255c05.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/1fb41763cc255c05.png)

6. 以同样的方式，向 `fragment_pickup.xml` 布局文件添加一个 **Cancel** 按钮。同时更新 **Next** 按钮的起始约束条件。然后，预览中将显示 **Cancel** 按钮。

   ```
   ...<TextView    android:id="@+id/subtotal" ... /><Button    android:id="@+id/cancel_button"    style="?attr/materialButtonOutlinedStyle"    android:layout_width="0dp"    android:layout_height="wrap_content"    android:layout_marginEnd="@dimen/side_margin"    android:text="@string/cancel"    app:layout_constraintEnd_toStartOf="@id/next_button"    app:layout_constraintStart_toStartOf="parent"    app:layout_constraintTop_toTopOf="@id/next_button" /><Button    android:id="@+id/next_button"    app:layout_constraintStart_toEndOf="@id/cancel_button" ... />...
   ```

7. 对 `fragment_summary.xml` 文件应用类似的更改，但此 fragment 的布局略有不同。您将在父类别 `LinearLayout` 的 **Send** 按钮下添加 **Cancel** 按钮，并在两按钮之间添加一定的外边距。

   <img src="https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/741c0f034397795c.png" alt="741c0f034397795c.png" style="zoom:33%;" />

   ```
   ...    <Button        android:id="@+id/send_button" ... />    <Button        android:id="@+id/cancel_button"        style="?attr/materialButtonOutlinedStyle"        android:layout_width="match_parent"        android:layout_height="wrap_content"        android:layout_marginTop="@dimen/margin_between_elements"        android:text="@string/cancel" /></LinearLayout>
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
   fun cancelOrder() {    sharedViewModel.resetOrder()    findNavController().navigate(R.id.action_pickupFragment_to_startFragment)}
   ```

   ```
   <Button    android:id="@+id/cancel_button"    android:onClick="@{() -> pickupFragment.cancelOrder()}" ... />
   ```

4. 为 `SummaryFragment` 中的 **Cancel** 按钮添加类似的代码，以便用户返回 `StartFragment`。如果系统未自动为您导入 `androidx.navigation.fragment.findNavController`，则您需要手动导入。并在 `fragment_summary.xml` 中，点击 **Cancel** 按钮时，调用 `SummaryFragment` 的 `cancelOrder()` 方法。

   ```
   fun cancelOrder() {    sharedViewModel.resetOrder()    findNavController().navigate(R.id.action_summaryFragment_to_startFragment)}
   ```

   ```
   <Button    android:id="@+id/cancel_button"    android:onClick="@{() -> summaryFragment.cancelOrder()}" ... />
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
   <navigation    android:id="@+id/nav_graph" ...>    <fragment        android:id="@+id/startFragment" ...>        ...    </fragment>    <fragment        android:id="@+id/flavorFragment" ...>        ...        <action            android:id="@+id/action_flavorFragment_to_startFragment"            app:destination="@id/startFragment"            app:popUpTo="@id/startFragment"            app:popUpToInclusive="true" />    </fragment>    <fragment        android:id="@+id/pickupFragment" ...>        ...        <action            android:id="@+id/action_pickupFragment_to_startFragment"            app:destination="@id/startFragment"            app:popUpTo="@id/startFragment"            app:popUpToInclusive="true" />    </fragment>    <fragment        android:id="@+id/summaryFragment" ...>        <action            android:id="@+id/action_summaryFragment_to_startFragment"            app:destination="@id/startFragment"            app:popUpTo="@id/startFragment"            app:popUpToInclusive="true" />    </fragment></navigation>
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
<string name="new_cupcake_order">New Cupcake Order</string><string name="order_details">Quantity: %1$s cupcakes \n Flavor: %2$s \nPickup date: %3$s \n Total: %4$s \n\n Thank you!</string>
```

`order_details` 是包含 4 种不同格式参数的字符串资源，这些参数是纸杯蛋糕实际数量、期望的口味、期望提货日期和总价的占位符。参数的编号为 1 到 4，语法为 `%1` 到 `%4`。系统也指定了参数类型（`$s` 表示此处需要字符串）。

在 Kotlin 代码中，您将能够对 `R.string.order_details` 调用 `getString()`，后接 4 个参数（顺序很重要！）。例如，调用 `getString(R.string.order_details, "12", "Chocolate", "Sat Dec 12", "$24.00")` 可创建以下字符串，该字符串是您需要的电子邮件正文。

```
Quantity: 12 cupcakesFlavor: ChocolatePickup date: Sat Dec 12Total: $24.00Thank you!
```

**注意**：您可能还记得，您已了解包含格式参数的字符串资源。例如，您在应用中使用的小计和总价字符串将声明为

```
<string name="subtotal_price">Subtotal %s</string><string name="total_price">Total %s</string>
```

其中 `%s` 是格式化的价格字符串的占位符。

1. 在 `SummaryFragment.kt` 中，修改 `sendOrder()` 方法。移除现有的 `Toast` 消息。

2. 在 `sendOrder()` 方法中，构建订单摘要文本。获取共享视图模型中的订单数量、口味、日期和价格，然后创建格式化的 `order_details` 字符串。

   ```
   val orderSummary = getString(    R.string.order_details,    sharedViewModel.quantity.value.toString(),    sharedViewModel.flavor.value.toString(),    sharedViewModel.date.value.toString(),    sharedViewModel.price.value.toString())
   ```

3. 在 `sendOrder()` 方法中，创建一个隐式 intent，以将订单分享给其他应用。如需了解如何创建电子邮件 intent，请参阅[文档](https://developer.android.com/guide/components/intents-common#Email)。为 intent 操作指定 `Intent.ACTION_SEND`，将类型设置为 `"text/plain"`，并包含电子邮件主题 (`Intent.EXTRA_SUBJECT`) 和电子邮件正文 (`Intent.EXTRA_TEXT`) 的 intent extra。如果需要，导入 `android.content.Intent`。

   ```
   val intent = Intent(Intent.ACTION_SEND)    .setType("text/plain")    .putExtra(Intent.EXTRA_SUBJECT, getString(R.string.new_cupcake_order))    .putExtra(Intent.EXTRA_TEXT, orderSummary)
   ```

   额外提示：如果您自行调整此应用以适应您自己的用例，则可以预先填充电子邮件的收件人，作为纸杯蛋糕店的电子邮件地址。在 intent 中，您需要使用 intent extra [`Intent.EXTRA_EMAIL`](https://developer.android.com/reference/android/content/Intent#EXTRA_EMAIL) 指定电子邮件收件人。

4. 由于这是隐式 intent，因此您无需提前了解具体由哪个组件或应用处理此 intent。用户将决定要使用哪个应用来处理  intent。不过，在使用该 intent 启动 activity 之前，请检查是否有应用能够处理该 intent。如果没有可用的应用来处理  intent，执行该项检查可防止 **Cupcake** 应用崩溃，从而提升代码的安全性。

   ```
   if (activity?.packageManager?.resolveActivity(intent, 0) != null) {    startActivity(intent)}
   ```

   通过访问 [`PackageManager`](https://developer.android.com/reference/android/content/pm/PackageManager) 来执行该项检查，PackageManager 中说明了设备上安装了哪些应用软件包。`PackageManager` 可通过 fragment 的 `activity` 访问，前提是 `activity` 和 `packageManager` 均不为 null。使用您创建的 intent 调用 `PackageManager` 的 `resolveActivity()` 方法。如果结果不为 null，就可以放心使用您的 intent 来调用 `startActivity()`。

   

5. 运行您的应用以测试代码。创建纸杯蛋糕订单，然后点按 **Send Order to Another App**。当共享对话框弹出时，您可以选择 Gmail 应用，但如果您愿意，也可以选择其他应用。如果您选择 Gmail  应用，则可能需要在设备上设置一个帐号（如果您尚未设置帐号），例如，在您使用模拟器的情况下。如果电子邮件正文中未显示您的最新纸杯蛋糕订单，则可能需要先舍弃当前的电子邮件草稿。

   ![170d76b64ce78f56.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/170d76b64ce78f56.png)

   在测试不同场景时，如果您只订购 1 个纸杯蛋糕，可能会出现错误。订单摘要显示 **1 cupcakes**，但在英语中，这种说法存在语法错误。

   ![ef046a100381bb07.png](https://developer.android.com/codelabs/basic-android-kotlin-training-navigation-backstack/img/ef046a100381bb07.png)

   正确说法应为 **1 cupcake**（不使用复数）。如果您想根据数量值选择是使用“cupcake”还是“cupcakes”，则可以使用 Android 中的[数量字符串](https://developer.android.com/guide/topics/resources/string-resource#Plurals)。通过声明 `plurals` 资源，您可以根据具体数量指定要使用的不同字符串资源，例如采用单数或复数形式。

6. 在 `strings.xml` 文件中添加一个 `cupcakes` 复数资源。

   ```
   <plurals name="cupcakes">    <item quantity="one">%d cupcake</item>    <item quantity="other">%d cupcakes</item></plurals>
   ```

   在单数情况 (`quantity="one"`) 下，将使用单数形式的字符串。在所有其他情况 (`quantity="other"`) 下，将使用复数形式的字符串。请注意，与需要字符串参数的 `%s` 不同，`%d` 需要的是整数参数，您将在格式化字符串时传入该整数参数。

   在您的 Kotlin 代码中，调用

   ```
   getQuantityString(R.string.cupcakes, 1, 1)` 将返回字符串 `1 cupcakegetQuantityString(R.string.cupcakes, 6, 6)` 将返回字符串 `6 cupcakesgetQuantityString(R.string.cupcakes, 0, 0)` 将返回字符串 `0 cupcakes
   ```

   **注意**：调用 `getQuantityString()` 时，您需要传入两次数量，因为第一个数量参数将用于选择正确的复数形式字符串。第二个数量参数用于实际字符串资源的 `%d` 占位符。

7. 在转到您的 Kotlin 代码之前，请更新 `strings.xml` 中的 `order_details` 字符串资源，这样复数形式的 **cupcakes** 就不会再硬编码到代码中。

   ```
   <string name="order_details">Quantity: %1$s \n Flavor: %2$s \nPickup date: %3$s \n        Total: %4$s \n\n Thank you!</string>
   ```

8. 在 `SummaryFragment` 类中，更新 `sendOrder()` 方法以使用新的数量字符串。最简单的方法是首先从视图模型中计算出数量，然后将其存储在变量中。由于视图模型中的 `quantity` 的类型为 `LiveData<Int>`，因此 `sharedViewModel.quantity.value` 可能为 null。如果该值为 null，使用 `0` 作为 `numberOfCupcakes` 的默认值。

   ```
   val numberOfCupcakes = sharedViewModel.quantity.value ?: 0
   ```

   [Elvis 运算符](https://kotlinlang.org/docs/reference/null-safety.html#elvis-operator) (?:) 表示如果左侧的表达式不为 null，则使用该表达式。但如果左侧的表达式为 null，请使用 Elvis 运算符右侧的表达式（在本例中为 `0`）

9. 然后，像之前一样格式化 `order_details` 字符串。使用 `resources.getQuantityString(R.plurals.cupcakes, numberOfCupcakes, numberOfCupcakes)` 创建格式化的纸杯蛋糕字符串，而不是直接传入 `numberOfCupcakes` 作为数量参数。

   完整的 `sendOrder()` 方法应如下所示：

   ```
   fun sendOrder() {    val numberOfCupcakes = sharedViewModel.quantity.value ?: 0    val orderSummary = getString(        R.string.order_details,        resources.getQuantityString(R.plurals.cupcakes, numberOfCupcakes, numberOfCupcakes),        sharedViewModel.flavor.value.toString(),        sharedViewModel.date.value.toString(),        sharedViewModel.price.value.toString()    )    val intent = Intent(Intent.ACTION_SEND)        .setType("text/plain")        .putExtra(Intent.EXTRA_SUBJECT, getString(R.string.new_cupcake_order))        .putExtra(Intent.EXTRA_TEXT, orderSummary)    if (activity?.packageManager?.resolveActivity(intent, 0) != null) {        startActivity(intent)    }}
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

