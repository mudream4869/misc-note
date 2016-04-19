# Collocations and Multiword Expressions

* Collocations : 哪些詞容易和哪些詞搭配
* Multiword Expression : 片語
* N-gram : N個字所形成的字串是不是有某些概念

## Collocation

**Collocation**（搭配詞）, 由兩個自或多個字所組合而成，並且有**特殊意義**

- `大蘋果`，一般意思是很大的蘋果，可是若有A市，指的是地名或者就是蘋果，
  那就是特殊意義。

- `green house`

定義：一串字，且不可配切割、替代。

## Multiword Expression

- idiom : kick the bucket(氣絕)
- compound noun : post office
- proper names : San Francisco

* 固定表達 : in short(O), in shorter(X)

* 有一些**Workshop**

## 尋找方法？

### 頻率法

1. 尋找常出現的組合（quantitative techique）
1. 依照詞性(POS)過濾

| Tag Pattern | Example           | 
| ----------- | ----------------- |
| A N         | linear function   |
| N N         | regression coff   |
| N P N       | degree of freedom | 


### 平均和變異數

* 這種方法對於固定的片語很方便，可有些有非固定的距離。

* EX : 
    - She *knocked* on his *door*. (distance = 2)
    - A man *knocked* on the metal front *door*. (distance = 4)

* **bigrams at a distance**
* 枚舉distance, position
* 尋找距離變異數小的

### 猜想驗證

前面的方法尋找後，有可能變異小的只是巧合。

* t-Test

    把測試文章當作一種抽樣
    
    ![](https://latex.codecogs.com/gif.latex?t%20%3D%20%5Cfrac%7B%5Cbar%7Bx%7D%20-%20%5Cmu%7D%7B%5Csqrt%7B%5Cfrac%7Bs%5E2%7D%7BN%7D%7D%7D)

* Null Hypothesis
    檢驗 P(ab) =? P(a)P(b) (也就是是否沒有關係)

* Pearson’s Chi-Square test

* Joint Entropy and Conditional Entropy

### t-Test Example

* 一個文章裡面有`14307668`個詞
* *new* 出現`15828`次
* *companies*出現`4675`次
* *new companies*出現`8`次

![](https://latex.codecogs.com/gif.latex?P%28new%29%20%3D%20%5Cfrac%7B15828%7D%7B14307668%7D)

![](https://latex.codecogs.com/gif.latex?P%28companies%29%20%3D%20%5Cfrac%7B4675%7D%7B14307668%7D)

假設*new*和*companies*沒有關係，那麼分佈會是

![](https://latex.codecogs.com/gif.latex?%5Cmu%20%3D%20P%28new%29P%28companies%29%20%3D%203.615%20%5Ctimes%2010%5E%7B-7%7D)

而我們所觀察到的*new companies*

![](https://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D%20%3D%20%5Cfrac%7B8%7D%7B14307668%7D%20%3D%205.591%20%5Ctimes%2010%5E%7B-7%7D)

![](https://latex.codecogs.com/gif.latex?s%5E2%20%3D%20p%281-p%29%20%5Capprox%20p%20%3D%205.591%20%5Ctimes%2010%5E%7B-7%7D)

可以得到

![](https://latex.codecogs.com/gif.latex?t%20%3D%200.99932)

因為`0.999932` < `2.576`，所以我們無法反駁**new和companies沒有關係**這句話。

## Emotion Analysis

* Yahoo Emotion

```
Sentence  = w + w + Ew + ...
```

* Emotion e = {e_1, ..., e_m}
* Word w = {w_1, ..., w_n}
* Es(w_i) = {es_i1, ..., es_ik} 

Sentence = w + Sad + w + Ha + :)

### Method evulation

* Tag = {`neg`, `pos`} : 
    
    * Use `svm`
    * Sentence Classifire
