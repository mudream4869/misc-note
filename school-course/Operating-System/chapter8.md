# Memory-Management Strategies

動機：把複數個Process放在記憶體已增加system performance

## Dynamic Loading 

A routine will not be loaded until it os called，好處：

1. 記憶體使用效率up
2. 分享Library

## Overlays

## Swapping

* Only swap in must used.
* Mobile systems 不支援 Swapping，但是會有 Paging
* What should swap out?
    * Lower Prioirty ?

## Contiguous Allocation

Contiguous memory allocation is a classical memory allocation model that assigns a process consecutive memory blocks

### Single User

### Multiple Users

* First Fit : Find first hole big enough
* Best Fit : Find smallest hole big enough

*Dynamic Partitions*

好處：higher degree of multiprogramming
壞處：relocation需要時間

*Solution* : Paged Memory

## Paging

Basic Method:

* logical address space : 2^m
* max number of pages : 2^(m-n)

### Hardware Support

Translation Look-aside Buffer

| page # | page offset |
|--------|-------------|
| m-n    | n           |

## Multilevel Paging

多數 Logical address space 也很大 2^32 ~ 2^64

## Inverted Page Table

"Pid, Page number, offset"

## Segmenatation

使用者對於記憶體的概念

"seg name, offset" => "seg number, offset"

## IA-32

### Segmentation

### Paging


