* Batch systems : User並沒有直接和System互動，而是準備好jobs清單給系統處理。相似的job會被綁在一起(?)。
* Spooling : Simultaneous Peripheral Operation On-Line，在高速的輸入及輸出裝置上的一個暫存區，讓眾多的工作存入該暫存區，在該暫存區內，眾多工作將會依序的加以完成。
* Multiprogramming : OS在memory裡同時保持多個job。Multiprogramming藉由組織jobs，讓CPU一直會有jobs要做，來增加CPU利用率。
* Timesharing : 一個Multiprogramming的logical extension.因為太快切換，以至於user可同時和每個program互動。
* Real-time systems : 很重視Deadline的OS，時間內對external stimuli是很重要的。
* Bootstrap program : 初始化OS所有方面。像是：CPU register, device controller, memory, etc.
* Microkernel : 
* Async I/O : 不等I/O處理完，先Return回user
* Program I/O : CPU 使用 polling 去看 device，constantly looping去看裝置有沒有準備好。
* Virtual Machine : VM 提供一個和 underlying bare hardware一樣的介面。
* Socket : 一個由(IP, port)所構成的溝通終點
* Cluster System : Cluster computers share sotorage and closeli linked via LAN networking.
* Cooperating Process : 有和其他Process Share Memory的Process。
* Primary Storage : Main memory(vloatile storage)
* Privilege Escalating : 取得額外的權限
* System Generation(SYSGEN) : A process that configure or generate the os for a specific computer.
* Booting : loading kernel來開始一個computer
* Sheduler Activation : A scheme for communication between the user-thread library and the kernel.
* Memory Stall : 需要等一段時間，該memory才會available
* Para-Virtualization : 
* Push Migration in Load Balancing : 
