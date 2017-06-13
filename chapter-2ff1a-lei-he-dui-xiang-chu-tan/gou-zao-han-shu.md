构造函数（contructor）

基本概念

* 定义：成员函数的一种，名字与类名相同，可以有参数，不能有返回值（void 也不行）
* **作用：对对象进行初始化，如给成员变量赋初值**
* 如果定义类时没有写构造函数，则编译器生成一个默认的无参数的构造函数
  * 默认构造函数无参数，不做任何操作
* 如果定义了构造函数，则编译器不会生成默认的无参数的构造函数。
* 对象生成时构造函数自动被调用。对象一旦生成，就再也不能在其上执行构造函数。
* 一个类可以有多个构造函数
* 为什么需要构造函数
  * 构造函数执行必要的初始化工作，有了构造函数，就不必在写初始化函数，也不用担心忘记调用初始化函数。
  * 有时候对象没有被初始化就使用，会导致程序出错。

eg1：调用默认的构造函数，定义对象时，不许给出构造函数的参数，采用系统随机生成的值

```
class Complex{
    private:
        double real,imag;
    public:
        void Set(double r,double i);
};    //编译器自动生成默认的无参的构造函数

Complex c1;    //默认的构造函数被调用
Complex * pc=new Complex;    //默认的构造函数被调用
```

eg2：调用自己编写的构造函数，定义对象时，需要给明构造函数的参数

```
class Complex{
    private:
        double real,imag;
    public:
        Complex(double r,double i=0);    //自己编写的构造函数，注意第二个参数有默认值，是可以缺省的
};
Complex::Complex(double r,double i){        //自己写了构造函数，用两个参数对实部和虚部进行初始化，编译器就不再生成了
    real=r;imag=i;
}
Complex c1;    //error,缺少构造函数的参数,而由于自己编写了构造函数，导致编译器不会自动生成默认参数的构造函数。
Complex * pc=new Complex;    //error，缺少构造函数的参数
Complex c1(2,1);     //OK
Complex c1(2,4),c2(3,5);    //OK
Complex * pc=new Complex(3,4);    //
```

可以有多个构造函数，参数个数或类型不同。多个构造函数分别在什么情况下起作用呢？就得看定义对象的时候给了什么样的参数。

```
class Complex{
    private:
        double real,imag;
    public:
        void Set(double r,double i);
        Complex(double r,double i);    //此处定义了3个参数不同的构造函数Complex()
        Complex(double r);
        Complex（Complex c1,Complex c2）;
}；
Complex::Complex(double r,double i)
{
    real=r;imag=i;
}
```



