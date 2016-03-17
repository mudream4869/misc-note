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
