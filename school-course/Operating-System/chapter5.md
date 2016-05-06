# Process Scheduling

* CPU-bound prog 需要 **一些** **長**時間的CPU爆發
* IO-bound prog  需要 **很多** **短**時間的CPU爆發

```
New ==> CPU-Burst <==> IO-Burst ==> Terminate
```

所以需要好好的規劃

## CPU Scheduling

* Nonpreemptive Scheduling

    一個process*CPU直到滿足，優點是容易實作。

* Preemptive Scheduling

    需要注意的Issue是：
    
    - Protection of Resources
    - Synchronization

## Scheduling Criteria(標準)

因為不同的Scheduling可能會偏好不同的Prog，所以需要訂共通標準

* CPU Utilization (利用率)
* Throughput (吞吐率，處理能力)
* Turnaround Time = Completion Time - Start Time
* Waiting Time = Waiting in Ready Queue
* Response Time = First Response Time

## Scheduling Algorithms

- First in First out
    - Shortest-Job-First
    - Prioirty Scheduling
- Round-Robin
- Multilevel

### First in First out

Nonpreemptive，變形後有 Shortest-Job-First和Priority-First

#### Shortest Job First

分有**Nonpreemptive**和**Preemptive**

*Preemptive*: 最短殘留時間優先

| Process | CPU Time | Arrival Time |
|:-------:|:--------:|:------------:|
| P1      | 8        | 0            |
| P2      | 4        | 1            |
| P3      | 9        | 2            |
| P4      | 5        | 3            |

```
 P1 P2 P4  P1  P3
0  1  5  10  17  26
```

#### Prioirty Scheduling

某種形式上算是 SJF 和 FIFO 的廣義版本

* FIFO : priority = Constant
* SFJ  : priority =  -(CPU Burst Time)

有不同的Prioirity給予方法，從內部（像是依照打開檔案的個數）或者外部（OS自己定義好）。

主要可能出現問題會有可能性的永久停滯（Starvation），解決方法是把等待時間加入Priority考慮。

## Round-Robin(RR)

每經過一些時間，不管Process如何，就直接Switch。為了公正的Time sharing而生。

## Multilevel Queue

像是Foregournd和Background就有不同的優先權，可以這樣做：分配20%給Background，80%給Foreground。

* Intra-queue Scheduling
* Inter-queue Scheduling
    
    - 固定優先權
    - Queue內部時間直接分配
    - [更多](https://www.facebook.com/OfficialBrayenLim/)

### Multilevel Feedback Queue

是進化版，除了原本的功能，還增加了『移動』功能。參數有這些：

* # of Queue
* 每個Queue的Algorithm
* 移動的策略
