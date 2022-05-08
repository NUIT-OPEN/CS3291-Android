# 条件控制语句课堂练习

## 题目

```
根据录入的成绩，输出对应的等级，90~100：A级，80~90：B级，70~80：C级，60~70：D级，<60:不及格

输入的提示信息：“请输入成绩：”

输出的提示信息：“你的成绩是X级”
```

## 代码

```kotlin
data class RankRange(val min: Int, val max: Int, val level: String)

fun main() {
    print("请输入成绩：")
    val scoreStr = readLine()
    val score = scoreStr?.toInt()
    val ranks = arrayOf(
        RankRange(90, 100, "A级"),
        RankRange(80, 90, "B级"),
        RankRange(70, 80, "C级"),
        RankRange(60, 70, "D级"),
        RankRange(0, 60, "不及格"),
    )

    if (score == null)
        return

    for (rank in ranks) {
        if (score >= rank.min && score <= rank.max) {
            println("你的成绩是${rank.level}")
            break
        }
    }
}
```

## 运行结果

```
请输入成绩：-1

Process finished with exit code 0
```

```
请输入成绩：0
你的成绩是不及格

Process finished with exit code 0
```

```
请输入成绩：60
你的成绩是D级

Process finished with exit code 0
```

```
请输入成绩：70
你的成绩是C级

Process finished with exit code 0
```

```
请输入成绩：80
你的成绩是B级

Process finished with exit code 0
```

```
请输入成绩：90
你的成绩是A级

Process finished with exit code 0
```

```
请输入成绩：100
你的成绩是A级

Process finished with exit code 0
```
