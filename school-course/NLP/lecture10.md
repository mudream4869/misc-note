# Statistical Parsing

問題：給這個句子和一些結構，看這些結構哪個較為漂亮或者適合這句子

## CFG Parsing

我們試著從**正確的Parse**到**最可能Parse**

## PCFG

*定義*：

- 有限個terminal, nonterminal
- 起始狀態
- 規則
- 對於每個規則都有一個機率函數，並且

    ![](https://latex.codecogs.com/gif.latex?%5Csum_j%20P%28N%5Ei%20%5Crightarrow%20%5Cxi%5Ej%20%29%20%3D%201)

### 三個關於Model的假設

- 節點機率上下文無關
- 節點機率和祖先無關
- 節點擊率和位置無關

### Train Model

重點試我們要如何取得每隔規則的機率

![](https://latex.codecogs.com/gif.latex?P%28%5Calpha%20%5Crightarrow%20%5Cbeta%20%7C%20%5Calpha%29)

一個簡單的Approach

![](https://latex.codecogs.com/gif.latex?P%28%5Calpha%20%5Crightarrow%20%5Cbeta%20%7C%20%5Calpha%29%20%3D%20%5Cfrac%7BC%28%5Calpha%20%5Crightarrow%20%5Cbeta%29%7D%7BC%28%5Calpha%29%7D)

可以做機率版的`CKY`

## PRG

機率型Regular Grammar：每個 `A -> w B` 都有機率
