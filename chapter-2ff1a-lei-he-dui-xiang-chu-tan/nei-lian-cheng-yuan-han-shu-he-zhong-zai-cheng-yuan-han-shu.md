### 内联成员函数和重载成员函数

1. #### 内联成员函数定义方式

   * inline + 成员函数
   * 整个函数体出现在类定义内部

   eg：方法1和方法2均定义了两个函数位内联成员函数

2. #### 成员函数的重载及参数缺省

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
       A.init(5);    //5被赋值给x，y使用init()的缺省参数0
       A.valueX(5);    //由于函数有参，因此调用成员函数(1)，给x赋值5
       cout<<A.valueX();    //由于函数无参，因此调用成员函数(2),只返回x的值
       return 0;
   }
   ```
3. #### 使用缺省参数时，要注意**避免**有函数重载时的**二义性**

   ```
   class Location{
       private:
           int x,y;
       public:
           void init(int x=0,int y=0);
           void valueX(int val=0){x=val;}    //对于一个valueX()的参数val，给出了初始值0，即它是有一个默认的具体的缺省值的
           int valueX(){return x;}
   };
       Location A;
       A.valueX();    //错误！！编译器无法判断调用那个value
   ```

---

课程视频：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first)

2017.06.13





