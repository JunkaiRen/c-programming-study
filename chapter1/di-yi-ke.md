函数指针

1. 定义

程序运行期间，每个函数会占用一段连续的内存空间，而函数名就是该函数所占内存区域的起始地址（入口地址）。将该地址赋给一个指针变量，通过指针变量就可以调用该函数。则这个指针变量就称为“函数指针”

2. 书写形式：回值类型\(\*指针变量名\)\(参数类型1，参数类型2，...\);

eg：

```
int(*pf)(int, char);
```

表示pf是一个函数指针，它所指向的函数返回值类型应该是int，该函数有两个参数，第一个是int类型，第二个是char类型。

3. 使用方法

可以用一个原型匹配的函数的名字给一个函数指针赋值，要通过函数指针调用它所指向的函数，写法为：_函数指针名\(实参表\);_

eg：

```
#include <stdio.h>
void PrintMin(int a,int b) //PrintMin返回两个参数中较小的那个
{    
    if(a<b)
        printf("%d",a);
    else
        printf("%d",b);
}
int main()
{
    void(*pf)(int,int); //定义了指针pf，说明了它返回值是void类型，参数是int类型.因此函数PrintMin与指针pf匹配。
    int x=4,y=5;
    pf=PrintMin;        //赋值语句，让pf指向PrintMin
    pf(x,y);            //调用了pf指向的函数（PrintMin）
    return 0;
}
```

1. qsort库函数

qsort库函数（C语言快速排序库函数），可以对任意类型的数组进行排序。

```
void qsort(void *base,int nelem,unsigned int width,int(*pfCompara)(const void*,const void*));pfCompara即指针
```

排序就是一不断比较并交换位置的过程。qsort函数在执行期间，会通过pfCompara指针调用“比较函数”，然后根据比较函数的返回值判断哪个元素应该排在前面。

eg：

调用qsort函数，将一个unsigned int数组按照**个位数**从小到大进行排序。

```
#include <stdio.h>
#include <stdlib.h>
int MyCompare(const void*elem1,const void*elem2)    //两个参数都是void*类型的 
{
    unsigned int*p1,*p2;
    p1=(unsigned int*)elem1;    //写*elem非法。elem是void*类型的指针，所以编译器不知道elem1指向的元素是多少字节的。由于我们知道
                                //*elem1指向的是一个unsigned int类型的元素，所以需要对elem1进行强制类型转换，把它强制转换成一个unsigned int*类型的指针
    p2=(unsigned int*)elem2;
    return(*p1%10)-(*p2%10);    //通过*p1就可以指向*elem指向的那个元素。
}
#define NUM5
int main()
{
    unsigned int an[NUM]={8,123,11,10,4};
    qsort(an,NUM,sizeof(unsigned int),MyCompare);    //此处第四个参数本应该是一个函数指针，但是由于函数名字跟函数指针的类型
    for(int i=0;i<NUM;i++)                            //是匹配的，MyCompare函数的形式正好跟qsort的第四个参数那个函数指针所指向的函数，它的形式是一样的，所以此处放一个函数的名字MyCompare
        printf("%d",an[i]);
    return 0;
}


输出结果：10 11 123 4 8
```



