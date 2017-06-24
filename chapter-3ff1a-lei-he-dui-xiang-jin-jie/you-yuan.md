# 友元（Friend）

### 1. 友元函数

一个类的**友元函数**可以访问该类的**私有成员（private）**

* [x] 一个成员被声明为private的，那么只有在这个类的成员函数内部才可以被访问到；但是有时候，有些公共函数或**类成员之外的函数**可能会**需要用到某个类的私有成员**，那么就可以**声明**这个**函数是这个类的友元函数**。

```java
class CCar;    //提前声明CCar类，以便后面CDriver类使用
class CDriver{
    public:
        void ModifyCar(CCar * pCar);    //C++中，当类的对象是指针的时候，就要用到->指向类中的成员
};

class CCar{
    private:
        int price;    //私有变量 price
    friend int MostExpensiveCar(CCar cars[],int total);    //把函数MostExpensiveCar(不属于类的成员函数，而是全局函数)
                                                        //声明为类的友元函数，这样它就可以访问类CCar里的私有成员price
    firend void CDriver::ModifyCar(CCar * pCar);           //其他类的成员函数，访问CCar类的私有成员price
};

void CDriver::ModifyCar(CCar * pCar)    //由于已经声明函数为友元类型，因此可以在函数内部访问对应的CCar类的私有成员变量price
{
    pCar->price+=1000;    //汽车改装后价值增加
}
int MostExpensiveCar(CCar cars[],int total)    //求最贵的汽车价格，在全局函数里访问对应的CCar类的私有成员变量price
{
    int tmpMax=-1;
    for (int i=0;i<total;++i)
        if(cars[i].price>tmpMax)
            tmpMax=cars[i].price;
    return tmpMax;
}
int main()
{
    return 0;
}
```

* [x] C++中当定义类对象是指针对象时候，就需要用到-&gt;指向类中的成员；当定义一般对象时候时就需要用到"."指向类中的成员

例如：

```java
class A 
{ 
    public 
        play(); 
};

如果定义如下：

A *p则使用：p->play(); 左边是结构指针。 
A p 则使用：p.paly(); 左边是结构变量
```

除了友元函数外，还可以将一个成员函数（包括构造、析构函数）定义为另外一个类的友元

```java
class B{
    public:
        void function();
};
class A{
    friend void B::function();
};
```

### 2. 友元类



