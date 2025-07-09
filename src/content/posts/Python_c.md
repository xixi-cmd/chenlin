---
title: 面向对象，真的面向对象
date: 2025-07-08T07:29:49.820Z
lastMod: 2025-07-28T07:29:49.820Z
tags: [Code, Python, 笔记]
category: Python
summary: 这篇文章介绍了面向对象编程的概念，以及如何用Python实现面向对象编程。
---
# 什么是面向对象编程？

> 参考了知乎上的<a href="https://zhuanlan.zhihu.com/p/334050088">这篇帖子</a>可以说是非常透彻了

简单来说，面向对象可以分为三个直接的东西

第一个叫做<a href="https://baike.baidu.com/item/%E5%B0%81%E8%A3%85/2796965?fromModule=lemma_inlink">封装</a>，比如说现在你和你女朋友吵架，你女朋友问你，为什么你不会自己主动去哄她，你很上进，马上就去找，然后见到有人分享了一份材料，里面记录了再什么场景下哄女生开心的话（不是我说，真有人找吗），在这封材料里，任何场景就是一个类，而对应的回答就是返回值

第二个叫做<a href="https://baike.baidu.com/item/%E6%8A%BD%E8%B1%A1/9021828">抽象</a>，抽象不是搞抽象，比如说女朋友问你“和你们一起上班的有没有漂亮小姐姐？”，你要怎么回呢？肯定是回没有或者小姐姐没你好看，抽象就是这个概念，你看，抽象，是把要回答的对象抽出来，反回去的是用户想要的内容

第三个是<a href="https://baike.baidu.com/item/%E5%A4%9A%E6%80%81%E6%80%A7/4725624?fromModule=lemma_inlink">多态性</a>，意思是一样的函数可以得到不同的结果，比如你是一个帅哥，你站在那，有不同的女生和你搭话，第一个女生不好看，但是嘴甜，你说她情商很高，善解人意；第二个女生好看，但是不是很会说话，很害羞，你说她很漂亮，但是要大胆一点；第三个女生又漂亮又会说话，你说她右眼眼角那颗痣真好看。多态性就是说对于不同的对象给以不同的反馈，就像是一个函数的y因为x的改变而改变

> 其实有第四个的，但是很简单，应该都知道吧(😓)

# 看看代码

```python
# 面向对象
class saohua:
    def __init__(self): # self代表类的实例
        self.name = "柳如烟" # 对象名字
        self.age = 23 # 年龄
        self.gender = "女" # 性别
nvyou001 = saohua() # 创建对象
print(nvyou001.name) # 输出对象名字
```

可以利用面向对象语言输出一个名叫柳如烟的对象的名字，更改print里面的内容我们也可以输出别的信息，比如年龄，性别

也可以使用这样的写法，让对象的输出更加灵活

```python
# 面向对象
class saohua:
    def __init__(self, name, age): # type: ignore
        self.name = name
        self.age = age
nvyou001 = saohua("柳如烟", 23)
# print(nvyou001.name)
# print(nvyou001.age)
print(f"{nvyou001.name}今年{nvyou001.age}岁了！") # 字符串格式化输出
```
