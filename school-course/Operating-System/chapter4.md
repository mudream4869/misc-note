# Multithreaded Programming

* 一種 Lightweight process(LWP)

## User-level Threads

* 用Thread library實作而成
* EX : POSIX Thread
* 優點：他們之間的Context switch很快
* 缺點：假如把其中一個Thread block住（像是IO），那整個process都會被Block住

## Kernel-level Thread

* 用syscall實作而成
* EX : Win XP
* 優點：不會被Block住
* 缺點：Context switch花費很多

## Models

|Type|Explain|好處|壞處|例子|
|----|-------|----|----|----|
|Many-to-One |*Many* User-thread to *one* Kernel thread |迅捷|block one, block all| |
|One-to-One  |*One* User-thread to *one* Kernel thread  |one block one|過度使用kernel thread| Win NT, 2000, XP |
|Many-to-Many|*Many* User-thread to *many* Kernel thread|混合！| | Tru UNIX |

## Library

### Pthread

* User-Level Thread (??)

```c
#include <pthread.h>
int main(int argc, char** argv){
    ...
    pthread_attr_init(&attr);
    pthread_create(&tid, &attr, runner, argv[1]);
    pthread_join(tid, NULL);
}
void* runner(void* par){
   ...
}
```

### Windows Thread

* Kernel-Level Thread

### Java Thread

[Stackoverflow](http://stackoverflow.com/questions/2653458/understanding-javas-native-threads-and-the-jvm)

* n:m Model

## Implicit Thread

目標：把管理Thread的義務轉移到Compiler上

* EX: OpenMP, Grand Central Dispatch

## Thread Issues

* Fork : 複製所有Thread或者純粹複製一條Thread?
* Exec : 取代所有Thread
* Fork then exec : 效能考慮
* Signal Handling:

    - masking
    - User-defined signal

* Thread Cancelling

    - 兩種取消方法
        - 非同步取消 (asynchronous cancellation) : 立即結束執行緒
        - 延遲取消 (deferred cancellation) : 執行緒週期性的檢查是否取消
    - 假如在Thread在更新資料時候被Cancel?
    
