# Vieta Jump

一個用根與係數關係的數論解題方式

## IMO 1988 P6

![](https://latex.codecogs.com/gif.latex?k%20%3D%20%5Cfrac%7Ba%5E2%20&plus;%20b%5E2%7D%7Bab%20&plus;%201%7D%20%5Cin%20%5Cmathbb%7BN%7D)

證明k是平方數

*pf* :

首先先固定非平方數`k`

![](https://latex.codecogs.com/gif.latex?
S_k%20%3D%20%5C%7B%20%28a%2C%20b%29%20%5Cin
%20%5Cmathbb%7BN%7D%5E2%20%5C%20%7C%20%5C%20
%5Cfrac%7Ba%5E2%20&plus;%20b%5E2%7D%7Bab%20&plus;
%201%7D%20%3D%20k%20%5C%7D)

假如 |S| > 0, 那就從裡面挖出一個**最小**(定義為`v((a, b)) = a+b`)的解 `(a, b)`，並且讓 `a >= b`

改寫式子：

![](https://latex.codecogs.com/gif.latex?a%5E2%20-%20%28kb%29a%20&plus;%20%28b%5E2%20-%20k%29%20%3D%200)

可以知道存在`b'`，使得

* a + b' = kb => b'是整數

* a(b') = bb - k =>

    因為(a, b)最小
    
    ![](https://latex.codecogs.com/gif.latex?%28b%27%2C%20b%29%20%5Cin%20S_k%20%5CRightarrow%20a%20%5Cleq%20b%27)

    ![](https://latex.codecogs.com/gif.latex?a%5E2%20%5Cleq%20ab%27%20%3D%20b%5E2%20-%20k)
    
    如此推出`a < b`矛盾
    
