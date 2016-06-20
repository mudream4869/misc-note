# Deadlock

## 性質

* 必要條件

    1. Mutual Exclusion : 至少有一個資源在不可分享狀態下被拿住
    2. Hold and Wait : Pi在等待資源的同時握有其他資源
    3. No Preemption : 
    4. Circular Wait : Waiting chain is a cycle.

## 處理Deadlock

* **Deadlock Prevention** : 至少一個必要條件消失
* **Deadlock Avoidance**  : Process提供資訊，讓系統永遠處於一個安全狀態

### Prevention

定義一個 F : Resource -> N，並且Resource Request順序必須遞增

### Avoidance

簡單的模型：Use "count of available resource, count of allocated resource, max demands of process"

Banker's Algorithm

## 回復

* Select a victim
* Roll-Back
* Starvation
