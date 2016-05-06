# Synchronization

* 為了能讓多方接觸的資料完整
* 主要是用各種方法保證執行順序

Example:

```c
for(;;){
    while(counter == BUFFER_SIZE);
    produce an item in nextp;
    buffer[in] = nextp;
    in = (in+1)%BUFFER_SIZE;
    counter++;
}
```

```c
for(;;){
    while(counter == 0);
    nextc = buffer[out];
    out = (out+1)%BUFFER_SIZE;
    counter--;
    consume an item in nextc;
}
```

問題：`counter++`, `counter--` Race Condition!

## Critical-Section Problem

* 只能有一個Process進入

```c
do{
    //entry section;
    //...critical section;
    // exit section;
    //...
}while(1);
```

### Peterson's Solution

#### Algo1

```c
do{
    while(turn != i);
    // critical section
    turn = j;
    //...
}while(1);
```

* 問題：假如其中一個壞掉，這個東西就會被卡住

#### Algo2

想法：保持住每個Proc的狀態

```c
do{
    flag[i] = true;
    while(flag[j]);
    // Critical
    flag[i] = false;
    // ...
}while(1);
```

* 問題：`flag[i] = flag[j] = true` 導致可能兩邊都卡住

#### Algo3

* 結合前兩個想法

```c
do{
    flag[i] = true;
    turn = j;
    while(flag[j] && turn == j);
    // Critical
    flag[i] = false;
    //...
}while(1);
```

#### Multiple-Process Solution

```c
do{
    choosing[i] = true;
    number[i] = max(number) + 1;
    choosing[i] = false;
    for(j = 0; j < n;j++){
        while(choosing[j]);
        while(number[j] != 0 && (number[j], j) < (number[i], i));
    }
    // Critical Section
    number[i] = 0;
    // ...
}while(1);
```

### Hardware Solution

#### TestandSet & Swap

`TestandSet` 和 `Swap` 要設成 atomic

```c
bool TestAndSet(bool &tar){
   bool rv = tar;
   tar = true;
   return rv;
}
```

```c
do{
    while(TestAndSet(&lock));
    // Critical
    lock = false;
    //...
}while(1);
```

```c
void Swap(bool* a, bool* b){
    bool temp = *a;
    *a = *b;
    *b = temp;
    return;
}
```

```c
do{
    key = true;
    while(key) Swap(&lock, &key);
    // Critical
    lock = false;
    // ..
}while(1);
```

