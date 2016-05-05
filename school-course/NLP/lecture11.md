# Parsing with Neural Networks

## RNN

w1, w2, w3, w4:

* y1 = tanh(W[w3, w4] + b)
* y2 = tanh(W[w2, y1] + b)
* y3 = tanh(W[w1, y2] + b)

```
       y3
      / \
     /   y2
    /   / \
   /   /   y1
  /   /   / \
w1   w2  w3  w4
```

## Models

* Model 1 : Greedy RNN
* Model 2 : Greedy Context-sensitive RNN
* Model 3 : Greedy, Context-sensitive RNN and Category Classifier
* Model 4 : Global, Context-sensitive RNN and Category Classifier

## Recursive Neural Networks for Structure Prediction

想要一個函數：

![](https://latex.codecogs.com/gif.latex?f%20%3A%20X%20%5Crightarrow%20Y)

* Y是所有可能分析🌲
* X有輸入Segment和每個Seg的Adj Matrix

### Greedy

1. 蒐集可以組合的Pair:

![](https://latex.codecogs.com/gif.latex?C%20%3D%20%5C%7B%20%28i%2C%20j%29%20%7C%20A_%7Bij%7D%20%3D%201%20%5C%7D)

1. 選出最高分：

![](https://latex.codecogs.com/gif.latex?p%28i%2C%20j%29%20%3D%20f%28W%5Bc_i%2C%20c_j%5D%20&plus;%20b%29)

![](https://latex.codecogs.com/gif.latex?s%28i%2C%20j%29%20%3D%20W%5E%7Bscore%7D%20p%28i%2C%20j%29)

然後從C裡面把`(i, j), (j, i)`移除並且把`(i, j, k)`加進去，其中k在i, j旁邊
