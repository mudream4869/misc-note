# Introduction

什麼是OS: 一個介於人和硬體的中間物

主要有兩個重點：**方便性**和**效率**，不過這兩個是衝突的！

* 對使用著的方便性
* 計算機的效率

## UNIX Architecture

|  user, user ...           |
|:-------------------------:|
| Shells, app, etc.         |
| CPU scheduling, paging... |
| physical memory...        |

## Booting

Bootstrap program : 初始化所有東西、開始跑OS

## Interrupt

分兩種：

* Hardware, ex : I/O request
* Software, ex : signal

```
proc exec
========\            /==========>
interrupt\          /  return
          \========/
            handle
```

### Interrupt Handling Procedure

* 把interrupted instruction的位置存起來

```
proc exec
========\   stack    /==========>
interrupt\          /  return
          \        /
           \======/
            handle
```

* 系統由**中斷向量**(Interrupt Vector)可知道中斷服務程式的入口

## Memory

* Process可以直接接觸
* Memory-Mapped I/O
* Polling

### Magnetic Disks

### DMA

**直接記憶體存取 Direct Memory Access**，可獨立讀寫記憶體。

為了避免讓CPU處理太多data interrupt

## Hardware Protection

避免錯誤和誤操作！像是寫到不屬於該Process的地方

* Dual-Mode Operation : 分mode
    
    - User-mode : 除去使用interrupt, trap
    - Monitor-mode : (System mode, privileged mode, supervisor mode)
    : 可能炸掉的操作

* Memory Protection : 作法：把跟Memory有關的操作設定為Privieged
* CPU Protection : 作法：Time sharing, context switch

## System Components

* Process Management

* Memory Management

    - OS必須keep好數個programs

* System Management

    A uniform logical view of information

* File-System

```
  ---------    ---------
  |process|    |process|
  ---------    ---------
      ||           ||
---------------------------
        File System
---------------------------
      Storage System
---------------------------
  Physical Devices(Disks)
```

* Storage Management
* Tertiary Storage Devices
* I/O System Management

## Caching

* Management
    
    * Cache Size
    * Replacement Policy(algorithm)

* Coherence and Consistence

    ```
    |------|      |-----|      |=====|
    |Client| <==> |Cache| <==> |  M  |
    |------|      |-----|      |  E  |
        conherence--^          |  M  |
                    v          |  O  |
    |------|      |-----|      |  R  |
    |Client| <==> |Cache| <==> |  Y  |
    |------|      |-----|      |=====|
    
    ```

    * Cache consistency requires that all write operations to the same memory location are performed in some sequential order.(wiki)

## Protection & Securty

*定義*：

* Protection ==> 控制存取的一些機制
* Security ==>  在來自外部或內部的攻擊下的保護
