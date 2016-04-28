# Syntactic Parsing

## SKY

先把Gammar都拆成 A -> BC形式，然後再對用`dp[start][end]`，
`dp[i][j]`紀錄的是字串從`i`到`j`有可能有哪些狀態。

![](https://latex.codecogs.com/gif.latex?dp%5Bi%5D%5Bj%5D%20%3D%20%5Cbigcup_%7Bk%7D%20%5Cleft%5C%7B%20A%20%7C%20A%3DBC%2C%20B%20%5Cin%20dp%5Bi%5D%5Bk%5D%2C%20C%20%5Cin%20dp%5Bk&plus;1%5D%5Bj%5D%20%5Cright%5C%7D)
