### 浅谈面向对象程序设计方法

#### 1、结构化程序设计的思考？

1. 结构化程序设计
   * 复杂的大问题→
     层层分解/模块化→
     若干子问题
   * 自顶而下，逐步求精
   * 程序=数据结构（变量）+算法（函数）
2. 结构化程序设计中，算法和数据结构没有直观联系
3. 结构化程序设计的程序模式

   ![](/assets/Screenshot from 2017-06-12 21:19:23.png)

4. 结构化程序设计的问题

   * _**理解难**_：随着程序规模的增加，程序变得非常难以理解。很难一下子在程序当中呢看出具体某个数据结构和函数直接是一个什么样的关系。任何两个函数之间存在着怎么样的调用关系呢？也很难清楚的知道。
   * _**修改难**_：因为结构化设计本身是没有封装的概念的。所以如果我们想要修改其中某一个变量定义的时候，就必须把所有访问该变量的语句全部找出来才能修改。非常不利于程序本身的维护和扩充。
   * _**差错难**_：当某个数据结构的值不正常的时候，因为本身程序呢关系错综复杂，很难找出到底是哪个函数所导致的。
   * _**重用难**_：在结构化的程序设计设计当中呢，随着程序规模的不断增大， 由于程序关系本身错综复杂，所以想要抽取其中需要的部分代码就会变得十分的困难。

---

* [x] 业界需要面向对象，软件设计的目标是更快、更正确、更经济。

#### 2、面向**对象**的程序设计方法：

1. 面向对象的**程序=类+类+...+类**，设计**程序**的过程→设计**类**的过程
2. 抽象和封装是面向对象的两个基本概念

   ![](/assets/Screenshot from 2017-06-12 21:32:41.png)

3. 可以看到，在面向对象的程序中，除了包含一个main函数之外，还会有一系列的类，在每一个类之内，又有一些特定的数据结构和相应的函数关系，类和类之间也存在一定的关系。有了类的封装，整个程序就变得非常清晰化和条理化。

   ![](/assets/Screenshot from 2017-06-12 21:34:48.png)

4. Gru面对千姿百态的minion，如何创建或者修改其中的一个minion呢？

   \(1\) 抽象/封装

   ![](/assets/Screenshot from 2017-06-12 21:57:03.png)

    \(2\) 实例化/赋值 （对minion其中的一个成员属性进行赋值）生成新的minion

   ![](/assets/Screenshot from 2017-06-12 21:57:39.png)

\*上例就是由一类事物抽象成一个类，再由一个类去生成新的实例化的对象的过程。

#### 3、类的定义

利用关键字class定义类

```
class 类名
{
  访问范围说明符：
    成员变量1
    成员变量2
    ...
    成员函数声明1
    成员函数声明2
  访问范围说明符：
    更多成员变量
    更多成员函数声明
    ...
};
```

视频地址：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first)

2017.06.12
