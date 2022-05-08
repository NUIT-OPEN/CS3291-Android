# Kotlin循环和类

## 题目

```
1、编写一个Course类作为父类，属性score，qiandaocishu

2、编写一个Kotlin类作为Course的子类，增加课程名称属性

3、在Kotlin类中写一个方法printqiandaocishu，使用for in循环输出1..qiandaocishu

4、创建一个Kotlin文件和main方法，创建Kotlin类对象，并调用printqiandaocishu方法
```

## 代码

```kotlin
open class Course(var score: Int, var qiandaocishu: Int) {// 基类

}

class Kotlin(score: Int, qiandaocishu: Int, var name: String) : Course(score, qiandaocishu) {
    fun printqiandaocishu() {
        for (i in 1..qiandaocishu)
            println(i)
    }
}

fun main() {
    Kotlin(0, 3, "测试").printqiandaocishu()
}
```

## 运行结果

```
1
2
3

Process finished with exit code 0
```
