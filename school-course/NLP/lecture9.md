# Syntactic Parsing

## CKY

先把Gammar都拆成`A -> BC`形式，然後再對用`dp[start][end]`，
`dp[i][j]`紀錄的是字串從`i`到`j`有可能有哪些狀態。

![](https://latex.codecogs.com/gif.latex?dp%5Bi%5D%5Bj%5D%20%3D%20%5Cbigcup_%7Bk%7D%20%5Cleft%5C%7B%20A%20%7C%20A%20%5Crightarrow%20BC%2C%20B%20%5Cin%20dp%5Bi%5D%5Bk%5D%2C%20C%20%5Cin%20dp%5Bk&plus;1%5D%5Bj%5D%20%5Cright%5C%7D)

## Early

## Partial parsing

有時理解一個句子，只需要大概瞭解到關鍵區域就行了，
或者你也可能者關注一些特定部分，所以不需要解出全部的數結構。

例如：假如只對人事物等感興趣，那只需要找NP就好了。

方法大概有：

* Rules-based
* HMM, MEMM
