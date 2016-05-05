# Process Concept

* Variety on Platforms

## Process 

EX:

* PID 0 : Swapper : Kernel process
* PID 1 : *init* => `/etc/rc*` or `/sbin/rc*`
* PID 2 : paging

````
new --> ready <==> running --> terminated
          ^        /
          ^       /
        waiting </
```

* 用 `PCB` 紀錄：Process State, Program Counter, CPU Register, 
Memory Management Information, Accounting Information, I/O Status Information

## Process Scheduling

### Schedulers

目標是為了有個好的I/O和CPU使用效率mix，牽涉到幾項

* Multiprogramming
* 可以花更多時間在選擇process，因為會也更長的空隙
* 可能不牽涉Physically

### Contex Switches

**LWP**

## Operations on Processes

## Interprocess Communication

### Shared Memory

*Example* : 環狀

**Producer**:

```c
for(;;){
    while(((in+1)%BUFFER_SIZE) == out);
    buffer[in]= nextp;
    in = (in + 1)%BUFFER_SIZE;
}
```

**Consumer**:

```c
for(;;){
    while(in == out);
    nextc = buffer[out];
    out = (out+1)%BUFFER_SIZE;
}
```

### Message Passing

邏輯上的定義：

* Msg size : Fixed/Var
* Communication : Sym/Asym, Direct/Indirect
* Buffering : Auto/Explicit ...
