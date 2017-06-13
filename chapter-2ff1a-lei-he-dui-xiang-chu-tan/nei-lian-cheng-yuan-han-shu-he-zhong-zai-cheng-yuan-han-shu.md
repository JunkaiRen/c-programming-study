内联成员函数和重载成员函数

* 内联成员函数定义方式

  * inline + 成员函数
  * 整个函数体出现在类定义内部

  eg：方法1和方法2均定义了两个函数位内联成员函数

* 成员函数的重载及参数缺省
  * 重载成员函数
  * 成员函数可以带缺省值

  ```
  #include <iostream>
  using namespace std;
  class Location{
      private:
          int x,y;
      public:
          void init(int x=0,int y=0);
   函数(1) void valueX(int val){x=val;}    //两个同名函数valueX(),即成员函数重载
   函数(2) int valueX(){return x;}        //这两个函数由于参数的不同，被标记为两个不同的函数
  };

  void Location::init(int X,int Y){
      x=X;
      y=Y;
  }
  int main(){
      Location A;
      A.init(5);    //5被赋值给x，使用缺省参数0
      A.valueX(5);
      cout<<A.valueX();
      return 0;
  }
  ```



