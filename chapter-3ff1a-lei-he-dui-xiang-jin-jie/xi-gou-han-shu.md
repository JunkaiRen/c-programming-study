析构函数（Destructor）

* 复习：构造函数

  * 成员函数的一种
  * 名字**与类名相同**
  * 可以有**参数**，不能有**返回值**
  * 可以有多个构造函数函数
  * 用来**初始化**对象

* 析构函数

  * 名字**与类名相同**
  * 在前面加“**～**”
  * 没有参数和返回值
  * 一个类**最多**只能有**一个**析构函数
  * 在对象消亡时**自动被调用**
    * 在对象消亡前做善后工作
      * 释放分配空间等 （在此之前，如果采用new动态分配内存，那么在各个地方编写delete语句时，需要确保程序的每一条路径上都能释放内存）
      * 有了析构函数后，只需要在析构函数里去使用delete语句，就能够确保对象运行中，使用new分配的空间在对象消亡时都被释放掉了。
  * 定义类时没写析构函数，则编译器**生成缺省析构函数**
    * 不涉及释放用户申请的内存释放等清理工作
  * 定义了析构函数，则编译器不生成缺省的析构函数

    ```
    class String{
        private：
            char * p;
        public:
            String(){
                p=new char[10];        //构造函数里，new出了一个char型的数组，使用一个char*去指向数组的首地址
            }
        ~String();            //定义析构函数
    };
    String::~String(){
        delete [] p;          //在析构函数里对new出的内存空间进行释放，就需要写一个相应的delete语句。
    }                         //这样，在调用析构函数时，自动去delete掉相应的内存空间
                              //注意，对于数组而言，要去delete掉的话，要使用[];否则，只写delete p，只是delete一个对象。
    ```

* 析构函数和数组

  * 对象数组生命期结束时，对象数组的**每个元素**的**析构函数**都会被调用

    ```
    class Ctest{
        public:
            ~Ctest(){
                cout<<"destructor called"<<endl;    //自己定义的析构函数
            } 
    };
    int main(){
        Ctest array[2];            //定义了一个Ctest类下面的数组，包含两个对象
        cout<<"End Main"<<endl;
        return 0;        //程序结束之前，就要释放相应的对象，这时程序就回去调用相应的析构函数
    }
    ——————
    输出
    End Main
    destructor called
    destructor called    //因为有两个数组对象，对应有两次析构函数的调用，因此有两条“destructor called”语句，分别对应两个
                      //数组对象消亡，产生析构函数的调用
    ```

* 析构函数和运算符delete

  * 使用delete语句也可以导致析构函数的调用

    ```
    Ctest * pTest;
    pTest = new Ctest;    //pTest指向new出来的一个Ctest,每次调用new的时候都会使得构造函数被调用到
    delete pTest;         //在new出一片内存空间后，要释放时就需要delete掉，只要使用delete运算，就会调用一个相应的析构函数
    ——————————
    pTest = new Ctest[3];   //new出来了一个数组，构造函数被调用3次
    delete [] pTest;        //析构函数被调用3次
    ```

* 构造函数和析构函数调用时机的例题

  ```
  class Demo{
          int id;
      public:
              Demo(int i)        //定义构造函数来进行初始化的传递
              {
                      id=i;
                      cout<<"id="<<id<<"Constructed"<<endl;
              }
              ~Demo()        //定义析构函数，即对应id的对象会被消亡掉
              {
                      cout<<"id="<<id<<"Distructed"<<endl;
              }
  };

  Demo d1(1);                       //a.定义了一个全局变量的对象，1为变量，输出id=1 Constructed
  void Func(){
          static Demo d2(2);        //g1.定义静态变量d2，输出id=2 Constructed
          Demo d3(3)                //g2.定义全局变量d3，输出id=3 Constructed
          cout<<"Func"<<endl;       //g3.打印输出Func，输出Func
                                    //g4.Func()函数结束，在这对花括号{}的作用域里包含了两个变量d2和d3.因为d2是静态的，
                                //静态变量的消亡会在整个程序结束之时，因此在这个作用域下消亡的只有d3，输出id=3 Distructed
  }

  int main(){                //b.程序进入main函数
          Demo d4(4);        //c.定义了一个局部变量d4,4为变量，输出id=4 Constructed
          d4=6;              //d.有了d4这个对象之后，执行这一条赋值语句，把常量赋值给d4.此处调用类型转换构造函数
                          //通过生成一个临时的demo对象，把6赋值给相应的d4，因此输出id=6 Constructed
                          //同时当这个临时对象消亡时，又要将这个临时对象析构掉，因此输出id=6 Distructed
          cout<<"main"<<endl;        //e.输出main
          {    Demo d5(5)  }         //f.{}为作用域，语法规定离对象最近的一对{}表示对象的作用域，因此输出id=5 Constructed和id=5 Distructed
          Func();                    //g.进入Func()这样一个函数
          cout << "main ends"<<endl; //h.输出main ends
          return 0;                  //i.全局变量d1，静态变量d2，main函数定义的局部变量d4都还没有消亡
                                  //析构顺序为“先被构造的对象会最后被析构掉”，因此输出顺序为：id=6 Distructed；id=2 Distructed；id=1 Distructed
  }
  ————————
  输出
  id=1 Constructed
  id=4 Constructed
  id=6 Constructed
  id=6 Destructed
  main
  id=5 Constructed
  id=5 Destructed
  id=2 Constructed
  id=3 Constructed
  Func
  id=3 Destructed
  main ends
  id=6 Destructed
  id=2 Destructed
  id=1 Destructed
  ```

* 构造函数和析构函数在不同编译器中的表现

  * 个别调用情况不一致

    * 编译器有bug

    * 代码优化措施

  * 这里讨论的是C++标准



