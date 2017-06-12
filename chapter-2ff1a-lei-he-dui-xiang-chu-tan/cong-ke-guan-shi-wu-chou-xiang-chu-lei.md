从客观事物抽象出类的例子

1、例子

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

2、对象的内存分配

1. 对象的内存空间
   1. 对象的大小=所有成员变量的大小之和
   2. E.g. CRectangle类的对象，sizeof\(CRectangle\)=8，即2个int的大小
2. 每个对象各有自己的存储空间
   1. 一个对象的某个成员变量被改变，不会影响到其他的对象。
3. 对象之间可以使用“=”进行赋值

4. 不能用“==”，“！=”，“&gt;”，“&lt;”，“&gt;=”，“&lt;=”进行比较，除非这些运算符经过了重载。

---

课程视频：[https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first](https://courses.edx.org/courses/course-v1:PekingX+04831750.1x+2015T1/courseware/ead35a945fe64078b09a03272620ed3a/b61817773f6e43d7af6b6284efc9b316/?child=first)

2017.06.12

