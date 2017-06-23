# 成员对象和封闭类

### 1. 成员对象

**成员对象：**一个类的成员变量是另一个类的对象

包含**成员对象**的类叫做**封闭类**（Enclosing）——&gt;类和类之间也是可以_**交织在一起**_的

eg 1:

```java
class CTyre{        //轮胎类
    private：
        int radius;    //半径
        int width;     //宽度
    public:
        CTyre(int r,int w):radius(r),width(w){}    //初始化列表，不是简单的“radius=r,width=w”这样的赋值语句进行初始化
}; 
                                           //这种初始化方式比进行赋值的风格看起来更好一些
class CEngine{         //引擎类
};

class CCar{                //汽车类——>封闭类，因为包含了2个成员对象
    private:
        int price;    //价格，传统的成员变量
        CTyre tyre;        //成员对象
        CEngine engine;    //成员对象
    public:
        CCar(int p,int tr,int tw);    //构造函数，下一个语句使用初始化列表来初始化CCar这个构造函数
};
CCar::CCar(int p,int tr,int w):price(p),tyre(tr,w){    //初始化列表，把p初始化给price，tr和w初始化给tyre，使得CCar里的
};  
                                                //每一个成员变量都有相应参数的一个初始化
int main(){
    CCar car(20000,17,225);    //定义一个新的CCar这样的实例化的对象，其中20000初始化为price，17初始化为半径，255初始化为宽度
    return 0;
}
```

* [x] 在例子中，如果CCar类_不定义构造函数_，则

  ```
  CCar car;    //error——>编译出错
  ```

  因为：编译器不知道car.tyre该如何初始化

  而car.engine初始化没有问题，因为本身没有对应的参数，可以使用默认的构造函数。

* [x] 因此，生成封闭类对象的语句，**必须明确“对象中的成员对象”是否需要进行相应的初始化。**

### 2. 如何初始化？——封闭类构造函数的“初始化列表”

* 定义封闭类的构造函数时，**添加初始化列表**：
  类名::构造函数\(参数表\)**:成员变量1\(参数表\),成员变量2\(参数表\),...**

{

...

}

* 成员对象初始化列表中的参数
  * 任意复杂的表达式
  * 函数/变量/表达式中的函数，变量有定义

### 3. 调用顺序

* 当封闭类对象生成时
  * Step 1：执行所有成员对象的构造函数
  * Step 2：执行封闭类的构造函数
* 成员对象的构造函数调用顺序
  * 和成员对象在类中的说明顺序一致
  * 与在成员初始化列表中出现的顺序无关
* 当封闭类的**对象消亡**时  （先构造的后析构，后构造的先析构）
  * Step 1：先执行封闭类的析构函数
  * Step 2：执行成员对象的析构函数
* 析构函数顺序和构造函数的调用顺序**相反**

eg 2：

```java
class CTyre
class CCar{
    private:
        CEngine engine;
        CTyre tyre;
    public:
        CCar(){cout<<"CCar contructor"<<endl;}
        ~CCar(){cout<<"CCar destructor"<<endl;}        
};

int main(){
    CCar car;
    return 0;
}
```



