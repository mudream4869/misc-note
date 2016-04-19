# N-grams Models

給`n-1`個Word，猜下一個Word

## Word Prediction

* 給一個句子：`So I notice ...`有以下2-gram: `So I`, `I notice`...

## Application

* 自動語音辨識
* 手寫辨識
* 拼音校正
* 翻譯

EX :

- Input: 在日本,大學生打工的情況是相當普*偏*的。 Output: 遍
- Input: 他是我*的*以前的室友 output: Redundant ("的")

* 給一個文章，判斷是誰寫的

##  Count

* 到底要不要數`.,`
* 說話：`I do main- mainly...`
    * 現象：
        - 詞彙重複（學習上會是noise）
        - 修正前面說錯的
        - 停頓
    * 有時候現象有用：像是停頓在對話

* Type and Token
    * `the`要不要算？

### Corpora 語料庫

* Google Web Crawl

    * Acronyms
    * Misspelling
    * etc

## 回到 Word Counting

![](https://latex.codecogs.com/gif.latex?
P%28w_n%20%7C%20w_1...w_%7Bn-1%7D%29%20%3D%20P%28%7Bw_1...w_n%7D%29/P%28%7Bw_1...w_%7Bn-1%7D%7D%29)

* 但是我們可能會獲得`0/0`
* Chain rule ?

![](https://latex.codecogs.com/gif.latex?
P%28w_1w_2w_3%29%20%3D%20P%28%7Bw_1w_2w_3%7D%29/P%28w_1w_2%29%20%5Ctimes%20P%28w_1w_2%29/P%28w_1%29%20%5Ctimes%20P%28w_1%29)

* 或者，我們做些簡化

P(w_n | w_1...w_{n-1}) ~ P(w_n | w_{n-1}) ?

* The Maximum Likelihood Estimate (MLE)

## Berkeley Restaurant Project Sentences

2-gram

|      | I    | want | to   | eat  |
| ---- | ---- | ---- | ---- | ---- |
|  I   | 5    | 827  | 0    | 9    |
| want | 2    | 0    | 608  | 1    |
| to   | 2    | 0    | 4    | 686  |

...

* 估計一個句子的機率


   P(I want to eat english food)
   = P(I | start of sentence)P(want | I)...
   
   * Shannon’s Method 生出一個可能性大的字句

* 發現一些特殊點：
   
   * P(english | want) < P(chinese | want) ==> 偏好
   * P(to | want) > 0.5 ==> 語法等
   * P(I | start of sentence)

### Shannon's Method

* 隨便生一個(start, w)
* 然後按照f(x) = P(w->x)的機率找(w, x)
* 直到(x, end)

## Perplexity

計算驚訝的程度，測量模型的好壞

定義：

![](https://latex.codecogs.com/gif.latex?PP%28W%29%20%3D%20%5Csqrt%5BN%5D%7B%5Cfrac%7B1%7D%7BP%28w_1w_2...w_N%29%7D%7D)

在bigram裡則會簡化為

![](https://latex.codecogs.com/gif.latex?PP%28W%29%20%3D%20%5Csqrt%5BN%5D%7B%5Cprod_%7Bi%20%3D%201%7D%5E%7BN%7D%5Cfrac%7B1%7D%7BP%28w_i%20%7C%20w_%7Bi-1%7D%29%7D%7D)

越小的PP代表Model越好

## log space

P_1 P_2 P_3 = e ^ {log P_1 log P_2 log P_3}

## Google N-Gram Release

