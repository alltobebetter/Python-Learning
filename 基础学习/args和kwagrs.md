# `*args`和`**kwargs`

在Python中，`*args`和`**kwargs`是用于函数定义中的特殊语法，用于处理可变数量的参数。

### `*args`

- `*args`用于传递可变数量的位置参数。
- 在函数内部，`args`是一个元组，包含所有传入的位置参数。

**示例**：

```python
def example_function(*args):
    for arg in args:
        print(arg)

example_function(1, 2, 3)
```

输出：

```
1
2
3
```

在这个例子中，`example_function`可以接收任意数量的位置参数，并将其打印出来。

### `**kwargs`

- `**kwargs`用于传递可变数量的关键字参数。
- 在函数内部，`kwargs`是一个字典，包含所有传入的关键字参数。

**示例**：

```python
def example_function(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

example_function(name="Alice", age=30)
```

输出：

```
name: Alice
age: 30
```

在这个例子中，`example_function`可以接收任意数量的关键字参数，并将其打印出来。

### 同时使用 `*args` 和 `**kwargs`

你可以在同一个函数中同时使用`*args`和`**kwargs`，这样可以同时处理位置参数和关键字参数。

**示例**：

```python
def example_function(*args, **kwargs):
    print("Args:", args)
    print("Kwargs:", kwargs)

example_function(1, 2, name="Alice", age=30)
```

输出：

```
Args: (1, 2)
Kwargs: {'name': 'Alice', 'age': 30}
```

### 总结

- `*args`用于接收可变数量的位置参数，作为元组处理。
- `**kwargs`用于接收可变数量的关键字参数，作为字典处理。
- 这两者可以结合使用，以便灵活地处理不同数量和类型的参数。
