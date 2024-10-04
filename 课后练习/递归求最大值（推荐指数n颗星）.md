def find_highest_number(numbers_list):
    # 基线条件：列表中只有一个元素
    if len(numbers_list) == 1:
        return numbers_list[0]
    
    # 递归：比较第一个元素和剩余列表中最大的元素
    else:
        max_of_rest = find_highest_number(numbers_list[1:])
        return max(numbers_list[0], max_of_rest)

# 输入数字并转为列表
numbers_list = list(map(int, input().split()))

# 调用函数打印结果
print(find_highest_number(numbers_list))
