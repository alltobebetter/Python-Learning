# sorted() 函数：像整理师一样排序

想象你有一盒玩具，里面乱七八糟地堆满了各种各样的玩具。你想把它们按照大小、颜色或者类型整理好，这时候你就需要一个整理师。`sorted()` 函数就像这个整理师，它能把任何可迭代对象（比如列表、元组、字符串）里的元素按照一定的规则排序，并返回一个新的已排序列表。

**怎么用呢？**

`sorted()` 函数的基本用法非常简单：

```python
my_list = [3, 1, 4, 1, 5, 9, 2, 6]
sorted_list = sorted(my_list)  # 对 my_list 进行排序
print(sorted_list)  # 输出：[1, 1, 2, 3, 4, 5, 6, 9]
print(my_list)  # 输出：[3, 1, 4, 1, 5, 9, 2, 6]，my_list 不变
```

**解释一下：**

1. `my_list` 是一个包含数字的列表，就像一盒乱七八糟的玩具。
2. `sorted(my_list)` 对 `my_list` 进行排序，并将排序后的结果赋值给 `sorted_list`。
3. `sorted_list` 现在是一个新的已排序列表，就像整理好的玩具盒。
4. `my_list` 仍然是原来的乱序列表，`sorted()` 函数并没有修改它。

**更强大的功能：**

`sorted()` 函数还可以接受两个可选参数：`key` 和 `reverse`。

**1. `key` 参数：**

`key` 参数让你可以指定一个函数，用于从每个元素中提取用于比较的“键”。 

例如，你想按照字符串的长度排序：

```python
words = ["apple", "banana", "kiwi", "orange"]
sorted_words = sorted(words, key=len)  # 按照字符串长度排序
print(sorted_words)  # 输出：['kiwi', 'apple', 'orange', 'banana']
```

这里，`key=len` 表示使用 `len()` 函数来获取每个字符串的长度作为排序的依据。

**2. `reverse` 参数：**

`reverse` 参数控制排序的方向。默认情况下，`reverse=False`，表示按升序排序。如果设置为 `True`，则按降序排序。

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]
sorted_numbers = sorted(numbers, reverse=True)  # 按降序排序
print(sorted_numbers)  # 输出：[9, 6, 5, 4, 3, 2, 1, 1]
```

**总结：**

`sorted()` 函数就像一个强大的整理师，可以帮助你对任何可迭代对象进行排序。它不会修改原始对象，而是返回一个新的已排序列表。你可以使用 `key` 参数自定义排序规则，使用 `reverse` 参数控制排序方向。

希望这个解释足够清晰易懂，让你轻松理解 `sorted()` 函数！ 😊 
