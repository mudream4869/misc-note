# A history of the development of NTRU

[Slide](http://ec14.compute.dtu.dk/talks/6.pdf)

## a way function from NT

Legendre Symbol :

![](https://latex.codecogs.com/gif.latex?
%5Cleft%20%28%20%5Cfrac%7Ba%7D%7Bp%7D%20%5Cright%20%29%20%3D%20a%5E%7B%5Cfrac%7Bp-1%7D%7B2%7D%7D%20%5C%20%28mod%20%5C%20p%29)

用這函數，我們可以訂出一個函數，把一個正整數，轉成一串bit stream

![](https://latex.codecogs.com/gif.latex?
f%28D%29%20%3D%20%5C%7B%20%5Cleft%20%28%20%5Cfrac%7BD%7D%7Bp_1
%7D%20%5Cright%20%29%2C%20%5Cleft%20%28%20%5Cfrac%7BD%7D%7Bp_2
%7D%20%5Cright%20%29%20...%2C%20%5Cleft%20%28%20%5Cfrac%7BD%7D%7Bp_n%7D%20%5Cright%20%29%20%5C%7D)

並且，在給定`E = {e_1, e_2 ..., e_100000}`下，高機率至多一個`D`，使得`f(D) = E`。
並且由RH，`f(D)`分佈是很隨機且均勻的。

這在Cypto '88中被Damg ̊ard第一次提出，當作一個很強的`bit generator`。

## Enter function field

現在考慮Z/pZ[x]/g（其中g是首一既約多項式）
的Legendre Symbol的特殊狀況：g(x) = x - a，在這情況下：

![](https://latex.codecogs.com/gif.latex?
%5Cleft%20%28%20%5Cfrac%7Bf%7D%7Bx-a%7D%20%5Cright
%20%29%20%3D%20%5Cleft%28%20%5Cfrac%7Bf%28a%29%7D%7Bp%7D%5Cright%20%29)

不過，我們為何不直接考慮`f(a) (mod p)`呢？這裏我們會獲得一個問題

**Q2**

給public prime : q，secret polynomial : f，公開f(a_1) ... f(a_t) (mod p)

如此，這樣個問題，有很多`f'`也符合`f'(a_1) = f(a_1)`，
所以一個可行的解決辦法就是限制：對係數做限制。

**Definition**

給定 `1 <= c << p`，假如f裡面的係數`|a_i| <= c`，那f是*short*。
