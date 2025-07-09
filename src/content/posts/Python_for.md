---
title: Python里的for和while循环
date: 2025-06-24T07:29:49.820Z
lastMod: 2025-06-24T07:29:49.820Z
tags: [Code, Python, 笔记]
category: Python
summary: 这篇文章介绍了python里的for循环还有while循环的用法。
---

## 前言

这篇文章介绍了python里的for循环还有while循环的用法。
> PS：有一些是从知乎的账号上面抄回来的，原文链接：<https://zhuanlan.zhihu.com/p/106997999>

## for循环语句

### 语法 + 实例

```python
for i in range(1, 10):
  print("这是第", i, "次循环")
  #for循环的range函数从1到9（不包括10）循环
  #（a,b）是一个集合指的是集合{i|0<i<10} = [1,2,3,4,5,6,7,8,9]，而不是一个区间
  if i == 5:
    print("这是第五次循环，跳出循环")
    break  # 当i等于5时，跳出循环
  # continue语句
  if i % 2 == 0:
    print("这是偶数，跳过")
    continue  # 当i是偶数时，跳过当前循环
```

### 个人理解

for循环在我看来可以看成是一个数列，可以是[等比数列](https://zhida.zhihu.com/search?content_id=259165597&content_type=Article&match_order=1&q=等比数列&zhida_source=entity)，[等差数列](https://zhida.zhihu.com/search?content_id=259165597&content_type=Article&match_order=1&q=等差数列&zhida_source=entity)，[斐波那契数列](https://zhida.zhihu.com/search?content_id=259165597&content_type=Article&match_order=1&q=斐波那契数列&zhida_source=entity)等等，例如如果用for循环表示一个首项为2公比为2的等比数列，要怎么表示？

首先第一步我们要定义一个首项，就是当 ***i==1\*** 的时候我们要把首项定义就像是这样

```python
n = int(input("输入最后一个下标"))  #输入最后一个下标
for i in range(1, n+1):
  if i == 1:
    a = 2
    print("这是第", i, "次循环" + "本次循环定义数列的首项为", a)
```

接下来就是公比，公比我们可以手动输入，参考等比数列的通项公式，我们发现最后公比的角标是***n-1\***

***因此在定义数列的时候，一定是2\*(2\**\*(n-1))**

代码如下

```python
n = int(input("输入最后一个下标")) #输入最后一个下标
for i in range(1, n+1):
 if i == 1:
    a = 2
 print("这是第", i, "次循环" + "本次循环定义数列的首项为", a)
 if i == (n):
 print("这是最后一次循环，这一次循环会输出最后一项的结果为", a*(2**(n-1)))
```

**看末尾，这就是一个等比数列，可以通过修改在第一次循环的时候的a的值来进行修改首项，修改最后一行代码里的2来进行改变公比的操作。等差数列也是类似，所以for循环可以当成是一个数列来看，结合相应的公式就可以搞定最后想要输出的值。**

# while循环语句

## 基本语法

```python
i= 0
while i < 5:  # 循环条件
    print(i)
    i += 1
```

## while循环的嵌套

```python
i = 0
while i < 3:
    j = 0
    while j < 3:
        print(i, j)
        j += 1
    i += 1
```

## 循环控制语句

- `break` 语句：用于跳出当前循环。
- `continue` 语句：用于跳过当前循环，直接进入下一轮循环。
- `pass` 语句：用于占位，什么都不做。

```python
i = 0
while i < 5:
    print(i)
    i += 1
    if i == 3:
        break  # 跳出当前循环

i = 0
while i < 5:
    i += 1
    if i == 3:
        continue  # 跳过当前循环
    print(i)
```

## 实例

让用户持续输入数字，最后输入q的时候计算平均值并发送给用户。

```python
print('你可以使用本程序求平均值') 
user_input = input("请输入一个数字,用来求平均值")
total = 0
count = 0
# 一直重复请求，直到某条件为假则使用while而不是for循环
while user_input != 'q':
    total += float(user_input)
    count += 1
    user_input = input("请输入一个数字,用来求平均值")
if count < 1:
    print('你咋直接输入q了吗？这我不炸了？')
else:
    result = total / count #平均值就是总数除以个数
    print('平均值为：', result)
```

## 个人理解

while循环在我看来就是一个条件判断语句，当条件为真时，循环体内的代码就会被执行，当条件为假时，循环体内的代码就不会被执行。

while循环的条件判断语句可以是任何表达式，只要表达式的结果为真，循环体内的代码就会被执行，否则循环体内的代码就不会被执行。

while循环的嵌套可以实现多重循环，即在一个循环体内嵌套另一个循环体。

同时，也可以这么理解，while的翻译是“当···时”。所以while语句的意思就是当某一个条件发生或者没有发生的时候，循环体内的代码就会被执行。

>有点类似于if语句的意思。

break语句的作用是跳出当前循环，continue语句的作用是跳过当前循环，pass语句的作用是什么都不做。
