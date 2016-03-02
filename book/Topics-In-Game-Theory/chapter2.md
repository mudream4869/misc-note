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

**Definition**

x, y是n-Vector，我們說 x dom_S y，假如

![](https://latex.codecogs.com/gif.latex?
%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20
%5Csum_%7Bi%20%5Cin%20S%7Dx_i%20%5Cleq
%20v%28S%29%20%5C%5C%20x_i%20%3E%20y_i%20%5C%20
%5Cforall%20%5C%20i%20%5Cin%20S%20%5Cend%7Bmatrix%7D%5Cright.)

**Definition**

(N, v)稱*essential*假如

![](https://latex.codecogs.com/gif.latex?%5Csum_%7Bi%20%5Cin%20N%7D%20x_i%20%3C%20v%28N%29)



