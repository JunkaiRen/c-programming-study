### 从客观事物抽象出类的例子

#### 1、例子

![](/assets/Screenshot from 2017-06-12 22:34:55.png)

* 创建矩形类

![](/assets/Screenshot from 2017-06-12 22:37:43.png)

```
   类的具体实现（类定义）：
```

```
class CRectangle {
    public:    //访问范围说明符，后续会讲解。
        int w,h;    //定义两个变量来表示矩形的宽和高
        void Init(int w_,int h_){    //初始化函数
            w=w_;h=h_;
        }
        int Area(){                //求面积函数
            return w*h;
        }
        int Perimeter(){            //求周长函数
            return 2*(w+h);
        }
};//必须有分号
```

* 使用上面创建的矩形类（类的实例化），类定义的**变量**→
  类的**实例**→
  “**对象**”

```
int main(){
    int w,h;    //定义款和高
    CRectangle r;    //用类声明的一个新的对象r，r是一个对象，有了对象就可以通过对象访问类的成员函数。类定义的变量就是类的实例，即对象。
    cin>>w>>h;    //键盘输入w和h
    r.Init(w,h);    //通过r的Init函数去初始化从键盘输入的宽和高
    cout<<r.Area()<<endl<<r.Perimeter();    //计算r的面积和周长
    return 0;
}
```

#### 2、对象的内存分配

* 对象的内存空间
  1. 对象的大小=所有成员变量的大小之和
  2. E.g. CRectangle类的对象，sizeof\(CRectangle\)=8，即2个int的大小
* 每个对象各有自己的存储空间
  1. 一个对象的某个成员变量被改变，不会影响到其他的对象。
* 对象之间可以使用“=”进行赋值

* 不能用“==”，“！=”，“&gt;”，“&lt;”，“&gt;=”，“&lt;=”进行比较，除非这些运算符经过了重载。

#### 3、访问类的成员变量和成员函数

* **用法1：对象名.成员名**

  ```
  CRectangle r1,r2;
  r1.w = 5;        //通过成员变量w，把5赋值给对象r1里面的w。
  r2.Init(3,4);    //通过成员函数Init()，把3和4分别赋值给对象r2里面的w和h。
  ```

* 用法2：指针 -&gt; 成员名

  ```
  CRectangle r1,r2;
  CRectangle r1,r2;
  CRectangle * p1 = & r1;      //用CRectangle类型定义指针*p1和*p2，分别指向r1和r2这两个对象的首地址。
  CRectangle * p2 = & r2;
  p1 -> w = 5;           //之后就可以用p1和p2来指向对应的w和Init函数。
  p2 -> Init(3,4);       //Init作用在p2指向的对象r2
  ```

* 用法3：**引用名**.成员名

  ```
  CRectangle r2;
  CRectangle & rr = r2;    //rr就是r2的一个别名
  rr.w = 5;
  rr.Init(3,4);    //rr的值改变了，r2的值也会改变
  ```

\*另一种输出结果的方式

```
void PrintRectangle(CRectangle & r){
    cout << r.Area() << "," << r.Perimeter();
}
CRectangle r3;
r3.Init(3,4);
PrintRectangle r3;
```

#### 4、成员函数体和类的定义分开写，利用"**::**"

* 之前我们把类的成员函数的定义写在类的定义中间。我们还可以把成员函数从类的定义中分离出来，只在类定义里面声明这个类里面包含了这一系列的成员函数，而具体的函数的定义则放在整个类的定义之外。

```
class CRectangle
{
    public:
        int w,h;
        int Area();    //仅在此声明成员函数
        int Perimeter();
        void Init(int w_,int h_);
};

int CRectangle::Area(){    //利用CRectangle::这样的一个标记去声明这三个函数不是普通意义上的函数，它是属于CRectangle类的。
    return w * h;          //这样三个函数就可以作为类的成员函数来进行定义了
}
int Crectangle::Perimeter(){
    return 2 * (w + h);
}
void CRectangle::Init(int w_,int h_){
    w = w_; h = h_;
}
```

* 注意，同样的，在调用这些类的成员函数的时候，仍然需要使用对象、对象的指针或者是对象的引用来进行，它也不能作为普通函数来进行访问。

---

课程视频：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first)

2017.06.12

