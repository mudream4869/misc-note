* Batch systems : User並沒有直接和System互動，而是準備好jobs清單給系統處理。相似的job會被綁在一起(?)。
* Spooling : Simultaneous Peripheral Operation On-Line，在高速的輸入及輸出裝置上的一個暫存區，讓眾多的工作存入該暫存區，在該暫存區內，眾多工作將會依序的加以完成。
* Multiprogramming : OS在memory裡同時保持多個job。Multiprogramming藉由組織jobs，讓CPU一直會有jobs要做，來增加CPU利用率。
* Real-time systems : 很重視Deadline的OS
* Bootstrap program : 初始化OS所有方面。像是：CPU register, device controller, memory, etc.
* Microkernel : 
