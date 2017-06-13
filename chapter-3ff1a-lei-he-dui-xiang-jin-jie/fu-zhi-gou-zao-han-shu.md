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



