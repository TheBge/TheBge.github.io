title: 侯捷C++ 面向对象 总结
author: Bing
tags: []
categories: []
date: 2020-12-25 16:25:00
---
//complex class  
1.带指针的class/不带指针的class  
2.初始化列表/不使用初始化列表赋值 （头文件与类的声明   
构造函数）   
3.constructor放在private里（参数传递与返回值）  
singleton  
4.考虑return by value与return by reference  

//string class  
**只要你的类里面带指针，必须有拷贝构造/拷贝赋值。**  
1.调试模式和release模式   

//Object Oriented Programming, Object Oriented Design (OOP, OOD)  
Inheritance 继承  
Composition 复合  
Delegation 委托
1.Composition（组合与继承）  
Adapter  
2.pimpl   
pointer to implementation  
3.Inheritance with virtual  
template method  
4.Delegation + Inheritance   
Observer  
Composite
5.Prototype