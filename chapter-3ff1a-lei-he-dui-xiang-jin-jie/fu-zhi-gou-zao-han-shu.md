复制构造函数（copy constructor）

* 只有一个参数，即对同类对象的引用
* 形如 X::X\( X& \) 或 X::X\( const X &\)，二者选一，后者能以常量对象作为参数
* 如果没有定义复制构造函数，那么编译器生成默认复制构造函数。默认的复制构造函数完成复制功能。

eg1：调用默认的复制构造函数

```
class Complex{
    private:
        double real,imag'
};
Complex c1;        //调用缺省无参构造函数
Complex c2(c1);    //调用缺省的复制构造函数，将c2初始化成和c1一样
```

* 如果定义了自己的复制构造函数，则默认的复制构造函数不存在。

```
class Complex{
    public:
        double real,imag;
    Complex(){}
    Complex(const Complex & c){    //定义复制构造函数
        real=c.real;
        imag=c.imag;
        cout<<"Copy Constructor called";    //复制构造函数也可以做其他工作
    }
};
Complex c1;
Complex c2(c1);    //调用自己定义的复制构造函数，使得c2的实部和虚部与c1一样，同时输出语句 Copy Constructor called
```

* 复制构造函数的参数必须是本类的**引用**，而不能是本类的对象
  * 即不允许有形如 X::X\(X\) 的构造函数

```
class CSample{
    CSample(CSample c){
    }        //错，不允许有这样的构造函数，参数不是类的引用
};
```

* 复制构造函数起作用的三种情况

  1. 当用一个对象去初始化同类的另一个对象时

     ```
     Complex c2(c1);
     Complex c2=c1;    //同上一条语句等价，初始化语句，非赋值语句。c2由复制构造函数初始化，初始化参数为c1
     ```

  2. 如果某函数有一个参数是类A的对象，那么该函数被调用时，类A的复制构造函数将被调用，进而初始化函数的形参

     ```
     class A
     {
         public:
         A(){};
         A(A & a){
             cout<<"Copy constructor called"<<endl;    //自己编写的复制构造函数
         }
     };
     ---
     void Func(A a1){ }    //函数的形参a1是类A的对象，a1默认由上面自定义的复制构造函数初始化
     int main(){
         A a2;
         Func(a2);    //函数被调用，以a2为参数（实参）。而函数的形参a1是由复制构造函数初始化的。
         return 0;
     }
     ---
     输出
     Copy constructor called
     ```

  3. 如果构造函数的返回值是类A的对象时，则函数返回时，A的复制构造函数被调用，用于初始化作为返回值存在的类A的对象。

     ```
     class A
     {
         public:
         int v;
         A(int n){ v=n; };
         A(const A & a){
             v=a.v;
             cout<<"Copy constructor called"<<endl;    //自己编写的复制构造函数
         }
     };
     ---
     A Func(){
         A b(4);        //定义了一个局部对象b
         return b;
     }
     int main(){
         cout<<Func().v<<endl;    //调用函数Func(),它的返回值是一个对象，接下来取该对象的v成员变量
         return 0;                //在对象被生成的时候，就会调用构造函数，按照规则3，就会用复制构造函数初始化，即输出Copy constructor called
     }                            //调用的复制构造函数的参数是b，因此返回值就是b，所以v就是b.v,即4，输出4
     ---
     输出
     Copy constructor called
     4
     ```

\*为什么要自己写复制构造函数？

后面我们会讲到，有的时候你是必须要写自己的复制构造函数，否则你的程序就会出错。那这个就下回分解。

---

课程视频：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/f0484398342241b7be57dfa9f31a2e65/188ff44d5a1e4114946741803abaf969/?activate\_block\_id=block-v1%3APekingX%2B04831750.1x%2B2015T1%2Btype%40sequential%2Bblock%40188ff44d5a1e4114946741803abaf969](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/f0484398342241b7be57dfa9f31a2e65/188ff44d5a1e4114946741803abaf969/?activate_block_id=block-v1%3APekingX%2B04831750.1x%2B2015T1%2Btype%40sequential%2Bblock%40188ff44d5a1e4114946741803abaf969)

2017.06.13



  




