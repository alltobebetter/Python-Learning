# Python 中 ASCII 码的互相转化

**什么是 ASCII 码？**

可以简单理解为，计算机内部用数字来表示字符（例如字母、数字、符号）。ASCII 码就是一套约定，规定了每个字符对应的数字是多少。比如，字母 'A' 对应数字 65，字母 'a' 对应数字 97。

**Python 如何进行转化？**

**1. 字符转 ASCII 码：**

   想象一下，你要把一个字母翻译成它的编号。Python 中用 `ord()` 函数来做这件事：

   ```python
   letter = 'A'
   ascii_code = ord(letter) 
   print(ascii_code)  # 输出：65
   ```

**2. ASCII 码转字符：**

   反过来，如果你知道编号，想查出对应的字母，Python 中用 `chr()` 函数：

   ```python
   ascii_code = 65
   letter = chr(ascii_code)
   print(letter)  # 输出：A
   ```

**举个栗子：**

假设你想把一句话 "Hello" 转换成对应的 ASCII 码：

```python
message = "Hello"
ascii_codes = []
for letter in message:
  ascii_codes.append(ord(letter))

print(ascii_codes)  # 输出: [72, 101, 108, 108, 111]
```

再把 ASCII 码转换回原来的句子：

```python
ascii_codes = [72, 101, 108, 108, 111]
message = ""
for code in ascii_codes:
  message += chr(code)

print(message)  # 输出: Hello
```

**总结：**

* `ord()` 函数：字符 -> ASCII 码
* `chr()` 函数：ASCII 码 -> 字符

是不是很简单？就像查字典一样，知道一个就能查到另一个！ 


希望这个解释足够通俗易懂，让你轻松掌握 Python 中 ASCII 码的转化！ 
