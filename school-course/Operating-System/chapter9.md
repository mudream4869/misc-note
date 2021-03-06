# Virtual Memory

一個讓Process不需完全進駐記憶體的方法

好處：

1. program大小可以更大
2. level of multiprogramming更大
3. user program 可能可以跑更快

實作：

需要 *paging*, *segmentation*

## Handle Page Fault

* Pure Demand Page
* Pre-Paging

### Crucial Issue

* Restart an inst

## Performance of Demand Paging

Effect Access Time = (page fault probility)*(page fault time) + (page hit probility)*(memory access time for paging)

## Copy-on-Write

`fork()` and `execve()`

## Page Replacement

* Algorithms

### FIFO

*Belady's anomaly* : 對於某些page-replacement algorithm，`page fault rate` 可能會隨著 `# of allocated frame` 上升

### OPT(Optimal Algorithm)

* 有最低page fault rate
* 把最久不使用的page換掉：需要prediction

### LRU(Least Recent Algorithm)

"frame #, v/i, time tag"

* LRU Approx(因為硬體難實作，所以用逼近法):

1. Additional-Ref-Bit Algorithm
2. Second-Chance Algorithm
3. Enhanced Second Chance Algorithm
4. Counting Based Page Replacement

### Additional-Ref-Bit Algorithm

把Ref bit的歷史保留下來

| xx | xx | history |
|:--:|:--:|:-------:|
|  1 | -> | 0001010 |
|  0 | -> | 1000001 |
| .. | .. | ..      |
|  1 | -> | 1110000 |

* LRU : get history smallest value

### Second-Chance Algorithm

* When a page is selected : take it as victim if ref-bit = `0`，otherwise use next.

* Enhanced Second-Chance Algorithm : 考慮swapping out的花費

    - `(0, 0)` : 非最近使用，且不髒
    - `(0, 1)` : 非最近使用，髒
    - `(1, 0)` : 最近使用，不髒
    - `(1, 1)` : 最近使用，髒

### Counting-Base

* 數ref的次數
* Least Freq Used
* Expansive

## Page Buffering

## Frame Allocation

### Single User(Process)

### Multiple Processes

* m frames , n processes
    * Equal Allocation
    * Proportional Allocation





