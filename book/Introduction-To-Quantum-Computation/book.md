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
