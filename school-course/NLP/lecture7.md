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
* Transformation-BasedTagger
* ...

## HMM

word -> observation
tag  -> status

然後求max
