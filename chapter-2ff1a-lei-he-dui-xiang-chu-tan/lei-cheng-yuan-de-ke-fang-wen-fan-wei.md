类成员的可访问范围

* 关键字——类成员可**被访问的范围**
  * private：指定私有成员，**只能在成员函数内被访问**
  * public：指定公有成员，可以在任何地方被访问
  * protected：指定保护成员
* 三种关键字的出现次数和先后顺序没有限制
* 定义一个类

```
class className{
    private:                //书名类成员的可见性
        私有属性和函数
    public:
        公有属性和函数
    protected:
        保护属性和函数
};
```

* 缺省为**私有成员**

```
class Man{
        int nAge；            //私有成员，只能在成员函数内被访问
        char szName[20];        //私有成员
    public:
        void SetName(char * Name){
            strcpy(szName,Name)    //因为在成员函数内部，所以szName[]可以被访问
            }
};
```

2、对象成员的访问权限

* 类的成员函数内部，可以访问：
  * 当前对象的全部属性，函数
  * 同类其他对象的全部属性，函数
* 类的成员函数以外的地方

  * 只能访问该类对象的公有成员

    ![](/assets/Screenshot from 2017-06-13 09:56:19.png)

    ![](/assets/Screenshot from 2017-06-13 09:55:09.png)

  * 我们强制要求对成员变量的访问一定要通过成员函数，这样的好处呢，就可以有效地把私有成员呢隐藏起来，它不会暴露在非常公开的地方，所有的函数或者是程序员都可以对它进行访问，而是需要通过成员函数来进行。那么有了这样的机制呢，可以保证我们的程序呢，少出错，同时呢，也容易修改。

  * 我们来具体看一看说，如果我的这个程序现在从PC呢迁移到了手机上，那么我的szName呢不再是一个20个的一个数组，它只能允许呢包含5个成员。即 szName→    char szName\[5\]
    * 

---

课程视频：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first)

