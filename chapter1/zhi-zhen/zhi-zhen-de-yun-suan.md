1、两个同类型的指针变量，可以比较大小，比较的就是里面存放的 _**地址 **_的大小

* 地址p1&lt;地址p2 $$\Leftrightarrow $$ p1&lt;p2值为真。
* 地址p1=地址p2 $$\Leftrightarrow $$ p1==p2值为真。
* 地址p1&gt;地址p2 $$\Leftrightarrow $$ p1&gt;p2值为真。

2、两个同类型的指针变量，可以相减

* 两个T\*类型的指针p1和p2，p1—p2=\(地址p1—地址p2\)/sizeof\(T\)
* 即这两个地址之间可以存放多少个T类型的变量

3、指针变量加减一个整数的结果是指针

* p：T\*类型的指针
* n：整数类型的变量或常量
* 则 p+n：为T\*类型的指针，指向地址为（地址p+nxsizeof\(T\)）

4、指针变量可以自增、自减

* T\*类型的指针p指向地址n，则
  * p++，++p：p指向n+sizeof\(T\)
  * p——，——p：p指向n-sizeof\(T\)

5、指针可以用下标运算符"\[ \]"进行运算

* p是一个T\*类型的指针，n是整数类型的变量或常量
* 则 p\[n\]等价于 \*\(p+n\)

---

如何访问int类型变量a前面的那一个字节？

```
int a;
char * p = (char * ) &a;    //强制类型转换，&a是int*类型。如果不转换。--p会访问a前面4个字节（int）
--p;
printf("%c", * p);    //可能导致运行错误，因为a前面一个字节的内存，系统不一定允许访问
* p = 'A';            //可能导致运行错误，因为a前面一个字节的内存，系统不一定允许访问
```

![](/assets/Screenshot from 2017-06-11 20:24:50.png)





课程地址：[http://www.icourse163.org/learn/PKU-1001553023?tid=1001995004\#/learn/content?type=detail&id=1002616215&cid=1002864455](http://www.icourse163.org/learn/PKU-1001553023?tid=1001995004#/learn/content?type=detail&id=1002616215&cid=1002864455 "课程视频")

2017.6.11





