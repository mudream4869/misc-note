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

## 台灣 TST 2011

![](https://latex.codecogs.com/gif.latex?k=%5Cfrac%7Ba%5E2%20&plus;%20b%5E2%20&plus;%206%7D%7Bab%7D%20%5Cin%20%5Cmathbb%7BN%7D)

證明：k是立方數

*pf* :

固定`k`，選一個**最小**解`(a, b)`，並且`a >= b`。

由跟與係數關係(重複上面推斷)，可以得到

![](https://latex.codecogs.com/gif.latex?b%20%5Cleq%20a%20%5Cleq%20%5Csqrt%7Bb%5E2%20&plus;%206%7D)

* `a = b` => a = b = 1 => k = 8
* `a = b+1` => 無解

## 羅馬尼亞 MO 2004

![](https://latex.codecogs.com/gif.latex?S%20%3D%20%5Cleft%5C%7B%20%5Cfrac%7Ba%5E2%20&plus;%20ab%20&plus;%20b%5E2%7D%7Bab-1%7D%20%5Cmid%20a%2C%20b%20%5Cin%20%5Cmathbb%7BN%7D%20%5Cright%5C%7D%20%5Ccap%20%5Cmathbb%7BN%7D)

找出S裡所有元素

*sol*:

先枚舉a, b < 4的解：`f(1, 2) = 7`、`f(2, 2) = 4`

設裡面某元素為`t`，可以得到：

![](https://latex.codecogs.com/gif.latex?a%5E2%20-%20%28bt-b%29a%20&plus;%20%28b%5E2%20&plus;%20t%29%20%3D%200)

讓`(a, b)`為最小解，且`a >= b > 3`

* `a + a' = bt - b` => a'是整數
* `aa' = bb + t` => 
    - `a'`是正數
    - `(a', b)`合法解
    - 因為`(a, b)`最小，所以`a' >= a`

        ![](https://latex.codecogs.com/gif.latex?a%20%5Cleq%20%5Csqrt%7Bb%5E2%20&plus;%20t%7D)
    
回到原式：

![](https://latex.codecogs.com/gif.latex?t%20%3D%20%5Cfrac%7Ba%5E2%20&plus;%20ab%20&plus;%20b%5E2%7D%7Bab%20-%201%7D%20%5Cleq%20%5Cfrac%7B3a%5E2%7D%7Bb%5E2%20-%201%7D%20%5Cleq%20%5Cfrac%7B3%28b%5E2%20&plus;%20t%29%7D%7Bb%5E2%20-%201%7D)

=> 

![](https://latex.codecogs.com/gif.latex?t%20%5Cleq%20%5Cfrac%7B3b%5E2%7D%7Bb%5E2%20-%204%7D%20%5Cleq%204)

* t = 1 => aa + bb = -1 : **impossible**
* t = 2 => aa - ab + bb = -2 : **impossible**
* t = 3 => (a-b)^2 = -3 : **impossible**
* t = 4 => ok

=> S = {4, 7}

## USA TST 2002

求出以下的所有解

![](https://latex.codecogs.com/gif.latex?%5Cfrac%7Ba%5E2%20&plus;%20b%5E2%7D%7Bab%20-%201%7D%20%5Cin%20%5Cmathbb%7BN%7D)

*sol*:

首先先處理 a, b < 3的所有解：`(1, 2)`

那用上面方法加上條件`a, b > 2`可以得到

![](https://latex.codecogs.com/gif.latex?t%20%3D%20%5Cfrac%7Ba%5E2%20&plus;%20b%5E2%7D%7Bab%20-%201%7D%20%5Cleq%20%5Cfrac%7B2b%5E2%7D%7Bb%5E2%20-%202%7D%20%5Cleq%203)

* t = 1, 2 => **no sol**
* t = 3 => `3 | a, 3 | b` but **impossible**

=> (a, b) = (1, 2)
