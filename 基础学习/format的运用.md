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

**总结：**

`format()` 方法就像一个强大的填空题工具，它可以帮助你创建各种格式的字符串，让你的代码更加灵活和易读。 

**记住：**

* `{}` 是占位符，等待被填写。
* 可以用编号、关键词、格式化说明符等方式来指定答案。
* `format()` 方法非常强大，还有很多其他的用法等待你去探索！ 
