# Quantum Systems

## Hilbert Space

一個複數內積空間，定義為：

*ket vector* 定義為

![](https://latex.codecogs.com/gif.latex?
%7C%20%5CPsi%20%5Crangle%20%3D%20%5Cbegin%7Bbmatrix%7D%20
c_0%20%5C%5C%20%5Cvdots%20%5C%5C%20c_%7Bn-1%7D%20%5Cend%7Bbmatrix%7D)

*bra vector* 定義為

![](https://latex.codecogs.com/gif.latex?
%5Clangle%20%5CPsi%20%7C%20%3D%20%7C%20%5CPsi%20%5Crangle%20%5E%20%5Cdagger)

*Inner Product* 定義為

![](https://latex.codecogs.com/gif.latex?%5Clangle%20%5CPsi%20%7C%20%5CPsi%20%5Crangle)

## Qubit

在*Quantum System*里，資訊是用*Quantum state*所表示，像是

* spin of a electron
* polarization of a photon

以上都有兩種狀態。

Qubit和傳統的bit量測時，都只會出現一種state，不一樣的地方，是在他們沒被量測的時候。
在Qubit沒被量測時，他是兩個State的疊加，可以用*ket vector*表示，稱為*state vector*。

一個Qubit可以寫作：

![](https://latex.codecogs.com/gif.latex?
%7C%5CPsi%20%5Crangle%20%3D%20%5Cbegin%7Bbmatrix%7D%20
w_0%20%5C%5C%20w_1%20%5Cend%7Bbmatrix%7D)

並且長度為`1`：

![](https://latex.codecogs.com/gif.latex?%5Clangle%20%5CPsi%20%7C%20%5CPsi%20%5Crangle%20%3D%201)

## Register

在傳統電腦，記憶體是一個bit的陣列，在量子電腦，是好幾個Qubit的組合。
考慮一個`n` state的系統，Hilbert Space裡有`n`個垂直軸。
並且，我們再測量時，state只會是其中一個，而不是疊加態。

![](https://latex.codecogs.com/gif.latex?
%7C%20%5CPsi%20%5Crangle%20%3D%20
%5Csum_%7Bk%3D0%7D%5E%7Bn-1%7Dw_k%20%7C%20%5Cphi_k%20%5Crangle)

## Time evolution of quantum system

Schrödinger equation：

![](https://latex.codecogs.com/gif.latex?
%5Cfrac%7Bd%7D%7Bdt%7D%20%7C%20%5CPsi%28t%29%20%5Crangle%20%3D%20-iH%20%7C%20%5CPsi%28t%29%20%5Crangle)

可得到

![](https://latex.codecogs.com/gif.latex?
%7C%20%5CPsi%28t%29%20%5Crangle%20%3D%20U%28t%29%20%7C%20%5CPsi%280%29%20%5Crangle)

其中`U(t)` 是 Unitary operator

現在我們考慮在Quantum System裡的gate，由上面可得知，
任何gate都可以寫成一個unitary operator。

## Measurement

考慮測量一個Qubit，Quantum Measurement可以用一堆*measure operator*:`{M_n}`描述，
並且，第`i`種測量出現的機率是

![](https://latex.codecogs.com/gif.latex?p%28i%29%20%3D%5Clangle%20%5CPsi%20%7C%20M_i%5E%5Cdagger%20M_i%20%7C%20%5CPsi%20%5Crangle)

並且測量完後，該系統會崩潰成

![](https://latex.codecogs.com/gif.latex?%5Cfrac%7BM_i%20%7C%20%5CPsi%20%5Crangle%7D%7B%5Csqrt%7Bp%28i%29%7D%7D)

## Multi-qubit system

表為tensor product

![](https://latex.codecogs.com/gif.latex?%7C%20%5Cphi%20%5Crangle%20%3D%20%7C%20%5Cphi_1%20%5Crangle%20%5Cotimes%20
...%20%5Cotimes%20%7C%20%5Cphi_n%20%5Crangle%20%3D%20%7C%20%5Cphi_1%20%5Crangle%20...%20%7C%20%5Cphi_n%20%5Crangle)

# Quantum Algorithm

## Deutsch' Algorithm

考慮`f:{0, 1} -> {0, 1}`，在一般情況下，
我們需要訪問`f`兩次才有辦法知道`f(1) = f(0)`還是`f(1) =/= f(0)`。

現在我們考慮 U unitary

![](https://latex.codecogs.com/gif.latex?
U_f%20%3A%20%7C%20x%20%5Crangle%20%7C%20y%20%5Crangle
%20%5Crightarrow%20%7C%20x%20%5Crangle%20%7C%20y%20%5Coplus%20f%28x%29%20%5Crangle)

使用這operator，就會發現

![](https://latex.codecogs.com/gif.latex?
%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%28%7C%200%20%5Crangle%20&plus;
%20%7C%201%20%5Crangle%29%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%28%7C%200%20%5Crangle
%20-%20%7C%201%20%5Crangle%29%20%5Crightarrow%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%28%28-1%29%5E%7Bf%280%29%7D%7C%200%20%5Crangle
%20&plus;%20%28-1%29%5E%7Bf%281%29%7D%7C%201%20%5Crangle%29%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%28%7C%200%20%5Crangle
%20-%20%7C%201%20%5Crangle%29)

## Deutsch - Jozsa Algorithm

接下來就是Deutsch Algorithm的進階版，考慮`f: n bits -> {0, 1}`，
已知f要嘛是常數，要嘛`f(x) = 0`的解個數等於`f(x) = 1`的解個數。

以下演算法用到`H` Hadamard transform

![](https://latex.codecogs.com/gif.latex?
%5Clarge%20H_n%20%7C%20i%20%5Crangle%20%3D%20
%5Csum_%7Bj%7D%20%5Cfrac%7B%28-1%29%5E%7Bi%20%5Ccdot
%20j%7D%7D%7B%5Csqrt%7B2%20%5En%7D%7D%20%7C%20j%20%5Crangle)

1. Step1 : 設置系統為

    ![](https://latex.codecogs.com/gif.latex?
%5Clarge%20%7C%20%5Cphi_0%20%5Crangle
%20%3D%20%7C%200%20%5Crangle%20%5E%7B%5Cotimes%20n%7D%20%7C%201%20%5Crangle)

2. Step2

    ![](https://latex.codecogs.com/gif.latex?
%7C%20%5Cphi_1%20%5Crangle%20%3D%20H_n%20%28%7C%200%20%5Crangle
%20%5E%7B%5Cotimes%20n%7D%29%20H_1%28%7C%201%20%5Crangle%29%20%3D%20
%5Csum_%7Bx%20%5Cin%20%5C%7B%200%2C%201%20%5C%7D%5En%7D%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%7D%7D%20%7C%20x%20%5Crangle
%20%5Cleft%5B%20%5Cfrac%7B%7C0%20%5Crangle%20-%20%7C%201%20%5Crangle%20%7D%7B%5Csqrt%7B2%7D%7D%20%5Cright%20%5D)

3. Step3 : 使用`U_f`

    ![](https://latex.codecogs.com/gif.latex?
%7C%20%5Cphi_2%20%5Crangle%20%3D%20
%5Csum_%7Bx%20%5Cin%20%5C%7B%200%2C%201%20%5C%7D%5En%7D%20
%5Cfrac%7B%28-1%29%5E%7Bf%28x%29%7D%7D%7B%5Csqrt%7B2%7D%7D%20%7C%20x%20%5Crangle
%20%5Cleft%5B%20%5Cfrac%7B%7C0%20%5Crangle%20-%20%7C%201%20%5Crangle%20%7D%7B
%5Csqrt%7B2%7D%7D%20%5Cright%20%5D)

4. 然後我們再 apply `H_n`

    ![](https://latex.codecogs.com/gif.latex?
%7C%20%5Cphi_3%20%5Crangle%20%3D%20
%5Csum_%7Bx%20%5Cin%20%5C%7B%200%2C%201%5C%7D%5En%7D
%5Csum_%7Bz%20%5Cin%20%5C%7B%200%2C%201%20%5C%7D%5En%7D%20
%5Cfrac%7B%28-1%29%5E%7Bf%28x%29%20&plus;
%20x%20%5Ccdot%20z%7D%7D%7B%5Csqrt%7B2%7D%7D%20%7C%20x%20%5Crangle
%20%5Cleft%5B%20%5Cfrac%7B%7C0%20%5Crangle%20-%20%7C%201%20%5Crangle
%20%7D%7B%5Csqrt%7B2%7D%7D%20%5Cright%20%5D)

5. 考察`0^n`的機率強度

    * 假如`f(x)`是常數，則強度為`-1`或者`+1`
    * 否則是`0`
