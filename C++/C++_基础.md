# 1. C++_基础
## 1.1. Day1 
### 1.1.1. 一、面向对象的概念
    类：同一类对象的共同属性和行为，形成类
    封装：
        隐蔽对象内部细节
        对外形成一个接口，安全
    继承：
        改造、扩展成新的类
    多态:
        同样的消息引起不同对象的不同行为
        
### 1.1.2. 二、程序开发过程
    汇编：汇编语言->目标程序
    编译：高级语言->目标程序
    解释：高级语言->机器指令（半编译，半解释）
    算法设计-》源程序编辑-》编译-》连接-》测试

### 1.1.3. 三、计算机数据表示
    源码
    反码
    补码

### 1.1.4. 四、基本语法
    1.运算符*
        cin>>a;
        cout<<"hello world"<< a;
        +-*/ % ++ --  =
        += -= *= /=
        x=a>0?1:2;
        sizeof()
        3&5 按位与操作 11&101
        3|5   按位或操作 11|101
        ~3    按位取反
        <<左移运算  ；>>右移运算
        运算符优先级
    2.注释
        // 一行*
        /* ...........*/一段*
    3.I/O流*
    4.IF语句
        if(x>y) cout<<x
        if
            else
                {
                    if
                    else
                }
        5.switch*
            switch(day){
                case 0:xxx;
                case 1:xxx; break;
                ....
                default
        6.while
            {
                xxxxx
            }
            do
            {
                xxxx
            }while();
        7.for(表达式1:判断条件:表达式2)
        {
            xxx
           }*
           break:跳出该内层循环
           continue：结束本次循环，开始下次循环
           goto：跳转到指定语句
       8.typedef自定义类型
           enum 每局类型名{
           monday tuesday ....}
           (不能赋*值，默认有值)
        *9.函数
            函数类型 函数名 （形参1，形参2...）
        10.函数嵌套、递归调用
            int fun1()
            return fun1*fun2*
        12.参数传递
            引用类型
            int &r=i; 类似别名，并初始化为变量i的引用，该引用不能指向别的变量
            引用可以作为形参
        13.可变参数函数
        14.内联函数
            inline函数：
        15.constexpr函数
            constexpr int get_size(){return 20;}
        16.函数重载
           C++允许功能相近的函数在同一个作用域以相同函数名声明，从而形成重载
            编译器识别 形参的个数，类型
            eg 比较数的大小
                        `#include<iostream>
                        using namespace std;
                        int max1(int x,int y){
                            if(x==y)return x;
                            else if(x>=y)
                                return x;
                                else
                                {
                                    return y;
                                }       
                        }
                        int max1(int x,int y,int z)
                        {
                            return max1(max1(x,y),z);
                        }
                        double max1(double x,double y)
                        {
                            if(abs(x-y)<1e-10)return x;
                            else if(x>=y)
                                return x;
                                else
                                {
                                    return y;
                                }
                                
                        }
                        double max1(double x,double y,double z)
                        {
                            return max1(max1(x,y),z);
                        }

                        int main()
                        {
                            int a,b,c;
                            double j,k,l;
                            cout<<"a b c"<<endl;
                            cin>>a>>b>>c;
                            cout<<max1(a,b,c)<<endl;
                            cin>>j>>k>>l;
                            cout<<max1(j,k,l)<<endl;
                            system("pause");
                            return 0;

                        }`
## 1.2. 类与对象
抽象
继承
多态：同一名称，不同功能
封装

### 抽象
`class clock{
    public:
    void settime(int newH,int newM,int newS);
    void showtime()
    private:
    int hour,minute,second;
    };`
### 封装：外部接口+访问权限=访问类成员
### 继承
### 多态：同一个名称，不同的功能
### 类：
    class 名称{
    public:
    private:
    protected:
    };
``class clock{
    public:
    void setTime(int newH=0,int newM=0,int newS=0);
    void showTime();
    private:
    int hour,minute,second;
`};
//成员函数
void clock::setTime(int newH=0,int newM=0,int newS=0){
    hour=newH;
    minute=newM;
    second=newS;
}
void clock::showTime(){
    cout<<hour<<":"<<minute<<":"<<second;
}
//主函数
int main(){
    clock myclock;
    myclock.setTime(8,10,10);
    myclock.showTime;
    return 0;
}``
### 构造函数：
    构造函数
    复制构造函数
    委托构造函数
    无return语句，无返回值类型
`class clock{
    public:
    clock(int newH,int newM, int newS);//构造函数
    clock();//默认构造函数
    void setTime(int newH=0,int newM=0,int newS=0);
    void showTime();
    private:
    int hour,minute,second;
};
//构造函数实现：
clock::clock(int newH,int newM,int newS):
hour(),minute(),second()
//调用
int main(){
clock c1(8,10,0)//调用有参数的构造函数
clock c2;//调用无参数的构造函数}`
#### 委托构造函数：
```clock(int newH,int newM,int newS):
    hour(newH),minute(newM),second(newS){}
    clock():clock(0,0,0){}
```
    复制构造函数
    用一个存在的对象去初始化同类型对象
```class xx{
    public:
    xx(形参);//构造函数
    xx(const 类名 &对象名);//复制构造函数
    };
    类名::类(const 类名 &对象名)//复制构造函数实现
    {。。。}
```
### 析构函数
    释放资源 ~类名();
### 类的组合
    用其他类的对象组合成新的类
## 1.3UML语言
    事物
    关系
    图
## 1.4结构体
### 1.特殊的类--结构体
    类缺省访问权限是private
    结构体缺省访问权限是public
``` 
    struct 名称{
    公用成员
    procted:
    private:
    }
    名称.成员//访问
```
## 1.5联合体
```x
    union 名称{
    public:
    procted:
    private:
    }
```
    有且只有一个有效
## 1.6枚举类
    enum class 名称:底层类型{枚举值列表};
```x
    enum class type{G,L,M,H};
    enum class type:char{G,L,M,H};
    enum class type:double{G,L,M,H};
```
    强作用域
    指定底层类型
    转换限制
## 1.2小结
    对象
    类
    构造函数
    析构函数
    内联成员
    类组合
    结构体
    联合体
    枚举类
    UML
# 实验四
eg1 声明一个CPU类，包含 rank frequency voltage
有两个公用成员函数run,stop
```x
#include<iostream>
#include<stdio.h>
using namespace std;
enum CPU_Rank{P1=1,P2,P3,P4,P5,P6,P7};
class CPU{
    private:
        CPU_Rank rank;
        int fre;
        float voltage;
    public:
        CPU(CPU_Rank r,int f,float v)
        {
            rank=r;
            fre=f;
            voltage=v;
            cout<<"构造了一个CPU"<<endl;
            }
        ~CPU(){cout<<"析构了一个CPU"<<endl;}
        //外部接口
        CPU_Rank GetRank() const{return rank;}
        int GetFre() const{return fre;}
        float GetVoltage() const{return voltage;}
        
        void SetRank(CPU_Rank r){rank=r;}
        void SetFre(int f){fre=f;}
        void SetVoltage(float v){voltage=v;}
        void Run(){cout<<"CPU开始运行"<<endl;}
        void Stop(){cout<<"CPU停止运行"<<endl;}
        };
    int main()
    {
        CPU a(P6,300,2.8);
        a.Run();
        a.Stop();
        system("pause");
        return 0;
        }
```

## 1.7 数据的保护与共享
    友元：可访问私有类 friend float dist(xx &a)
    const:保护数据
    static:静态生存区
    动态生存区
    .h文件：类声明
    .cpp文件：类实现
        xxx.h iostream .cpp  -->obj--->.exe
    #define #undef
    
## 1.8 数组&&指针
    int a[10]
    static int i;
## 1.9 继承&&派生
## 2.0 运算符重载
## 2.1虚函数
## 2.2 OVERRIDE FINAL
## 2.3 模板 链表 栈
## 2.4 智能指针
## 2.5 输入、输出流

# 2.常见问题
2020年
## 8/1
    1.作用域::
    A::B A是B的作用域
    














