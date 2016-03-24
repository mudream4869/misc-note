# A Neural Probabilistic Language Model and Word Embedding

使用估計：

![](https://latex.codecogs.com/gif.latex?P%28w_1%2C%20...%2C%20w_T%29%20%5Capprox%20%5Cprod_%7Bt%20%3D%201%7D%5E%7BT%7D%20P%28w_t%20%7C%20w_%7Bt-1%7D%20%2C%20...%20%2C%20w_%7Bt-n&plus;1%7D%29)


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

### Neural Model

![](https://latex.codecogs.com/gif.latex?y%20%3D%20b%20&plus;%20Wx%20&plus;%20U%20%5Ctanh%28d%20&plus;%20Hx%29)

* Softmax => 
    
    ![](https://latex.codecogs.com/gif.latex?P%28w_t%20%7C%20w_%7Bt-1%7D%2C%20...%2C%20w_%7Bt-n&plus;1%7D%29%20%3D%20%5Cfrac%7Be%5E%7By_%7Bw_t%7D%7D%7D%7B%5Csum%20e%5E%7By_i%7D%7D)

## Issue

*  Neural Model可以做的精確，可是效能...?
*  藉由簡化來做的更有效率？

### The Continuous Bag-Of-Word Model

使用『從左右兩旁的字來預測中間的字』的model來找出適合word的vector

### The Skip-gram Model

使用『中間的字預測左右兩旁的字』的model來找出適合word的vector

## Word Vector

* 降低維度
    * Latent Semantic Analysis (LSA)
    * Principal Component Analysis (PCA)
    * Latent Dirichlet Allocation (LDA)

### 學習Word的Representation

* Distributional hypothesis
    * 在哪裡使用？

    > You shall know a word by the company it keeps. (J.R. Firth, 1957)

