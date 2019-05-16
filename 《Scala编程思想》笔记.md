# 《Scala编程思想》笔记

<a name="2e82d497"></a>
## 还没写完，不定期更新。
<a name="df368884"></a>
## 前言
这本书主要是Scala基础知识的快速介绍和简单罗列。并不全面。
<a name="8546d654"></a>
### 0x00：case class 工厂方法实现

```scala
class Car(val str: String) {
}

object Car {
    def apply(str: String) = new Car(str)
}
```
<a name="5503a7be"></a>
### 0x01：推导

```scala
val v = Vector(0, 1, 2, 3, 4)
val result = for {
	n <- v
	if n %　2 == 0
} yield {
	val u = n + 10
	u * 2
}
```
<a name="0571ede3"></a>
### 0x02：反射

<a name="a1740418"></a>
### 0x03：枚举

```scala
object Level extends Enumeration {
    type Level = Value
    val Low, High = Value
}
```
<a name="3eb3bf0c"></a>
### 0x04：类型
Scala里类型和类是俩东西<br />额外参考<br />[https://blog.csdn.net/hellojoy/article/details/81020832](https://blog.csdn.net/hellojoy/article/details/81020832)
```scala
scala> classOf[List[Int]] == classOf[List[String]]
res16: Boolean = true

scala> typeOf[List[Int]] == typeOf[List[String]]
res17: Boolean = false
```
<a name="4f8c6b90"></a>
### 0x05：统一访问原则
```scala
trait Base {
    def f: Int
}

class Derived extends Base {
    val f = 1
}
```
<a name="32988f7d"></a>
### 0x06：单元测试
推荐使用ScalaTest。里面的Assert特别好用，数据对比十分清晰。和Node.js中的PowerAssert一样，是目前遇到的最好断言显示方式。
<a name="527e139f"></a>
### 0x07：组合表达式
把表达式用花括号包起来，返回结果默认为最后的表达式。
<a name="9cc4406b"></a>
### 0x08：标记特征和case对象

```scala
sealed trait Color 

case object Red extends Color
case object Green extends Color

object Color {
    val values = Vector(Red, Green)
}
```

<a name="32536950"></a>
### 文档
[https://scala-lang.org/files/archive/api/2.11.12/#package](https://scala-lang.org/files/archive/api/2.11.12/#package)<br />某些Scala类是直接用的Java类，Scala文档中没有（例如String）。要去Java文档中看，地址：[https://docs.oracle.com/javase/8/docs/api/overview-summary.html](https://docs.oracle.com/javase/8/docs/api/overview-summary.html)
<a name="25f9c7fa"></a>
## 总结
这本书没有《Scala编程》写的深入，还是推荐《Scala编程》，当然两本都看收货更多。
