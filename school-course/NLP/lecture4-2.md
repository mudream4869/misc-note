# Smoothing

* 機率估計的可靠性 
* 好的分辨性

## Modeling

P(W | Y) ~ P(Y | W)P(W)

* P(Y | W) -> acoustic model
* P(W) -> model

### N-gram

P(w9 | w1...w8)

w1...w8 -> history

* large n -> greater, but 總大小指數增加

| Model   | Number of Parameter | 
| ------- | ------------------- |
| Unigram |  N                  |
| Bigram  | N^2                 |
| Trigram | N^3                 |

## Statistical Estimators I : Overview

## Data Sparseness

Data sparity + max likelyhood => P = 0

* Smoothing
    - 把過去有看過的機率降低
    - 留給一些沒看過的

* Zero count
    - Zipf' law : 小部分詞有高機率，大部份詞只有小機率
    - 如何估計從來沒有出現的`N-gram`

## Smoothing

* Discounting : 把前面看過的弄掉一些，分配給下面的
* Model combination

### Discounting

Laplace : 讓每個N-gram都先出現1次

![](https://latex.codecogs.com/gif.latex?P_%7BLap%7D%28w_%7Bn-1%7D%2C%20w_n%29%20%3D%20%5Cfrac%7Br&plus;1%7D%7BB&plus;N%7D)

* 可是會有很多
* Church and Gale’s experiment: Bigram會生出很多（N = 2.2*10^7, B = 1.6*10^11）

|      | I    | want | to   | eat  |
| ---- | ---- | ---- | ---- | ---- |
|  I   | 6    | 828  | 2    | 10   |
| want | 3    | 1    | 609  | 2    |
| to   | 3    | 1    | 5    | 687  |

使用 C' = P_Lap*N，發現有些Couting變動會很大。

==> +1可能太大，+小一點？

![](https://latex.codecogs.com/gif.latex?P_%7BLap%7D%28w_1...w_n%29%20%3D%20%5Cfrac%7BC%28w_1...w_n%29&plus;%5Clambda%7D%7BB&plus;N%20%5Clambda%7D%20%3D%20%5Cmu%20%5Cfrac%7BC%28w1...w_n%29%7D%7BN%7D%20&plus;%20%281-%5Cmu%29%5Cfrac%7B1%7D%7BB%7D)

### Train vs heldout

![](https://latex.codecogs.com/gif.latex?P_ho%28w%29%20%3D%20%5Cfrac%7BT_r%7D%7BN_rN%7D)
