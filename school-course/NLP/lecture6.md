# Hidden Markov Models

## 兩個假設

* 下一個字只和上一個字有關

![](https://latex.codecogs.com/gif.latex?P%28X_%7Bt&plus;1%7D%20%3D%20s_k%20%7C%20X_1%2C%20X_2%2C%20...%2C%20X_t%29%20%3D%20P%28X_%7Bt&plus;1%7D%20%3D%20s_k%20%7C%20X_t%29)

* 時間不變性

## 冰淇凌

由冰淇凌日記推出天氣冷熱

* Given : 冰淇凌序列： 1, 2, 3, 2, 2, 2, 3
* Produce : 天氣序列： H, C, H, H, H, C

HMM:

* HOT  -> HOT  : 0.7
* HOT  -> COLD : 0.3
* COLD -> HOT  : 0.4
* COLD -> COLD : 0.6

那現在假如有一個冰淇凌序列: 1, 3, 1

那 `P(CHC | Seq = 1, 3, 1) = P(1 | COLD)P(1 | COLD)P(3 | HOT)P(C -> H)P(H-> C)`

用這種方法，可以估計出 P(???) 所有可能性，藉此找出 `argmax P(???)`

## 三個問題

使用這模型概念，可以弄出三個問題：

1. 給定Model, Observation Seq：求機率
2. 給訂Model, Observation Seq：求最可能的Seq
3. 給定Observation Seq : 訓練參數


