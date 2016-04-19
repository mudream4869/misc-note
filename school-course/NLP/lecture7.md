# Lecture 7 : Part-of-Speech Tagging

## 選一個Tagset

* 可以選很粗超的，像是`N, V, Adj, Adv. ...`
* `Penn TreeBank tagset`
    
    | Tag | Description     | Example      |
    | --- | --------------- | ------------ |
    | CC  | coordin. conj   | and, but, or |
    | CD  | cardinal num    | one, two ... |
    | ... | ...             | ...          |

## 各種Tag方法

* Ruled-based
* Stochastic
    * HMM
    * MEMM
* Transformation-BasedTagger
* ...

## Ruled-base

通常會需要超過1000條手寫規則

## HMM

word -> observation
tag  -> status

然後求max

![](https://latex.codecogs.com/gif.latex?T%20%3D%20%5Cmax_T%20%5Cprod%20P%28word_i%20%7C%20tag_i%29%20%5Cprod%20P%28tag_i%20%7C%20tag_%7Bi-1%7D%29)

# MEMM

Max Entropy Markov Models

![](https://latex.codecogs.com/gif.latex?T%20%3D%20%5Cmax_T%20%5Cprod%20P%28tag_i%20%7C%20word_i%2C%20tag_%7Bi-1%7D%29)
