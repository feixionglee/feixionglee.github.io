---
layout: post
title:  Stack, Heap, and Pointer
date:   2019-09-20 16:48:23 +0800
categories: rust
---
栈内存、堆内存和指针

当给一个函数A分配一段栈内存，是这个区域在栈内存区域的最顶端，如果此时又有一个新的函数B调用，给B分配的内存区域将A的上方，这个就是栈区域的含义（后入先出）。分配给A和B的内存是自由使用的一段内存（可能连续或不连续），这段内存不是栈（数据结构）。

变量本身存在栈区域，如果是整型变量, e.g.
| name | value |
|---|:---:|
|type  | int |
|value | 10  |

如果是string, e.g. (from rust book chapter 4th)
| name | value |
|---|:---:|
| ptr | xxxxxx |
| len | 5 |
| capacity | 5  |

ptr是一个指针，指向堆内存中的一个地址

---
References:
[c - memory allocation in Stack and Heap - Stack Overflow](https://stackoverflow.com/a/6770626/163977)

When I allocate something dynamically using malloc, there are actually TWO pieces of data being stored. The dynamic memory is allocated on the heap, and the pointer itself is allocated on the stack. So in this code:
```c
int* j = malloc(sizeof(int));
```
This is allocating space on the heap for an integer. It's also allocating space on the stack for a pointer (j). The variable j's value is set to the address returned by malloc.

---
堆内存的访问性能远不如栈内存。存放在堆上的数据要通过其存放于栈上的指针进行访问，这就至少多了一层内存中的跳转。--- Rust编程之道4.1.2