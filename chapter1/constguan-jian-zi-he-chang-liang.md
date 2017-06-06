const关键字

1  定义常量\(const是有类型性的，便于类型检查。少用define\)

```
const int MAX_VAL=23;    //定义了一个整型常量
const double Pi = 3.14;    //定义了一个浮点型常量
const char*SCHOOL_NAME="Peking University";    //char*类型的常量，字符串指针的常量，SCHOOL_NAME就是一个指针常量。2
```

2  定义常量指针

* 注意：不可以通过常量指针修改其指向的内容

```
int n,m;
const int*p=&n;    //p是一个cont int*类型的指针，即常量指针，p指向n
*p=5;    //报错，因为试图通过p修改其指向的内容
n=4;     //ok
p=&m;    //ok，常量指针的指向可以变化
```

* 注意：不能把常量指针赋值给非常量指针，反过来可以。

```
const int*p1;int*p2;
p1=p2;    //ok
p2=p1;    //error。因为我们倾向于常量指针指向的内容尽量不要被修改，如果把他赋值给非常量指针p2，那就可以通过修改p2指向的内容（如*p2=4）来修改p1指向的内容。
p2=(int*)p1;    //ok,强制类型转换，吧p1强制转换成一个int×类型的指针，再赋值给p2。
```

* 把函数参数写为常量指针，可避免函数内部不小心改变参数指针所指向地方的内容。

```
void MyPrintf(const char*p)
{
    strcpy(p,"this");    //编译出错，因为函数strcpy()第一参数的类型是char*，而参数p的类型位const char*类型
    printf("%s",p);    //ok
}
```

3  定义常引用

不能通过常引用修改其引用的变量

```
int n;
const int&r=n;
r=5;    //error
n=4;    ok
```



