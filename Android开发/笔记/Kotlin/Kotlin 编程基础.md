
# 课程大纲
本课程旨在以基础水平介绍 Kotlin 编程语言。您将练习和扩展任何语言都必不可少的编程基础知识，以及 Kotlin 语法的独特之处。每个模块都旨在为您提供理解 Kotlin 编程语言所需的知识和技能。
在本课程中，您将探索以下内容。
### 模块 1：Kotlin 编程入门
在第一个模块中，您将首先概述 Kotlin 编程。一旦您对 Kotlin 的职业和用途更加熟悉，您将继续学习 Kotlin 编程，探索和了解支撑 Kotlin 编程语言的基本概念。
完成本模块后，您将能够：
- 描述基本类型和变量
- 解释 Kotlin 中的数字
- 解释条件语句是什么
- 描述如何使用循环
### 模块 2：函数、类和对象
在接下来的模块中，您将学习函数、类和对象。您将更深入地了解函数以及程序是如何由函数构建的。您还将学习如何在编写代码时使用类、对象和类型。
完成本模块后，您将能够：
- 解释函数的概念
- 区分参数和参数值
- 解释函数可以返回值的概念，并描述其工作原理
- 解释类、对象和类型之间的区别
- 区分不同的可见性修饰符
### 模块 3：高级类和对象
在本模块中，您将进一步学习 Kotlin 中的高级类和对象。您将学习 List、Set 和 Map 以及在 Kotlin 编写代码时如何使用这些集合。您还将学习何时使用这些集合。
完成本模块后，您将能够：
- 描述在编程中使用集合的用途
- 确定在任何给定情况下使用哪种集合类型
- 解释 List、Set 和 Map 之间的区别
### 模块 4：评估考核
在最后一个模块中，您将学习评估考核。在完成本模块中的单元后，您将综合运用课程中所学的技能，为银行账户项目编写代码。
您还将有机会反思课程内容和未来的学习路径。


# Kotlin Playgrounds
在本篇阅读中，您将了解 Kotlin Playgrounds，这是一个用于运行 Kotlin 代码的在线编辑器。


## 基础数据类型
````tab
tab:Kotlin
```
fun main() {  
    // 整数类型  
    val intNumber: Int = 10  
    val longNumber: Long = 1000000000L  
  
    // 浮点数类型  
    val floatNumber: Float = 3.14f  
    val doubleNumber: Double = 2.71828  
  
    // 布尔类型  
    val isTrue: Boolean = true  
    val isFalse: Boolean = false  
  
    // 字符类型  
    val char: Char = 'A'  
  
    // 字符串类型  
    val string: String = "Hello, Kotlin!"  
  
    // 数组类型  
    val intArray: IntArray = intArrayOf(1, 2, 3, 4, 5)  
    val stringArray: Array<String> = arrayOf("apple", "banana", "cherry")  
  
    // 列表类型  
    val intList: List<Int> = listOf(1, 2, 3, 4, 5)  
    val stringList: MutableList<String> = mutableListOf("apple", "banana", "cherry")  
  
    // 显示输出各种类型的值  
    println("整数类型: $intNumber, $longNumber")  
    println("浮点数类型: $floatNumber, $doubleNumber")  
    println("布尔类型: $isTrue, $isFalse")  
    println("字符类型: $char")  
    println("字符串类型: $string")  
    println("数组类型: ${intArray.joinToString()}")  
    println("数组类型: ${stringArray.joinToString()}")  
    println("列表类型: $intList, $stringList")  
  
    val intArray2: IntArray = intArrayOf(1, 2, 3, 4, 5)  
    val firstItem = intArray2[0]  
    println("数组的第一项是: ${intArray2[0]}")  
  
  
    val name = "Alice"  
    val age = 30  
  
// 下面的代码将会导致编译错误，因为name是不可变的  
// name = "Bob"  
  
  
    var count = 10  
  
    count = 20 // 可以重新赋值  
  
// 也可以在后续的代码中修改它的值  
    if (count > 5) {  
        count += 1  
    }  
  
}
```
````

![[Pasted image 20231112155411.png]]


## 输入与输出

````tab
tab:Kotlin
```
fun main() {  
    println("请输入一个整数：")  
    val userInput = readlnOrNull()  
  
    try {  
        val number = userInput?.toInt()  
        if (number != null) {  
            println("你输入的整数是：$number")  
        } else {  
            println("输入不是一个有效的整数")  
        }  
    } catch (e: NumberFormatException) {  
        println("输入不是一个有效的整数")  
    }  
}
```
````

![[Pasted image 20231112155437.png]]
![[Pasted image 20231112155456.png]]
