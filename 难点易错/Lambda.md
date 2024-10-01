# Lambda的参数

### 关键点：

1. **带参数的 `lambda` 函数**：
   
   - 可以接受外部传入的参数。
   - 例如：`lambda x: x * x`，您可以传入任意值来计算其平方。
   
   ```python
   square = lambda x: x * x
   print(square(5))  # 输出: 25
   ```
2. **不带参数的 `lambda` 函数**：
   
   - 不能接受任何输入参数。
   - 通常用于闭包，其中它可以访问外部函数的变量。
   - 例如：`lambda: x + y`，这个函数没有参数，但可以使用外部的 `x` 和 `y`。
   
   ```python
   def create_adder(x):
       return lambda: x + 10  # 这个 lambda 函数可以访问 x
   
   add_five = create_adder(5)
   print(add_five())  # 输出: 15
   ```

### 总结

- **带参数的 `lambda`**：适合需要动态输入的场景。
- **不带参数的 `lambda`**：适合闭包场景，能够利用外部变量，但不能处理动态输入。

这样可以让您在使用 `lambda` 函数时根据需求选择合适的形式！如果还有其他问题或需要进一步的例子，请随时问我。
