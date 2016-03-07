恩... 在看論文看到的一些方法

# A Latent Source Model for Nonparametric Time Series Classification

## Weighted Majority Voting and Nearest-Neighbor Classification

首先給一堆時間序列的資料（s : Z -> R），每筆時間序列都會有一個標籤:(`1`或`-1`)。

**Definition**

兩個vector相似性定義如下：

![](https://latex.codecogs.com/gif.latex?d%28x%2C%20y%29%20%3D%20%5Csum%7B%7Cx_i%20-%20y_i%7C%5E2%7D)

不過考慮到資料具有**時間**這項特性，定義改為：

![](https://latex.codecogs.com/gif.latex?
d%5ET%28r%2C%20s%29%20%3D%20%5Cmin_%7B%5CDelta%20%5Cin%20%5B%20-
%5CDelta_%7Bmax%7D%2C%20%5CDelta_%7Bmax%7D%5D%20%7D%20%5Csum_%7Bi%20%3D%201%7D%5ET%7B%7Cr%28i&plus;
%5CDelta%29%20-%20s%28i%29%7C%5E2%7D)

- Weigthed Majority Voting
    
    ![](https://latex.codecogs.com/gif.latex?%5Cwidehat%7BL%7D%5ET%28s%3B%5Cgamma
    %29%20%3D%20%5Cleft%5C%7B%5Cbegin%7Bmatrix%7D%20&plus;1%20%5C%20%5Csum_%7Br%20%5C%20label
    %20&plus;1%7D%20e%5E%7B-%5Cgamma%20d%5ET%28r%2C%20s%29%7D%20%5Cgeq%20%5Csum_%7Br%20%5C%20label
    %20-1%7D%20e%5E%7B-%5Cgamma%20d%5ET%28r%2C%20s%29%7D%20%5C%5C%20-1%20%5C%20%5C%20%5C%20%5C%20%5C%20
    %5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C
    %20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20
    %5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5C%20%5Cend%7Bmatrix%7D%5Cright.)

- Nearest-neighbor classifer

    直接用相似性定義距離，看和哪個Label距離近，就用哪個Label，記做
    ![](https://latex.codecogs.com/gif.latex?%5Cwidehat%7BL%7D%5ET_%7BNN%7D%28s%29)
