### 类型转换构造函数

目的：实现类型的自动转换

特点：只有一个参数，不是复制构造函数

编译系统会自动调用转换构造函数，建立一个临时对象/临时变量

eg：复数类

    class Complex{
        public:
            double real,imag;
            Complex(int i){               //（2）类型转换构造函数（本身是构造函数，与类同名，同时只有一个参数）
                cout<<"IntCountstructor called"<<endl;
                real=i;imag=0;            //在这个类型转换构造函数里头它实现的功能就是首先呢cout这个函数被调用到了，此外呢，就是用这个i去初始化实部，而虚部呢，就直接赋值为0了。
            }
            Complex(double r,double i)    //（1）传统的构造函数，传入一个r和i，分别初始化实部和虚部
            {real=r;imag=i;}
    };
    int main(){
        Complex c1(7,8);    //调用（1）
        Complex c2=12；     //调用（2）。“=”不是赋值，而是初始化
        c1=9；              //调用（2）。“=”是赋值语句，编译器自动调用赋值构造函数，9被自动转换成一个临时的Complex对象赋值给c1
                            //c1是Complex类型，而9是一个整形常量，但编译器不会报错，原因是9作为一个实参，调用Complex （int i）这样一个类型转换构造函数来进行初始化。那么有了这样的一个初始化之后，
    ``````````````````````````我们就可以将这个临时对象的值，也就是说实际上它变成了一个complex对象，赋给c1，
        cout<<c1.real<<","<<c1.imag<<endl;
        return 0;
    }
    ————————
    输出
    IntCountstructor called
    IntCountstructor called
    9,0



