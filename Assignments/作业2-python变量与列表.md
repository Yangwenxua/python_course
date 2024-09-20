# 作业二 Python变量和列表

- 班级： 22物联2班

- 学号： B20220305223

- 姓名： 阳文萱

---

## 第1题：求离整数n最近的平方数（Find Nearest square number）

难度：8kyu

你的任务是找到一个正整数n的最近的平方数
例如，如果n=111，那么nearest_sq(n)（nearestSq(n)）等于121，因为111比100（10的平方）更接近121（11的平方）。
如果n已经是完全平方（例如n=144，n=81，等等），你需要直接返回n。
代码验证地址
<https://www.codewars.com/kata/5a805d8cafa10f8b930005ba>

```python
# 请在这里填写你的代码

def nearest_sq(n):
    if n < 0:
        return None
    sqrt_n = int(n ** 0.5)
    lower_sq = sqrt_n ** 2
    upper_sq = (sqrt_n + 1) ** 2
    return lower_sq if n - lower_sq <= upper_sq - n else upper_sq

## 第2题：偶数或者奇数（Even or Odd）

难度：8kyu

创建一个函数接收一个整数作为参数，当整数为偶数时返回”Even”当整数为奇数时返回”Odd”。
代码验证地址：
<https://www.codewars.com/kata/53da3dbb4a5168369a0000fe>

```python
# 请在这里填写你的代码

def even_or_odd(number):
    if number % 2 == 0:
        return "Even"
    else:
        return "Odd"

## 第三题：括号匹配（Valid Braces）

难度：6kyu

写一个函数，接收一串括号，并确定括号的顺序是否有效。如果字符串是有效的，它应该返回True，如果是无效的，它应该返回False。
例如：

```python
"(){}[]" => True 
"([{}])" => True
 "(}" => False
 "[(])" => False 
"[({})](]" => False
```

**提示：
python中没有内置堆栈数据结构，可以直接使用`list`来作为堆栈，其中`append`方法用于入栈，`pop`方法可以出栈。**

代码验证地址
<https://www.codewars.com/kata/5277c8a221e209d3f6000b56>

```python
# 请在这里填写你的代码

def validBraces(string):
    stack = []
    braces_map = {')': '(', '}': '{', ']': '['}
    for char in string:
        if char in braces_map.values():
            stack.append(char)
        elif char in braces_map.keys():
            if stack == [] or braces_map[char] != stack.pop():
                return False
    return stack == []

