`union` 是 Python 集合（`set`）的一个方法，用于返回两个或多个集合的并集。并集是指所有集合中存在的唯一元素的集合。

### 用法

1. **基本语法**：
   ```python
   set1.union(set2, set3, ...)
   ```

2. **示例**：
   ```python
   # 创建两个集合
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}

   # 使用 union 方法
   result = set1.union(set2)
   print(result)  # 输出: {1, 2, 3, 4, 5}
   ```

3. **使用 `|` 操作符**：
   `union` 方法的功能也可以通过 `|` 操作符实现：
   ```python
   result = set1 | set2
   print(result)  # 输出: {1, 2, 3, 4, 5}
   ```

4. **合并多个集合**：
   你可以合并多个集合：
   ```python
   set3 = {5, 6}
   result = set1.union(set2, set3)
   print(result)  # 输出: {1, 2, 3, 4, 5, 6}
   ```

5. **使用可迭代对象**：
   `union` 方法也可以接受一个可迭代对象（如列表、元组等）作为参数：
   ```python
   list_of_sets = [{1, 2}, {2, 3}, {4, 5}]
   result = set().union(*list_of_sets)
   print(result)  # 输出: {1, 2, 3, 4, 5}
   ```

### 注意事项
- 并集只包含唯一的元素，因此重复的元素会被自动去除。
- 原始集合不会被改变，`union` 方法返回一个新的集合。

通过这些示例，你可以看到 `union` 方法的灵活性和便利性，特别是在处理多个集合时。
