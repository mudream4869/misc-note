# Top-Down Approach

`Morphological Processing` => `Syntactic Analysis` => `Semantic Interpretation` => `Content`

* Morphological(型態) Analyzer
    - find root of words, eg : going -> go

* **Part of Speech** Tagger

    **Part of Speech** : 具有類似語法性質的一堆單字
    
    | Part of Speech(symbol) | 例子          |
    | :--------------------: | :------------ |
    | Noun                   | dog, concerts |
    | Possessive             | my, your      |

    * 其實還可以更細

# Context Free Grammars

* Examples' rule 
    - majority sentence -> s fpunc
    - s -> np vp
    - vp -> verb
    - np -> det noun

* 模糊
    - np -> det noun noun
    - vp -> verb np np


