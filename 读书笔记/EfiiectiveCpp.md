# 0.CPP 是一个语言联邦
    C 
    object-oriented C++ classes 封装 继承 多态 virtual函数等等
    Template C++ 泛型编程，模板化编程
    STL template程序库 容器 迭代器 算法 函
# 1.prefer enum const inline to define
    ：：在类的外部 引用、定义 类的成员函数
```x
const double PI = 3.1415926;
const char NAME[] = "jade";
inline min(a,b) { if (a < b) return a; else return b; }
```
# 2.Use const whenever possible
    int const *p=greeting    #const value
    const int *p=greeting    #const value
    int * const p=greeting    #const pointer
# 3.Make sure the object are initialized before they're used