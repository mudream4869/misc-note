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

# Semantic Role(語意角色)

* John(agent) hit Bill(patient).
* 主要有這些：Agent（施事者）、patient（受事者）、Instrument（工具格）、Goal（目標）...
* 資料庫：
    - FrameNet
    - Chinese PropBank
        * [arg0我][argm-adv已經][rel打][arg1電話][arg2給斯恩特]
        * [arg1這些算盤][arg0 產業界自己][rel打]的[argm-ext最精]

# Pragmatics

* 研究某句話的意思，還有要表達的東西
* 研究某些識別字的有效範圍（Scope）。

* Speech Act
    
    | Utterance                     | Speech Act   |
    | ----------------------------- | :----------: |
    | 我想要掛眼科門診。            |Elaborate-fact|
    | 請問要在總院看還是公館分部看? |Request-ref   |
    | 總院。                        |Answer-ref    |
    
    * 做到 **Dialog Tagging**

* Anaphoric Relations
    
    * 小9是個小蘿莉。
        * 同指涉是`小9`和`小蘿莉`
    * 現在氣溫是25度
        * 同指涉是`現在氣溫`和`25度`

* Discourse Analysis
    
# 一些結論

NLP是神馬？

* 大多是標記轉換，像是：
    - English sentence -> Chinese sentence
    - long text -> short text  (Summ)
    - sound wave -> text string
* 增加一些資訊，像是semantic labeling
* 小部分是理論
* 有些是工程（*engineering*）

# 獲取知識的瓶頸

提供一個大型的知識庫困難且耗時

* 一些資料庫進行式

    - WordNet [Fellbaum, 1998]
    – Open Mind Word Expert [Chklovski & Mihalcea, 2002] – EuroWordNet [Vossen, 1998]
    – Multilingual Central Repository [Atserias et al. 2004]
    – The WordNetPlus project [Boyd-Graber et al., 2006]
    – OntoNotes [Hovy et al., 2006]
    – Wikipedia (collaborative effort)
    – Wiktionary (collaborative effort)
    – Omega Wiki (collaborative effort)

