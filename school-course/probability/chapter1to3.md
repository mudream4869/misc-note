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



