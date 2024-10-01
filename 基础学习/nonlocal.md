# nonlocal 的用法详解

**简单来说，`nonlocal` 关键字用来告诉 Python，一个变量不是局部的，而是属于外部函数作用域的。**

我们知道，Python 中变量的作用域有四种：

1. **局部作用域 (Local)**:  定义在函数内部的变量
2. **封闭作用域 (Enclosing)**:  外部函数的作用域 (如果存在嵌套函数)
3. **全局作用域 (Global)**:  定义在模块顶层的变量
4. **内置作用域 (Built-in)**:  Python 内置的函数和变量

**`nonlocal` 专门用来处理封闭作用域的变量。**

**什么时候需要用 `nonlocal`?**

当你在嵌套函数中想要修改外部函数的变量时，就需要用到 `nonlocal`。

**举个例子:**

```python
def outer_function():
  x = "outer"

  def inner_function():
    nonlocal x  # 告诉 Python，x 不是局部变量，而是外部函数的变量
    x = "inner"
    print("内部函数:", x)

  inner_function()
  print("外部函数:", x)

outer_function() 
```

**输出:**

```
内部函数: inner
外部函数: inner
```

**解释:**

1. `outer_function` 定义了一个变量 `x`，值为 "outer"。
2. `inner_function` 是嵌套在 `outer_function` 中的函数。
3. 在 `inner_function` 中，我们使用了 `nonlocal x`，告诉 Python 我们要修改的是 `outer_function` 中的 `x`，而不是创建一个新的局部变量。
4. `inner_function` 将 `x` 的值修改为 "inner"。
5. 当 `inner_function` 执行完毕后，`outer_function` 中的 `x` 的值也变成了 "inner"。

**如果没有 `nonlocal` 会怎么样?**

```python
def outer_function():
  x = "outer"

  def inner_function():
    x = "inner"  # 没有 nonlocal，这里会创建一个新的局部变量 x
    print("内部函数:", x)

  inner_function()
  print("外部函数:", x)

outer_function()
```

**输出:**

```
内部函数: inner
外部函数: outer
```

**解释:**

由于没有 `nonlocal`，`inner_function` 中的 `x = "inner"` 创建了一个新的局部变量 `x`，它与 `outer_function` 中的 `x` 是不同的变量。所以 `outer_function` 中的 `x` 的值仍然是 "outer"。


**总结:**

* `nonlocal` 用于在嵌套函数中修改外部函数的变量。
* `nonlocal` 只能用于修改封闭作用域的变量，不能修改全局变量。
* 如果没有 `nonlocal`，在嵌套函数中赋值给一个变量会创建一个新的局部变量。
