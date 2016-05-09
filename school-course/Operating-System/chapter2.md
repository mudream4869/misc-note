# System Structures

目標：提供一個理解OS的方法，主要分三方向

* Services
* Interface
* System Components

## 系統提供的服務

* 執行程式：啟動、執行、終止...等
* I/O 操作
* 檔案系統 操作
* **溝通** ： Process內部或Process外部的交流
* 錯誤偵測：確保**正確**且Consistent的Computin
* 資源分配
* Accounting(這啥？)
* 安全和保護

## 介面

* Command Interpreter
* GUI

或者？兩個混合

# System Call

一個介於Process和OS的介面，像是Win32 API、POSIX API...，如此可以有些好處：

* Portability
* Ease of Use + Better Functionally

System 主要Handle: Process控制、檔案管理、裝置管理、Information Maintenance、溝通。

* Process 控制
    
    - 正常結束(end)、非正常結束(abort)
    - 讀取並執行
    - 增加或者結束Process => Multiprogramming?
    - 設定屬性
    - 等待(Signal)

* 檔案管理

    - 新增、移除
    - 打開、關閉
    - 讀寫
    - 設定屬性
    - 資料夾

* 裝置管理

    - Physical or virtual devices : File
    - Request or Release
    - 讀寫
    - 設定屬性
    - Logically 裝卸裝置

* Information Maintenance

    - 時間日期
    - Get or set system data(ex : amount of free memory)

* 溝通

# OS Structure 

Layer Approach: 模組化、除錯、驗證，但卻需要**好**的Layer定義，範例：

1. User Programe 
2. I/O Buffering 
3. Operator-console Device Driver
4. Memory management
5. CPU
6. Hardware

## Modules

可以不需reboot os就可以啟動的部分，像是：Solaris裡面的Sheduling Class, Loadable System Calls。

## Hybrid System

*定義：一些不同結構的組合*

EX: Mac OS X、iOS、Android

## Debugging

* Terminologies

    - Performance Tuning : seek to improve performance by removing bottlenecks
    - Core Dump : A Capture of the Memory of a Process or OS
    - Crash : A Kernel Fail

## VM

| Virtual User Mode    | Process | Process | Process |
|:--------------------:|:-------:|:-------:|:-------:|
| Virtual Monitor Mode | Kernel1 | Kernel2 | Kernel3 |
| monitor mode         |  VM     |  =      | =       |

優點：

* Complete Protection : Complete Isolation !
* OS Reasearch & Development

### VMware

### JVM
