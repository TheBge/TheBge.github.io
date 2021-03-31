title: C++
author: Bing
tags:
  - C++
categories: []
date: 2021-01-21 15:47:00
---
**记录下琐碎的知识点**

**类与类的关系**  
1、类的组合  
类A具有类B的属性
```c++  
class Person
{
  public:
	  Person(int _age, string _name) :age(_age), name(_name) {}
	  ~Person() {};
	void print() 
	{
		cout << name<<"	" << age  << endl;
	}
	private:
		int age;
	   string name;
};
class Teacher
{
public:
	Teacher(Person* _person) :person(_person) {}
	~Teacher() {};
	void print()
	{
		this->person->print();
	}
	private:
		Person* person;
		
};
int main()
{
	Person p(40, "lisan");
	Teacher teacher(&p);
	teacher.print();
	system("pause");
	return 0;
}
```
**函数的返回值和临时对象**  
传引用和返回引用，将参数声明为引用是为了提高效率，返回值如果是临时对象则不能返回引用。不要返回指向局部变量或者临时对象的引用。  

**关于const**  
```c++  
  int   b   =   500;   
  const   int*   a   =   &b; 
  int   const   *a   =   &b;              
  int*   const   a   =   &b;           
  const   int*   const   a   =   &b;   
```
const位于* 的左侧，则const用来修饰指针所指向的变量，即指针指向常量。  
const位于* 的右侧，则const修饰指针本身，即指针本事是常量。 
const可以修饰函数的返回值、某个参数、或者函数本身。  
注意：  
	const变量赋值   
	在参数中使用const应该使用引用或指针，而不是一般的对象实例，原因同上；   
	const在成员函数中的三种用法要很好的使用；   
	不要轻易的将函数的返回值类型定为const;   
	除了重载操作符外一般不要将返回值类型定为对某个对象的const引用;  
    
**this**  
this指针是空的相当于成员函数的第一个参数是NULL，那么只要成员函数没有使用到成员变量，也是可以正常调用成员函数。  
静态成员函数不能使用 this 指针，因为静态成员函数相当于是共享的变量，不属于某个对象的变量。  

**class与struct**  
1.使用 class 时，类中的成员默认都是 private 属性的；而使用 struct 时，结构体中的成员默认都是 public 属性的。  
2.class 继承默认是 private 继承，而 struct 继承默认是 public 继承。  
3.class 可以使用模板，而 struct 不能。  
