# A Neural Probabilistic Language Model and Word Embedding

估計P(w_1 ... w_T) = \PI P(..)

## 兩個問題

* 有關係的字中間可能有間隔
* 相似性
    - The cat is walking in the bedroom
    - A dog was running in a room

## Distributed Representations

* 用vector表示每個word
* 用word的vector表達word sequence的機率

## 模型

![](https://latex.codecogs.com/gif.latex?f%28w_%7Bt-n&plus;1%7D%2C%20...%20%2C%20w_t%29)

### The Continuous Bag-Of-Word Model

### The Skip-gram Model

## Word to Vector

* 降低維度
    * Latent Semantic Analysis (LSA)
    * Principal Component Analysis (PCA)
    * Latent Dirichlet Allocation (LDA)

### 學習Word的Representation

* Distributional hypothesis
    * 在哪裡使用？

    > You shall know a word by the company it keeps. (J.R. Firth, 1957)

