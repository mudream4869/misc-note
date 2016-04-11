# Chapter1 : Event, Sample, Space, and Probability

* P(A|B) := P(AB)/P(B)
* If P(A|B) = P(A), then call A, B *independent*

# Chapter2 : Random variable

## Probability Mass Function

p_0(x_0) 定義成 Random variable = x_0 的機率

* Sum p_0(x) = 1
* p_0 in [0, 1]

## Expectation and Conditional Expectation

* 期望值: 
    * E(X) = sum x * p(x)
    * E(g(X)) = sum g(x) * p(x)

* 條件期望值: E(g(X) | A) = sum g(x) * p(x | A)

* EX: 當 g(x) = (x - E(x))^2

![](https://latex.codecogs.com/gif.latex?
E%28g%28X%29%29%20%3D%20E%28%28X%20-%20E%28X%29%5E2%29%29%20%3D%20E%28X%29%5E2%20-%20E%28X%5E2%29)
   
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

## Composition

* A物品的重量分佈*s Transform*為`f`，A物品的數量分佈*z Transform*為`p` ==> 總共重量為 `p(f(x))`
* A物品裡B的數量分佈*z Transform*為`p`，B物品的裡C的數量分佈*z Transform*為`q` ==> 總共重量為 `p(q(x))`

# Chapter4 :

## The Bernoulli Process

### Interval

## The Poision Process

### Interval
