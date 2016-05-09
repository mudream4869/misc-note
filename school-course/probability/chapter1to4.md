# Chapter1 : Event, Sample, Space, and Probability

* P(A|B) := P(AB)/P(B)
* If P(A|B) = P(A), then call A, B *independent*

[Monty Hall Problem](http://math.ucsd.edu/~crypto/Monty/montybg.html)

## Law of Total Probability

![](https://latex.codecogs.com/gif.latex?P%28A%29%20%3D%20%5Csum_n%20P%28A%20%5Ccap%20B_n%29)

# Chapter2 : Random variable

## Probability Mass Function(PMF)

p_0(x_0) 定義成 Random variable = x_0 的機率

* Sum p_0(x) = 1
* p_0 in [0, 1]

## Expectation and Conditional Expectation

* 期望值: 
    * E(X) = sum x * p(x)
    * E(g(X)) = sum g(x) * p(x)

* 條件期望值: E(g(X) | A) = sum g(x) * p(x | A)

* EX: 當 g(x) = (x - E(x))^2

   ![](https://latex.codecogs.com/gif.latex?E%28g%28X%29%29%20%3D%20E%28%28X%20-%20E%28X%29%5E2%29%29%20%3D%20E%28X%29%5E2%20-%20E%28X%5E2%29)

* E(x^r)稱為  **rth moment of the distribution about origin**

* Moment-Generating Function : `f(t) = E(e^tx)`

## CDF

* `F(x) = P(X <= x)`

## PDF

* `f(x) = F'(x)`

# Chapter3 : 

## *s* Transform

   ![](https://latex.codecogs.com/gif.latex?f_x%5ET%28s%29%20%3D%20E%28e%5E%7B-sx%7D%29%20%3D%20%5Cint_%7B-%5Cinfty%7D%5E%7B%5Cinfty%7De%5E%7B-sx%7Df%28x%29%5Cmathrm%7Bd%7Dx)

* E(X)

   ![](https://latex.codecogs.com/gif.latex?E%28x%29%20%3D%20-%20%5Cleft%5B%20%5Cfrac%7B%5Cmathrm%7Bd%7D%20f_x%5ET%28s%29%7D%7B%5Cmathrm%7Bd%7D%20s%7D%20%5Cright%5D_%7Bx%20%3D%200%7D)

* E(X^2)

   ![](https://latex.codecogs.com/gif.latex?E%28x%5E2%29%20%3D%20%5Cleft%5B%20%5Cfrac%7B%5Cmathrm%7Bd%5E2%7D%20f_x%5ET%28s%29%7D%7B%5Cmathrm%7Bd%7D%20s%5E2%7D%20%5Cright%5D_%7Bx%20%3D%200%7D)

* E((X - E(X))^2) = E(X^2) - E(X)^2


## *z* Transform

![](https://latex.codecogs.com/gif.latex?p_x%5ET%28z%29%20%3D%20E%28z%5Ex%29%20%3D%20%5Csum%20z%5Ex%20p%28x%29)

* E(X)

   ![](https://latex.codecogs.com/gif.latex?E%28X%29%20%3D%5Cleft%5B%20%5Cfrac%7B%5Cmathrm%7Bd%7D%20p_x%5ET%7D%7B%5Cmathrm%7Bd%7D%20x%7D%20%5Cright%20%5D_%7Bx%20%3D%201%7D)

* E(X^2)
   
   ![](https://latex.codecogs.com/gif.latex?E%28X%5E2%29%20%3D%5Cleft%5B%20%5Cfrac%7B%5Cmathrm%7Bd%7D%20p_x%5ET%7D%7B%5Cmathrm%7Bd%7D%20x%7D%20&plus;%20%5Cfrac%7B%5Cmathrm%7Bd%7D%5E2%20p_x%5ET%7D%7B%5Cmathrm%7Bd%7D%20x%5E2%7D%5Cright%20%5D_%7Bx%20%3D%201%7D)

## Composition

* A物品的重量分佈*s Transform*為`f`，A物品的數量分佈*z Transform*為`p` ==> 總共重量為 `p(f(x))`
* A物品裡B的數量分佈*z Transform*為`p`，B物品的裡C的數量分佈*z Transform*為`q` ==> 總共重量為 `p(q(x))`

## 獨立的和

x, y獨立

* E(X+Y) = E(X) + E(Y)
* E(XY) = E(X)E(Y)
* sig(x+y)^2 = sig(x)^2 + sig(y)^2

# Chapter4 :

## The Bernoulli Process

一個離散，每次成功機率固定的過程

* 長度

    - `P(L = l) = p(1-p)^(l-1)`
    - `Ptrans(z) = zp/(1 - z + zp)`
    - `E(L) = 1/p`
    - `Sig = (1-P)/P^2`

* 數量
    
    - `P(N = k) = (Cn取k)p^k (1-p)^(n-k)`
    - `Ptrans(z) = (1 - P + zP)^k`
    - `E(N = k) = kp`
    - `Sig = kp(1-p)`

## Poisson Distributions

給訂一段時間，平均`lambda`人，求來的人的分佈數量

![](https://latex.codecogs.com/gif.latex?P%28k%20%5C%20event%20%5C%20occurs%29%20%3D%20%5Cfrac%7B%5Clambda%5Eke%5E%7B-%5Clambda%7D%7D%7Bk%21%7D)

* 假設一：下一個的人和這一個來的人獨立
* 假設二：確實有一個人來的機率 ~ delta t
* 假設三：

## Exponential Distribution

問兩個arrival間隔多久？

![](https://latex.codecogs.com/gif.latex?F%28w%29%20%3D%20P%28W%20%5Cleq%20w%29%20%3D%201%20-%20P%28no%20%5C%20arrival%20%5C%20at%20%5B0%2C%20w%5D%29%20%3D%201%20-%20e%5E%7B-%5Clambda%20w%7D)

![](https://latex.codecogs.com/gif.latex?F%27%28w%29%20%3D%20%5Clambda%20e%5E%7B-%5Clambda%20w%7D)

## Gamma Distribution

第alpha個arrival

F(w) = P(W <= w) = 1 - P(少於alpha個arrival在[0, w]) 
