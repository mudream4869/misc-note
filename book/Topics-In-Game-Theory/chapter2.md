# n-Person Cooperative Games in Characteristic Function Form

## 介紹

多人合作遊戲：多人一起努力，然後獲得東西的遊戲。

**Definition**

讓N是Player的集合，定義

![](https://latex.codecogs.com/gif.latex?v%20%3A%202%5EN%20%5Crightarrow%20%5Cmathbb%7BR%7D)

並且在v(empty) = 0的條件下，v稱作*characteristic function*，
(N, v)稱作*game in characteristic function form*

**Definition**

若對於每個*disjoint pair*(S, T)，v(S) + v(T) <= v(S+T)，
那這*game*就稱作*superaddivtive*

**Definition**

(N, v)是遊戲，`x = (x_1, x_2, ..., x_n)`是*imputation* 假如

![](https://latex.codecogs.com/gif.latex?
%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20x_1%20&plus;
%20...%20x_n%20%3D%20v%28N%29%20%5C%5C%20x_i
%20%5Cgeq%20v%28i%29%20%5C%20%5Cforall%20%5C%20i
%20%5Cin%20N%20%5Cend%7Bmatrix%7D%5Cright.)

> 合作後更好的利益分配方法

**Definition**

x, y是n-Vector，我們說 x dom_S y，假如

![](https://latex.codecogs.com/gif.latex?
%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20
%5Csum_%7Bi%20%5Cin%20S%7Dx_i%20%5Cleq
%20v%28S%29%20%5C%5C%20x_i%20%3E%20y_i%20%5C%20
%5Cforall%20%5C%20i%20%5Cin%20S%20%5Cend%7Bmatrix%7D%5Cright.)

> 在S底下，x合作模式優先於y

**Definition**

(N, v)稱*essential*假如

![](https://latex.codecogs.com/gif.latex?%5Csum_%7Bi%20%5Cin%20N%7D%20x_i%20%3C%20v%28N%29)

## Stable Set 

在某些遊戲裡，會有*穩定的合作集合*，像，假如有遊戲是這樣：

`v(1, 2, 3) = 10, v(1, 3) = 10, v(other) = 0`

那利益分配必然只長得像這樣：`(a, 0, 10-a)`

以下是**Stable Set**的定義：

**Definition**

A nonempty set K of *imputation* is said to be stable if it satisfies:

- x, y in K => neither x, y dominate the other
- z is *imputation* not in K => exist x in K s.t. x dom z

## 遊戲的策略等價與標準化

對一個遊戲做線性變化不會影響其策略。固定正數`c`和常數`a_i`，作出以下變換：

![](https://latex.codecogs.com/gif.latex?v%27%28S%29%20%3D%20cv%28S%29%20&plus;%20%5Csum_%7Bi%20%5Cin%20S%7Da_i)

其遊戲策略和原本一樣。

所以，我們可以用這種調整方法達到：

![](https://latex.codecogs.com/gif.latex?
%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20v%28i%29%20%3D%200%20%5C%20
%5Cforall%20%5C%20i%20%5Cin%20N%20%5C%5C%20v%28N%29%20%3D%201%20%5C%20
%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5Cend%7Bmatrix%7D%5Cright.)

稱作*(0, 1)-normalization*

### 特殊型：三人遊戲

舉個例子：`v(1, 2, 3) = 1, v(1, 2) = 0.6, v(1, 3) = 0.7, v(2, 3) = 0.5, v(1) = v(2) = v(3) = 0`

假如(x, y, z)是Stable，那

- x + y >= 0.6
- y + z >= 0.5
- x + z >= 0.7

衍生出來： `x <= 0.5, y <= 0.7, z <= 0.4`，
使用**Ternary plot**(待補)，可以發現他在三角形裡面生出一個**Core**
