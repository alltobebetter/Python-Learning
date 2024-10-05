# sum和条件判断的结合

例如
```python
sum(1 for item in list_input if isinstance(item, list)
```

`sum()` 可以用这种方式与生成器表达式一起使用。这种组合既简洁又高效，因为它避免了创建不必要的中间列表。

以下是如何将 `sum(1 for item in list_input if isinstance(item, list))` 拆分成多行，以提高可读性，尤其是在条件或逻辑更复杂的情况下：

```python
def count_sublists(list_input):
    count = sum(
        1
        for item in list_input
        if isinstance(item, list)
    )
    return count

# 或者使用一个单独的生成器函数：

def count_sublists(list_input):
    def generate_ones():
        for item in list_input:
            if isinstance(item, list):
                yield 1

    return sum(generate_ones())


# 示例用法（对两个版本都相同）：
list_input = [1, [2, 3], 4, [5, 6], "string", (1,2), {3: "three"}]
sublist_count = count_sublists(list_input)
print(sublist_count)  # 输出: 2
```

**解释**

这两种多行版本在功能上与单行版本相同。它们只是使代码更易于阅读和理解，尤其是在条件或生成的值的逻辑更复杂的情况下。

* **多行生成器表达式：** 第一个版本简单地将生成器表达式拆分成多行，使每个部分更容易看到。Python 解释器将其视为单个表达式。

* **单独的生成器函数：** 第二个版本使用一个名为 `generate_ones()` 的单独的生成器函数。此函数迭代 `list_input`，并如果一个项是一个列表，则 `yield` 1。然后将 `sum()` 函数应用于此生成器函数的结果。对于更复杂的逻辑，这种方法可能更具组织性，并能提高可读性。


这两种多行方法都提供与单行版本相同的效率优势，因为它们仍然避免创建包含 1 的中间列表。选择哪种方法主要取决于个人喜好和代码复杂性。
