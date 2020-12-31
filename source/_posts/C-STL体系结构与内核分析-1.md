title: C++ STL体系结构与内核分析
author: Bing
tags:
  - C++
  - 数据结构
categories:
  - C++
date: 2020-12-30 20:07:00
---
###### STL 六大部件
容器（Containiers）  
分配器（Allocators）  
算法（Alogrithms）  
迭代器（Iterators）  
适配器（Adapters）  
仿函数（Functors）  
![upload successful](\\images\pasted-8.png\)  

###### 容器  
Sequance Containers：  
Array  
Vector  
Deque  
List  
Forward List  

Associative Containers：  
Set/MultiSet   
Map/Multimap    
![upload successful](\\images\pasted-9.png\)  

Unordered Containers：  
Unordered Set/MultiSet  
Unordered Map/Multimap  
用hash table实现的
![upload successful](\\images\pasted-10.png\)  

###### 分配器  
example：  
```c++  
template<typename T, typename _Alloc = std::allocator<T>>
class vector:protected _Vector_base<T, _Alloc>
```  

##### OOP(object-oriented programming) vs GP(Generic Programing)  
OOP将datas与methods关联在一起  
GP将datas与methods分开  
使用**GP**：  
1 Containers/Algorithms团队各司其职，以Iterator沟通  
2 Algorithms通过Iterators确定操作范围，通过Iterators取用Containers元素  
![upload successful](\\images\pasted-11.png\)

##### 阅读C++标准库，基础  
1 Operator Overloading 操作符重载  
2 Templates 模板  
类模板/函数模板/成员模板  
模板特化/偏特化