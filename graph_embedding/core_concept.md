# 基础组件

0、raw input

1、图模型概念
edge, node, ...

2、计算图相关概念
walk_method / join_method

3、图的概率属性

# 基本流程：case
## 股票

### raw_input:
```
day1  a1, a2, ..., a100, b1, b2, ..., b100, ..., Y(a), Y(b)
day2  ....
```

其中a~d为股票，Y(a~d)表示涨跌二值变量，a1~a100表示原始输入（当日成交量、当日股价等）

### structure
![-w736](media/15787601112370/15788130557096.jpg)
计算图

![-w590](media/15787601112370/15788136833785.jpg)
展开的计算图

1、a1~a100 -> DNN -> a-embedding
2、[a-embedding]n = f([a-embedding]n-1, [c-embedding]n-1 ,[d-embedding]n-1 )
3、a-loss = cross-entropy(softmax(a-embedding))
4、loss = sum(a~d loss).

```
某种意义上，可以把图神经网络理解为RNN + attention + 人工跳接。
某种程度上，图神经网络可以进行结构调优的自动化。
收敛平衡态对应的是有效市场状态。
```

## 电商
比上一问题多出的要素：
1、节点间跳转（购买行为的【关联规则】）
2、结构性 & 序列性
    2.1 相似的用户购买相似的商品（协同过滤）体现出的节点相似度的结构性
    2.2 同一用户购买商品的序列性，使得问题可以被转化为W2V类似问题进行训练

比上一问题减少的要素：
1、似乎不存在动态游走并进入收敛平衡态这一问题。


# 算法
coming soon...