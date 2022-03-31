# Ex1

* Activity&Intent的使用

## Activity基本使用

* 手动创建活动

```kotlin
val intent = Intent()
intent.setClass(this, FirstActivity::class.java)
startActivity(intent);
```

* 加载布局

```kotlin
class FirstActivity : AppCompatActivity() {
    var msg: String? = null;

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_first)
    }
}
```

* 控件点击事件

```kotlin
b_first = this.findViewById<Button>(R.id.b_first)
b_first.setOnClickListener {
    // do something
}
```

* 弹出Toast提示

```kotlin
b_test = this.findViewById<Button>(R.id.b_test)
b_test.setOnClickListener {
    Toast.makeText(this, "you click me", Toast.LENGTH_SHORT).show()
}
```

## 使用Intent显式跳转

```kotlin
val intent = Intent()
intent.setClass(this, FirstActivity::class.java)
startActivity(intent);
```

## 使用Intent隐式跳转

* 拨号界面

```kotlin
val intent = Intent();
intent.addCategory(Intent.ACTION_CALL)
intent.data = Uri.parse("tel:12345")
startActivity(intent)
```

* 浏览器

```kotlin
val intent = Intent()
intent.addCategory(Intent.CATEGORY_BROWSABLE)
intent.data = Uri.parse("https://baidu.com")
startActivity(intent);
```

## Intent携带数据

```kotlin
val intent = Intent()
intent.putExtra("msg", "hello FirstActivity,i am MainActivity")
intent.setClass(this, FirstActivity::class.java)
startActivity(intent);
```

## 返回数据给上一个活动

* 带请求代码启动activity

```kotlin
val intent = Intent()
intent.setClass(this, ThirdActivity::class.java)
startActivityIfNeeded(intent, 1);
```

* 新activity回传结果

```kotlin
val intent = Intent()
intent.putExtra("return", "我回传一本给你")
setResult(Activity.RESULT_OK, intent)
finish()
```

* 覆写方法获取返回结果

```kotlin
override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
    super.onActivityResult(requestCode, resultCode, data)
    if (requestCode == 1 && resultCode == Activity.RESULT_OK) {
        val returnData = data?.getStringExtra("return")
        Toast.makeText(this, returnData, Toast.LENGTH_SHORT).show()
    }
}
```
