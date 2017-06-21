# 静态成员变量与静态成员函数

### 基本概念

静态成员：在说明前面加了static关键字的成员。

```java
class CRectangle
{
    private:
        int w,h;
        static int nTotalArea;        //静态成员变量，用于记录所有矩形对象的总面积
        static int nTotalNumber;      //用于记录所有矩形对象的总数目
    public:
        CRectangle(int w_,int h_);
        ~Crectangle();
        static void PrintTotal();     //静态成员函数
};
```

区别：普通成员变量——&gt;每个对象有各自的一份；而静态成员变量一共就一份，**为所有对象共享**。

注意：sizeof 运算符不会计算静态成员变量

```java
class CMyclass{
    int n;
    static int s;
};

则sizeof（CMclass）等于4，没有计算静态成员变量s
```

区别2：普通成员函数必须具体作用于某个对象，而静态成员函数**不具体作用于某个对象。**

因此静态成员**不需要通过对象**就能访问。

### 如何访问静态成员

1. 类名::成员名
   **CRectangle::PrintTotal\(\); **    //访问静态成员函数
2. 对象名.成员名
   CRectangle r; **r.PrintTotal\(\);**
3. 指针-&gt;成员名
   CRectangle \* p =&r;  **p-&gt;PrintTotal\(\);**
4. 引用.成员名
   CRectangle & ref = r;  int n = **ref.nTotalNumber;**

静态成员变量，本质上是**全局变量**，哪怕一个对象都不存在，类的静态成员变量也存在。

静态成员函数，本质上是**全局函数**。

设置静态成员这种机制的目的：**将和某些类紧密相关的全局变量和全局函数写到类里面，看上去像一个整体，易于维护和理解**。

### 静态成员示例

考虑一个需要随时知道矩形总数和矩形面积的图形处理程序，可以用全局变量记录总是和总面积，但是**用静态成员将这两个变量封装进类中，就更容易理解和维护**。

```java
class CRectangle
{
    private:
        int w,h;    //普通成员变量，每个矩形对象有各自的一份，代表各自矩形的宽和高。
        static int nTotalArea;      //两个静态成员变量，用来记录所有矩形的总面积和总数
        static int nTotalNumber; //可以用两个全局变量来代替，但是体现不出来它和CRectangle类的紧密关系，同时也容易被其他类所访问，不易维护
    public:                      //因此，把这两个变量写到CRectangle类里面，成为静态成员变量。
        CRectangle(int w_,int h_)
        ~CRectangle();
        static void PrintTotal();    //静态成员函数，只与CRectangle类有关
};

——————————

CRectangle::CRectangle(int w_,int h_)
{
    w=w_;
    h=h_;
    nTotalNumber ++;        //因为只有有矩形对象的生成，就一定会引发构造函数的调用，因此在构造函数里既可以增加矩形的总数和总面积。
    nTotalArea + = w*h;
}
CRectangle::~CRectangle()
{
    nTotalNumber --;
    nTotalArea - = w*h;
}
void CRectangle::PrintTotal()
{
    cout<<nTotalNumber<<","<<nTotalArea<<endl;
}
```



