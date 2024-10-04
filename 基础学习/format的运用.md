# `format()` 方法：像填空题一样，打造个性化字符串

想象一下，你有一份填空题试卷，上面有一些空格需要你填写答案。 `format()` 方法就像这份试卷，它提供了一个模板字符串 (试卷)，其中包含了一些占位符 (空格)，你需要用具体的值 (答案) 来填充这些占位符，最终得到一个完整的字符串 (答卷)。

**基本玩法：**

```python
"模板字符串".format(值1, 值2, ...)
```

* **模板字符串**:  就像试卷，包含了一些占位符 `{}`， 等待被填写。
* **值**: 就像答案，用来填充占位符， 可以是数字、字符串、列表等等。
* 格式化数字，使用`format()`函数将数字格式化，,表示千位分隔符。如`format(123456789, ',')`的结果为`123,456,789`。


**例如：**

```python
name = "Alice"
age = 30
greeting = "Hello, my name is {} and I'm {} years old.".format(name, age)
print(greeting)  # 输出: Hello, my name is Alice and I'm 30 years old.
```

这里， `{}` 就是占位符， `format(name, age)`  就像把 "Alice" 和 30 这两个答案填到空格里，最终得到了完整的句子。

**进阶玩法：**

**1. 编号填空：**

你可以在占位符里加上编号，指定每个答案应该填到哪个空格里。

```python
greeting = "Hello, {1} and {0}!".format("Alice", "Bob")
print(greeting)  # 输出: Hello, Bob and Alice!
```

这里， `{0}` 对应第一个答案 "Alice"， `{1}` 对应第二个答案 "Bob"。

**2. 关键词填空：**

你也可以给每个空格起一个名字，然后用关键词的方式指定答案。

```python
greeting = "Hello, {name} and {age}!".format(name="Alice", age=30)
print(greeting)  # 输出: Hello, Alice and 30!
```

这里， `{name}` 对应 `name="Alice"`， `{age}` 对应 `age=30`。

**3. 格式化填空：**

你还可以指定答案的格式，例如保留几位小数、转换成十六进制等等。

```python
pi = 3.141592653589793
formatted_pi = "Pi is approximately {:.2f}.".format(pi)
print(formatted_pi)  # 输出: Pi is approximately 3.14.
```

这里， `:.2f`  表示保留两位小数。

**4. 高级填空：**

你还可以用 `format()` 方法访问对象属性、字典元素等等。

```python
person = {"name": "Alice", "age": 30}
greeting = "Hello, {person[name]}! You are {person[age]} years old.".format(person=person)
print(greeting)  # 输出: Hello, Alice! You are 30 years old.
```

**5.format的其他用法**
除了 `,` 表示千位分隔符外，`format()` 函数还支持许多其他的特殊符号，用于格式化数字、字符串、日期时间等数据类型。

以下是 `format()` 函数常用的一些特殊符号及其含义：

**数字格式化：**

* `,`：千位分隔符。
* `.`：小数点。
* `b`：二进制格式。
* `c`：Unicode 字符。
* `d`：十进制整数。
* `e` 或 `E`：科学计数法。
* `f` 或 `F`：定点数。
* `g` 或 `G`：通用格式（根据数值大小自动选择 `e` 或 `f` 格式）。
* `o`：八进制格式。
* `x` 或 `X`：十六进制格式。
* `%`：百分比格式。

**字符串格式化：**

* `s`：字符串格式。
* `<`、`>`、`^`：左对齐、右对齐、居中对齐。
* `+`、`-`、` `：显示正负号、只显示负号、在正数前面添加空格。
* `0`：使用 `0` 填充空白。
* `#`：显示进制前缀（例如 `0b`、`0o`、`0x`）。

**日期时间格式化：**

* `%Y`：年份（例如 2023）。
* `%m`：月份（例如 01）。
* `%d`：日期（例如 05）。
* `%H`：小时（24 小时制）。
* `%M`：分钟。
* `%S`：秒。
* `%a`：星期几的缩写（例如 Mon）。
* `%A`：星期几的全称（例如 Monday）。
* `%b`：月份的缩写（例如 Jan）。
* `%B`：月份的全称（例如 January）。
* `%p`：上午/下午指示符（例如 AM）。

**其他：**

* `{}`：占位符，用于替换 format() 函数的参数。
* `:`：用于分隔字段宽度、精度、对齐方式等格式说明符。


**示例：**

```python
number = 1234.5678
formatted_number = format(number, ",.2f")  # 千位分隔符，保留两位小数
print(formatted_number)  # 输出: 1,234.57

string = "hello"
formatted_string = format(string, "^10s")  # 居中对齐，宽度为 10
print(formatted_string)  # 输出:   hello   

import datetime
now = datetime.datetime.now()
formatted_date = format(now, "%Y-%m-%d %H:%M:%S")  # 格式化日期时间
print(formatted_date)  # 输出: 2023-11-06 10:30:00
```


**更多信息：**

你可以参考 Python 官方文档中关于 `format()` 函数的详细说明，了解更多格式说明符及其用法。

* [Format String Syntax](https://docs.python.org/3/library/string.html#formatstrings)

**总结：**

`format()` 方法就像一个强大的填空题工具，它可以帮助你创建各种格式的字符串，让你的代码更加灵活和易读。 

**记住：**

* `{}` 是占位符，等待被填写。
* 可以用编号、关键词、格式化说明符等方式来指定答案。
* `format()` 方法非常强大，还有很多其他的用法等待你去探索！ 
