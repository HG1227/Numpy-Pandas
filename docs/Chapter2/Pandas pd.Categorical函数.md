# Pandas pd.Categorical()函数

```python
pandas.Categorical(values,
                   categories = None,
                   ordered = None,
                   dtype = Nonel
                   fastpath = False 
                  )
```

参数：

- values：类似列表。分类的值，如果给出了类别，则不在类别中的值将替换为NaN。
- categories：索引式（唯一），可选。此分类的唯一类别。如果没有给出，则假定类别是值的唯一值。
- ordered：布尔值，（默认为False）。此分类是否被视为有序分类。如果没有给出，则不会订购生成的分类。
- dtype：CategoricalDtype，CategoricalDtype用于此分类的实例
  

示例

```python
In [16]: st = ['a','a','b','c','c']

In [17]: ss = pd.Categorical(st)

In [18]: ss
Out[18]:
[a, a, b, c, c]
Categories (3, object): [a, b, c]

In [22]: ss.dtype
Out[22]: CategoricalDtype(categories=['a', 'b', 'c'], ordered=False)


```

这里就可以看到 categorical 实际上是计算一个列表型数据中的类别数，即不重复项，它返回的是一个CategoricalDtype 类型的对象，相当于在原来数据上附加上类别信息

**属性 ` codes `和 `categories `**

具体的类别可以通过和对应的序号可以通过` codes `和 `categories `来查看：

```python
In [23]: ss.codes
Out[23]: array([0, 0, 1, 2, 2], dtype=int8)

In [21]: ss.categories
Out[21]: Index(['a', 'b', 'c'], dtype='object')

```

有序分类可以根据类别的自定义顺序进行排序，并且可以具有最小值和最大值。

```python
>>>c = pd.Categorical(['a','b','c','a','b','c'], ordered=True, categories=['c', 'b', 'a'])
>>> c
[a, b, c, a, b, c]
Categories (3, object): [c < b < a]
>>> c.min()
'c'

```

属性

- `categories`	这种分类的类别。
- `codes`	此类别的类别代码。
- `ordered`	类别是否具有有序关系
- `dtype`	在CategoricalDtype此实例



参考：

<a href="https://blog.csdn.net/Lq_520/article/details/83616673" blank="">pandas 中 pd.Categorical用法</a>

