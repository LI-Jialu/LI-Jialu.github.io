---
layout: post
title: Python魔法大战LeetCode数据结构和算法
date: 2023-09-01 20:08:02 +/-5000
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [jekyll]     # TAG names should always be lowercase
---

# Intro
为了用Python解决LeetCode问题努力！ 
以数据结构作为主线，每一章一个数据结构，章节内包括：基本概念，python实现，和对应的LC题。每章节内的内容从简单到困难，可以停在任何想停止的地方。 


# Stack 
## What is stack? 
LIFO: Last in, First out 

## 单调栈
单调：单调递增，或单调递减
比如，题目需要
Easy: Leetcode 496 
Hard: 

# Queue 

# Linked list 链表

# Hash Table 
## Why hash table? 
哈希表能用 **常量时间复杂度O(1)** 插入、查找和删除，非常适合存储大量数据并高效的检索。


## What is hash table? 
**Hash table: container of key-value pais.**


|  |  |
|--------|--------|
| key | - 任何可哈希（可散列）的数据类型，例如数字、字符串... <br> - Key should be UNIQUE 唯一的 |
| value | - any data, <br> - 可以是重复的 |

可哈希*： 

**哈希表由哈希桶构成**
* 每个哈希桶可以容纳一个或多个键值对
* 哈希桶的大小可变  => 合适的“负载因子” 

**哈希桶内会发生 哈希冲突** 

哈希冲突： 两个不同的键被映射到相同的哈希值



**避免发生哈希碰撞** 
- 好的哈希函数: 均匀分布,低碰撞

**发生哈希碰撞后的处理** 

根据哈希桶内的实际存储方法，对应处理哈希冲突和动态增减键值对。

| Data stucture   | Method   | Explanation   |
|-------|-------|-------|
| N.A.| 开放寻址法（Open Addressing）|直接把键值对存储在哈希桶中，不创建新的数据结构。当发生哈希冲突时，会根据一定规则（如线性探测、二次探测等）尝试找到下一个可用的位置来存储键值对。|
| 链表 | 链式哈希法（Chaining） |在哈希桶内部创建一个链表或链表的数组，每个节点存储一个键值对。如果多个键映射到同一个哈希桶，它们将被按顺序存储在链表中。| 
| 二叉树或红黑树 | 二叉查找树（Binary Search Tree） |当哈希桶中的键值对数量较多时，可以使用来存储键值对，树的每个节点都存储一个键值对，并根据键的大小进行排序。| 




## How O(1)? 
TBC

## How to implement hash table in Python? 
* Dictionary 
  
  **创建**，创建的dictionary 自带哈希函数。
  ```python
  dict_a = {'test_key':'test_value'}
  ```
  |    |    | 
  |-------|-------|
  |key| `test_key`
  |value |`test_value`
  |hash value|  `test_key` ---hash func--> hash value (一个整数)
    

  **增**，如果用相同的key插入多个值，会覆盖。 
  ```python
  my_dict = {'key': 'value1'}
  my_dict['key'] = 'value2'
  print(my_dict['key'])  # 输出: 'value2'
  ```
    * 具体的哈希桶大小、内存分配策略等是由Python解释器进行管理的

Python中的字典是动态的、无序的、可变的。 

* Dictionary in queue 

  当你在运行Python脚本时，操作系统会在计算机的内存中为该脚本创建一个进程，并为该进程分配一段内存空间来执行代码和存储数据。堆是一种用于动态分配内存的数据结构，用于存储不定大小的数据，包括刚才提到的dictionary。以及Python的垃圾回收机制会自动检测不再被使用的对象，并释放其占用的堆内存。

  - 分配内存： 首先在堆内存中分配一块足够大的内存空间，用于存储字典对象及其键值对。后续会动态扩展。
  - 哈希表初始化： 字典内部使用一个哈希表来存储键值对。哈希表是一个数组，每个元素都是一个哈希桶，每个哈希桶可以存储多个键值对。初始时，哈希表中的哈希桶都是空的。
  - 添加键值对： 当你添加一个键值对时，Python会使用哈希函数计算键的哈希值。这个哈希值会被映射到哈希表中的一个哈希桶。在哈希桶中，会存储该键值对的键、值以及哈希值（用于处理哈希冲突）等信息。
  - 处理哈希冲突： 如果发生哈希冲突（多个键映射到同一个哈希桶），Python会使用特定的方法来解决。通常，这包括使用链式哈希法，在同一个哈希桶中创建一个链表或红黑树来存储多个键值对。
  - 动态内存管理： 如果字典的键值对数量增加，Python可能会动态地扩展哈希表的大小，重新分配更大的内存空间，并重新哈希现有的键值对，以确保哈希表的负载因子保持在合适的范围内。


## Drawbacks of hash table? 

哈希冲突


# Trere 

# Graph 
