#### 1、空指针

* 地址0不能访问，指向地址0的指针就是空指针
* 可以用“NULL”关键字对任何类型的指针进行赋值。NULL实际上就是整数0，值为NULL的指针就是空指针。

  eg：

  ```
  int * pn = NULL;
  char * pc = NULL;
  int * p2 = 0;    //0就是NULL

  而类如 * pn =..., int n=*pn都是错误的，因为绝大多数操作系统都不允许去访问（读/写）地址0的内容。
  ```

* 指针可以作为条件表达式使用。如果指针的值位NULL，则相当于为假；值不为NULL，就相当于为真。

  如果p为指针，则有：

  * if \(p\) $$\Leftrightarrow $$ if \(p!=NULL\)

  * if \(!p\)$$\Leftrightarrow $$ if \(p==NULL\)

#### 2、指针作为函数参数

c++中很多库函数的参数是指针类型的

```
#include <iostream>
using namespace std;
void Swap（int *p1,int *p2）    //Swap()的形参是p1,p2
{
    int tmp = *p1;    //创建临时变量tmp，将p1指向的变量的值，赋给tmp
    *p1 = *p2;        //将p2指向的变量的值，赋给p1指向的变量
    *p2 = tmp;        //将tmp的值赋给p2指向的变量
}
int main()
{
    int m = 3,n = 4;
    Swap(&m,&n);    //使得p1指向m，p2指向n：实参&m是一个指针，&m是m的地址，在c和c++中函数的形参的值是实参的一个拷贝，所以指针p1的地址也是m的地址，即p1指向m。
    cout << m << " " << n << endl;    //输出4 3
    return 0;
}
```

**形参是实参的一个拷贝，改变形参不会改变实参。**上例中并没有通过改变形参而改变实参，因为实参是&m而非m，变量m的地址（&m）并没有改变，只是该地址处的值改变了。





课程地址：[http://www.icourse163.org/learn/PKU-1001553023?tid=1001995004\#/learn/content?type=detail&id=1002616216&cid=1002864456&replay=true](http://www.icourse163.org/learn/PKU-1001553023?tid=1001995004#/learn/content?type=detail&id=1002616216&cid=1002864456&replay=true)

2017.06.11

