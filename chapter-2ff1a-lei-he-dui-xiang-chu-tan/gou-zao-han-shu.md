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

* 一个类可以有多个构造函数，只要多个构造函数的参数个数或类型不同，这多个构造函数就构成了重载的关系。多个构造函数分别在什么情况下起作用？就得看定义对象的时候给了什么样的参数。

eg：多个构造函数的调用

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
Complex::Complex(double r)
{
    real=r;imag=0;
}
Complex::Complex(Complex c1,Complex c2)
{
    real=c1.real+c2.real;imag=c1.imag+c2.imag;
}

Complex c1(3),c2(1,0),c3(c1,c2);    //由于整型参数可以被自动转化成double类型的，所以c1={3,0},c2={1,0},c3={4,0};
```

构造函数在数组中的使用（注意：类的对象为数组，指的是数组里的每个元素都是类的对象）

eg1：

```
class CSample{
        int x;
    public:
            CSample(){
                    cout<<"Constructor 1 Called"<<endl;        
            }
            CSample(int n){
                    x=n;
                    cout<<"Constructor 2 Called"<<endl;
            }
};
int main(){
    CSample array1[2];        //编译器使用无参的构造函数初始化
    cout<<"step1"<<endl;        
    CSample array2[2]={4,5};  //编译器使用无参的构造函数初始化
    cout<<"step2"<<endl;
    CSample array3[2]={3};
    cout<<"step3"<<endl;
    CSample * array4=new CSample[2];
    delete []array4;        //new出来的东西，在结束的时候要用delete把空间收回
    return 0;
}

输出：
Constructor 1 Called
Constructor 1 Called
step1
Constructor 2 Called
Constructor 2 Called
step2
Constructor 1 Called
Constructor 2 Called
step3
Constructor 1 Called
Constructor 1 Called
```

eg2：

```
class Test{
    public:
        Test(int n){}            //(1)
        Test(int n,int m){}      //(2)
        Test(){}                 //(3)
};
Test array1[3]={1,Test(1,2)};    //3个元素分别用(1),(2),(3)初始化
Test array2[3]={Test(2,3),Test(1,2),1};    //3个元素分别用(2),(2),(1)初始化
Test * pArray3[3]={new Test(4),new Test(1,2)};    //3个元素分别用(2),(2),(1)初始化，用new出来的地址去初始化指针数组里的元素（指针）
//pArray3[]是一个指针数组（而非对象数组），里面的每个元素都是一个指针而非对象，所以不需要初始化，pArray[2]就是一个没有初始化的指针
```



