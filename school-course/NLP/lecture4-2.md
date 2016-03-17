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
