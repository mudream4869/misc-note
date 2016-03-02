# Two-Person, Zero-Sum, Finite Matrix Games

## 簡介

Player1和Player2各有`n`, `m`個選擇，
有一個矩陣A(i, j)描述著Player1和Player2做出選擇
（Player1選擇`i`, Player2選擇`j`）後，
Player1會獲得多少錢

像是假如矩陣長這樣：

![](https://latex.codecogs.com/gif.latex?%5Cbegin%7Bbmatrix%7D%201%20%26%202%5C%5C%203%20%26%204%20%5Cend%7Bbmatrix%7D)

那當Player1選1且Player2選1的時候，Player2要給Player1`1`

## Minimax策略

在上面的例子，假如Player1選擇1的話，那他至少可以獲得`1`
，選擇2的話，至少可以獲得`3`，所以在這策略下，Player1會選擇2。
就是**先對每個row取最小值**，再看哪一行的最小值最大。

Player2則是要相反，不過可以看成取負號在做一樣操作。

### 特殊情況

在某些時候，Player1取到的最大值會和
Player2取道的最小值一樣。一開始的例子就是。

## 混合策略



